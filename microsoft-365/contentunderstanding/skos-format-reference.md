---
title: SharePoint 분류에 대한 SKOS 형식 참조
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: SharePoint 분류에 대한 SKOS 형식 참조
ms.openlocfilehash: 90c20ddb440e216941a5ea06f1aa815cb80102a9
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087285"
---
# <a name="skos-format-reference-for-sharepoint-taxonomy"></a><span data-ttu-id="e35ec-103">SharePoint 분류에 대한 SKOS 형식 참조</span><span class="sxs-lookup"><span data-stu-id="e35ec-103">SKOS format reference for SharePoint taxonomy</span></span>

<span data-ttu-id="e35ec-104">본 문서는 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)를 나타내는 데 사용되는 RDF 용어를 포함하고 있으며 [SKOS](https://www.w3.org/TR/skos-primer/)를 기반으로 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-104">This article includes RDF vocabulary used to represent [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) and is based on [SKOS](https://www.w3.org/TR/skos-primer/).</span></span> <span data-ttu-id="e35ec-105">이 RDF 구문을 직렬화하려면 RDF [TURTLE](https://www.w3.org/TR/turtle/)을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="e35ec-105">For serialization of this RDF syntax, use RDF [TURTLE](https://www.w3.org/TR/turtle/).</span></span>

<span data-ttu-id="e35ec-106">다음 표에서 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 용어에 해당하는 [SKOS](https://www.w3.org/TR/skos-primer/)를 표시합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-106">The following table shows the [SKOS](https://www.w3.org/TR/skos-primer/) equivalents for the [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary.</span></span> <span data-ttu-id="e35ec-107">SharePoint는 해당하는 SharePoint 분류가 없는 [SKOS](https://www.w3.org/TR/skos-primer/) 값을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-107">SharePoint does not support [SKOS](https://www.w3.org/TR/skos-primer/) values that have no SharePoint taxonomy equivalent.</span></span>

|<span data-ttu-id="e35ec-108">SharePoint 분류</span><span class="sxs-lookup"><span data-stu-id="e35ec-108">SharePoint taxonomy</span></span>|<span data-ttu-id="e35ec-109">해당하는 SKOS</span><span class="sxs-lookup"><span data-stu-id="e35ec-109">SKOS equivalent</span></span>|
|:-----------------|:--------------|
|<span data-ttu-id="e35ec-110">sharepoint-taxonomy:Term</span><span class="sxs-lookup"><span data-stu-id="e35ec-110">sharepoint-taxonomy:Term</span></span>|<span data-ttu-id="e35ec-111">skos:Concept</span><span class="sxs-lookup"><span data-stu-id="e35ec-111">skos:Concept</span></span>|
|<span data-ttu-id="e35ec-112">sharepoint-taxonomy:TermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-112">sharepoint-taxonomy:TermSet</span></span>|<span data-ttu-id="e35ec-113">skos:ConceptScheme</span><span class="sxs-lookup"><span data-stu-id="e35ec-113">skos:ConceptScheme</span></span>|
|<span data-ttu-id="e35ec-114">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-114">sharepoint-taxonomy:inTermSet</span></span>|<span data-ttu-id="e35ec-115">skos:inScheme</span><span class="sxs-lookup"><span data-stu-id="e35ec-115">skos:inScheme</span></span>|
|<span data-ttu-id="e35ec-116">sharepoint-taxonomy:hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-116">sharepoint-taxonomy:hasTopLevelTerm</span></span>|<span data-ttu-id="e35ec-117">skos:hasTopConcept</span><span class="sxs-lookup"><span data-stu-id="e35ec-117">skos:hasTopConcept</span></span>|
|<span data-ttu-id="e35ec-118">sharepoint-taxonomy:topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="e35ec-118">sharepoint-taxonomy:topLevelTermOf</span></span>|<span data-ttu-id="e35ec-119">skos:topConceptOf</span><span class="sxs-lookup"><span data-stu-id="e35ec-119">skos:topConceptOf</span></span>|
|<span data-ttu-id="e35ec-120">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-120">sharepoint-taxonomy:defaultLabel</span></span>|<span data-ttu-id="e35ec-121">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-121">skos:prefLabel</span></span>|
|<span data-ttu-id="e35ec-122">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="e35ec-122">sharepoint-taxonomy:termSetName</span></span>|<span data-ttu-id="e35ec-123">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-123">skos:prefLabel</span></span>|
|<span data-ttu-id="e35ec-124">sharepoint-taxonomy:propertyName</span><span class="sxs-lookup"><span data-stu-id="e35ec-124">sharepoint-taxonomy:propertyName</span></span>|<span data-ttu-id="e35ec-125">skos:prefLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-125">skos:prefLabel</span></span>|
|<span data-ttu-id="e35ec-126">sharepoint-taxonomy:otherLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-126">sharepoint-taxonomy:otherLabel</span></span>|<span data-ttu-id="e35ec-127">skos:altLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-127">skos:altLabel</span></span>|
|<span data-ttu-id="e35ec-128">sharepoint-taxonomy:description</span><span class="sxs-lookup"><span data-stu-id="e35ec-128">sharepoint-taxonomy:description</span></span>|<span data-ttu-id="e35ec-129">skos:definition</span><span class="sxs-lookup"><span data-stu-id="e35ec-129">skos:definition</span></span>|
|<span data-ttu-id="e35ec-130">sharepoint-taxonomy:parent</span><span class="sxs-lookup"><span data-stu-id="e35ec-130">sharepoint-taxonomy:parent</span></span>|<span data-ttu-id="e35ec-131">skos:broader</span><span class="sxs-lookup"><span data-stu-id="e35ec-131">skos:broader</span></span>|
|<span data-ttu-id="e35ec-132">sharepoint-taxonomy:child</span><span class="sxs-lookup"><span data-stu-id="e35ec-132">sharepoint-taxonomy:child</span></span>|<span data-ttu-id="e35ec-133">skos:narrower</span><span class="sxs-lookup"><span data-stu-id="e35ec-133">skos:narrower</span></span>|

<span data-ttu-id="e35ec-134">다음 표는 [OWL](https://www.w3.org/TR/owl2-primer/)에서 파생된 SharePoint 분류 용어의 엔터티입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-134">The following table displays the entities of the SharePoint taxonomy vocabulary derived from [OWL](https://www.w3.org/TR/owl2-primer/).</span></span>

|<span data-ttu-id="e35ec-135">SharePoint 분류 용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-135">SharePoint taxonomy vocabulary</span></span>|<span data-ttu-id="e35ec-136">OWL에서 파생</span><span class="sxs-lookup"><span data-stu-id="e35ec-136">Derived from OWL</span></span>|
|:-----------------------------|:----------------------|
|<span data-ttu-id="e35ec-137">sharepoint-taxonomy:isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="e35ec-137">sharepoint-taxonomy:isAvailableForTagging</span></span>|<span data-ttu-id="e35ec-138">owl:datatypeproperty</span><span class="sxs-lookup"><span data-stu-id="e35ec-138">owl:datatypeproperty</span></span>|
|<span data-ttu-id="e35ec-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-139">sharepoint-taxonomy:SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="e35ec-140">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="e35ec-140">owl:ObjectProperty</span></span>|
|<span data-ttu-id="e35ec-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-141">sharepoint-taxonomy:LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="e35ec-142">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="e35ec-142">owl:ObjectProperty</span></span>|
|<span data-ttu-id="e35ec-143">sharepoint-taxonomy:CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-143">sharepoint-taxonomy:CustomPropertyForTermSet</span></span>|<span data-ttu-id="e35ec-144">owl:ObjectProperty</span><span class="sxs-lookup"><span data-stu-id="e35ec-144">owl:ObjectProperty</span></span>|

## <a name="sharepoint-taxonomy-vocabulary"></a><span data-ttu-id="e35ec-145">SharePoint 분류 용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-145">SharePoint taxonomy vocabulary</span></span>

<span data-ttu-id="e35ec-146">분류는 공식 분류 체계입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-146">A taxonomy is a formal classification system.</span></span> <span data-ttu-id="e35ec-147">분류는 요소를 설명하는 단어, 레이블, 용어를 그룹화하고 해당 그룹을 계층 구조로 정렬합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-147">A taxonomy groups the words, labels, and terms that describe something, and then arranges the groups into a hierarchy.</span></span>

<span data-ttu-id="e35ec-148">**sharepoint-taxonomy:Term**</span><span class="sxs-lookup"><span data-stu-id="e35ec-148">**sharepoint-taxonomy:Term**</span></span>

<span data-ttu-id="e35ec-149">관리된 메타데이터 계층 구조에서 Term 또는 Keyword를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-149">Represents a Term or a Keyword in a managed metadata hierarchy.</span></span>

<span data-ttu-id="e35ec-150">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 원자성 단위입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-150">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is the atomic unit of a SharePoint [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore).</span></span> <span data-ttu-id="e35ec-151">각 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)는 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에 속한 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-151">Each [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belongs to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) that belongs to a [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> 

<span data-ttu-id="e35ec-152">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-152">The syntax to define a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) is as follows:</span></span>

```SKOS
ex:TermA    a    sharepoint-taxonomy:Term;
    sharepoint-taxonomy:inTermSet    ex:TermSetA;
    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA;
    sharepoint-taxonomy:child    ex:TermA1;
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharePoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="e35ec-153">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 필수적으로 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) 내에 존재합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-153">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) compulsorily exists within a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-154">DefaultLabel은 시각적 표현에 표시되는 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-154">DefaultLabel is the name of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) as it appears in the visual representation.</span></span> <span data-ttu-id="e35ec-155">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의하는 데 필요한 필드에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-155">The required fields for defining a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) include:</span></span>

- <span data-ttu-id="e35ec-156">sharepoint-taxonomy:defaultLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-156">sharepoint-taxonomy:defaultLabel</span></span>
- <span data-ttu-id="e35ec-157">sharepoint-taxonomy:inTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-157">sharepoint-taxonomy:inTermSet</span></span>

<span data-ttu-id="e35ec-158">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 다음 사항을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-158">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can:</span></span>

- <span data-ttu-id="e35ec-159">동일한 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있는 두 가지 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)과 제공된 다른 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 관련될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-159">Be hierarchically related to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is provided both the [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) belong to the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="e35ec-160">여러 하위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)이 있지만 하나의 상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)만 가집니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-160">Have multiple child [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), but only a single parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>
- <span data-ttu-id="e35ec-161">topLevelTermOf [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 경우 상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)이 정의되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-161">Not have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) defined, if it is a topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>
- <span data-ttu-id="e35ec-162">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 당 하나의 defaultLabel이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-162">Have one defaultLabel, per [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>
- <span data-ttu-id="e35ec-163">상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)이 포함되지 않거나 topLevelTermOf [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)이 아닌 경우 존재하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-163">Not exist if it neither contains a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), nor is the topLevelTermOf a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> 
- <span data-ttu-id="e35ec-164">동일한 계층 수준에 고유한 defaultLabel이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-164">Have only a unique defaultLabel in the same hierarchical level.</span></span>

<span data-ttu-id="e35ec-165">**sharepoint-taxonomy:TermSet**</span><span class="sxs-lookup"><span data-stu-id="e35ec-165">**sharepoint-taxonomy:TermSet**</span></span>

<span data-ttu-id="e35ec-166">"TermSet" 이라는 계층적 또는 일련의 용어 개체 집합을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-166">Represents a hierarchical or flat set of Term objects known as a "TermSet".</span></span>

<span data-ttu-id="e35ec-167">이름에서 알 수 있듯이 TermSet은 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)의 집합입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-167">As the name suggests, TermSet is a set of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="e35ec-168">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore)의 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 속해 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-168">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) must belong to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-169">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 독립적으로 존재할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-169">No [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can exist independently.</span></span> 

<span data-ttu-id="e35ec-170">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-170">The syntax to define a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

```SKOS
ex:TermSetA    a    sharepoint-taxonomy:TermSet;
    sharepoint-taxonomy:termSetName    “TermSet A";
    sharepoint-taxonomy:isAvailableForTagging    “true”^^xsd:Boolean;
    sharepoint-taxonomy:hasTopLevelTerm    Ex:Term A.
```

<span data-ttu-id="e35ec-171">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)은 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group)에서 논리적으로 함께 그룹화됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-171">[TermSets](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) are logically grouped together in [TermGroups](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group).</span></span> <span data-ttu-id="e35ec-172">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 정의하는 데 필요한 필드에는 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-172">The required field for defining a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) is:</span></span>

- <span data-ttu-id="e35ec-173">sharepoint-taxonomy:termSetName</span><span class="sxs-lookup"><span data-stu-id="e35ec-173">sharepoint-taxonomy:termSetName</span></span>

<span data-ttu-id="e35ec-174">제공된 termSetName이 [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group) 내에서 고유하지 않은 경우 SharePoint는 이름 끝에 숫자를 추가하여 termSetName의 고유성을 유지합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-174">In the case of the termSetName provided is not unique within the [TermGroup](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.group), SharePoint appends a number at the end of the name to maintain the uniqueness of termSetName(s).</span></span>

<span data-ttu-id="e35ec-175">**sharepoint-taxonomy:hasTopLevelTerm**</span><span class="sxs-lookup"><span data-stu-id="e35ec-175">**sharepoint-taxonomy:hasTopLevelTerm**</span></span>

<span data-ttu-id="e35ec-176">SharePoint는 이 속성을 사용하여 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에서 맨 위의 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 매핑합니다. 이는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에서 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)의 계층 구조에 대한 진입점입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-176">SharePoint uses this property to map the top most [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), which is the entry point to the hierarchy of [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-177">이는 sharepoint-taxonomy:topLevelTermOf와 역 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-177">This is an inverse relation to sharepoint-taxonomy:topLevelTermOf.</span></span> 

<span data-ttu-id="e35ec-178">이를 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-178">The syntax to define this is:</span></span>

```SKOS
ex:TermSetA    sharepoint-taxonomy:hasTopLevelTerm    ex:TermA.
```

>[!NOTE]
> <span data-ttu-id="e35ec-179">상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)의 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 정의할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-179">You cannot define the top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="e35ec-180">**sharepoint-taxonomy:topLevelTermOf**</span><span class="sxs-lookup"><span data-stu-id="e35ec-180">**sharepoint-taxonomy:topLevelTermOf**</span></span>

<span data-ttu-id="e35ec-181">sharepoint-taxonomy:topLevelTermOf는 sharepoint-taxonomy:hasTopLevelTerm과 역 관계입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-181">Sharepoint-taxonomy:topLevelTermOf is the inverse of sharepoint-taxonomy:hasTopLevelTerm</span></span>

<span data-ttu-id="e35ec-182">이를 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-182">The syntax to define this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:topLevelTermOf    ex:TermSetA.
```

<span data-ttu-id="e35ec-183">**sharepoint-taxonomy:inTermSet**</span><span class="sxs-lookup"><span data-stu-id="e35ec-183">**sharepoint-taxonomy:inTermSet**</span></span>

<span data-ttu-id="e35ec-184">이를 사용하여 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 매핑합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-184">Use this to map a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-185">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 단일 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에만 존재할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-185">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) can only exist in a single [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-186">[용어를 정의](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term)하는 경우 SharePoint에서 해당 속성이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-186">SharePoint requires this property when [defining a term](https://github.com/MicrosoftDocs/microsoft-365-docs-pr/blob/3a3cd54dd076b18bdff1d43b3e342897f8704c23/microsoft-365/contentunderstanding/skos-format-reference.md#term).</span></span>

## <a name="required-labels"></a><span data-ttu-id="e35ec-187">필수 레이블</span><span class="sxs-lookup"><span data-stu-id="e35ec-187">Required labels</span></span>

<span data-ttu-id="e35ec-188">조직에서 관리된 메타데이터를 사용하기 전에 신중하게 계획해야 할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-188">Your organization may want to do careful planning before you start to use managed metadata.</span></span> <span data-ttu-id="e35ec-189">수행해야 하는 계획의 양은 분류의 공식적인 정도에 따라 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-189">The amount of planning that you must do depends on how formal your taxonomy is.</span></span> <span data-ttu-id="e35ec-190">또한 메타데이터에 적용할 제어 정도에 따라서도 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-190">It also depends on how much control that you want to impose on metadata.</span></span> <span data-ttu-id="e35ec-191">각 계층 수준에서 Term이나 TermSet의 필수 레이블을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-191">At each level of the hierarchy, you need to configure required labels for a Term or TermSet.</span></span>

<span data-ttu-id="e35ec-192">Term에는 기본 언어로 레이블이 하나 이상 포함될 수 있으며 기본 언어가 아닌 경우 1개 이상의 레이블이 있거나 레이블이 없을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-192">A Term can have one or more labels in the default language, and zero or more labels in the non-default language.</span></span> <span data-ttu-id="e35ec-193">용어에 언어 레이블이 있는 경우 레이블 중 하나는 기본 레이블이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-193">If the term has labels in a language, one of the labels must be the default label.</span></span>

<span data-ttu-id="e35ec-194">**sharepoint-taxonomy:defaultLabel**</span><span class="sxs-lookup"><span data-stu-id="e35ec-194">**sharepoint-taxonomy:defaultLabel**</span></span>

<span data-ttu-id="e35ec-195">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 필수 매개 변수인 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 기본 어휘 레이블을 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-195">Use this default lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) that is a required parameter for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="e35ec-196">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 시각적으로 나타내기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-196">Use to visually representing the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="e35ec-197">DefaultLabel을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-197">The syntax to define a defaultLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:defaultLabel    “Term A”@en-us.
```

<span data-ttu-id="e35ec-198">DefaultLabel에는 문자열 및 언어 태그의 두 부분이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-198">The defaultLabel contains two parts to it – the string and the language tag.</span></span> <span data-ttu-id="e35ec-199">언어는 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-199">The language must be one of the [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working languages.</span></span> <span data-ttu-id="e35ec-200">DefaultLabel은 동일한 계층 수준에서 동일한 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 모든 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대해 고유해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-200">The defaultLabel must be unique for all [Terms](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) in the same [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), at the same hierarchical level.</span></span>

<span data-ttu-id="e35ec-201">**sharepoint-taxonomy:termSetName**</span><span class="sxs-lookup"><span data-stu-id="e35ec-201">**sharepoint-taxonomy:termSetName**</span></span>

<span data-ttu-id="e35ec-202">현재 TermSet 개체의 이름을 가져오고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-202">Gets and sets the name for the current TermSet object.</span></span>

<span data-ttu-id="e35ec-203">[TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어에 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대한 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-203">This the lexical label for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span> <span data-ttu-id="e35ec-204">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대한 필수 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-204">This is a required parameter for a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-205">[TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 시각적으로 나타내기 위해 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-205">Use to visually representing a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span>

<span data-ttu-id="e35ec-206">termSetName을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-206">The syntax to define a termSetName is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:TermSetName    “Term Set A”@en-us.
```

<span data-ttu-id="e35ec-207">**sharepoint-taxonomy:propertyName**</span><span class="sxs-lookup"><span data-stu-id="e35ec-207">**sharepoint-taxonomy:propertyName**</span></span>

<span data-ttu-id="e35ec-208">현재 TermSet 개체의 속성 이름을 가져오고 설정합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-208">Gets and sets the property name for the current TermSet object.</span></span>

<span data-ttu-id="e35ec-209">이는 [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) 작업 언어에서 sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet에 대한 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-209">This is the lexical label for a sharepoint-taxonomy:SharedCustomPropertyForTerm, sharepoint-taxonomy:LocalCustomPropertyForTerm and sharepoint-taxonomy:CustomPropertyForTermSet in a [TermStore](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termstore) working language.</span></span>

<span data-ttu-id="e35ec-210">sharepoint-taxonomy:propertyName은 CustomProperty의 키로 간주됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-210">The sharepoint-taxonomy:propertyName is treated as the key of the CustomProperty.</span></span>

<span data-ttu-id="e35ec-211">propertyName을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-211">The syntax to define a propetyName is:</span></span>

```SKOS
ex:SharedCustomProperty1    sharepoint-taxonomy:propertyName    “Shared Custom Property Key 1”@en-us.
```

## <a name="optional-labels"></a><span data-ttu-id="e35ec-212">선택적 레이블</span><span class="sxs-lookup"><span data-stu-id="e35ec-212">Optional labels</span></span>

<span data-ttu-id="e35ec-213">분류에 선택적 레이블을 추가할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-213">You can also add optional labels to your taxonomy.</span></span>

<span data-ttu-id="e35ec-214">**sharepoint-taxonomy:otherLabel**</span><span class="sxs-lookup"><span data-stu-id="e35ec-214">**sharepoint-taxonomy:otherLabel**</span></span>

<span data-ttu-id="e35ec-215">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 대체 어휘 레이블입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-215">This is the alternate lexical label for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="e35ec-216">otherLabel을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-216">The syntax to define an otherLabel is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:otherLabel    “Term A”@en-us.
```

## <a name="semantic-relationships"></a><span data-ttu-id="e35ec-217">의미 관계</span><span class="sxs-lookup"><span data-stu-id="e35ec-217">Semantic relationships</span></span>

<span data-ttu-id="e35ec-218">분류는 계층적이며 때때로 단순한 "관련 용어" 연관 관계를 가지지만 일부는 "의미 관계" 또는 사용자 지정 관계를 가지기도 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-218">Taxonomies have hierarchical and sometimes a simple “related term” associative relationship, but some have "semantic relationships" or custom-created relationships.</span></span> 

<span data-ttu-id="e35ec-219">**sharepoint-taxonomy:parent**</span><span class="sxs-lookup"><span data-stu-id="e35ec-219">**sharepoint-taxonomy:parent**</span></span>

<span data-ttu-id="e35ec-220">이는 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 관련되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-220">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> <span data-ttu-id="e35ec-221">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)은 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)의 최상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)이 될 수 있지만 최상위 Term이 아닌 경우에는 상위 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-221">A [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) could be a top level [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) of a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), but in case it doesn’t it must have a parent [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span> 

<span data-ttu-id="e35ec-222">상위 항목을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-222">The syntax to define a parent is:</span></span>

```SKOS
ex:TermA1    sharepoint-taxonomy:parent    ex:TermA.
```

<span data-ttu-id="e35ec-223">즉 TermA가 상위 항목이 될 수 있으며 TermA가 하위 항목이 될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-223">This means that TermA is the parent and  TermA is the child.</span></span>

<span data-ttu-id="e35ec-224">**sharepoint-taxonomy:child**</span><span class="sxs-lookup"><span data-stu-id="e35ec-224">**sharepoint-taxonomy:child**</span></span>

<span data-ttu-id="e35ec-225">개체는 하나 이상의 하위 TermSet 인스턴스를 포함하며 TermSet 속성을 통해 액세스할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-225">The object contains one or more child TermSet instances, and these can be accessed through the TermSets property.</span></span> <span data-ttu-id="e35ec-226">이 클래스는 새 하위 TermSet 개체를 만드는 방법을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-226">This class also provides methods for creating new child TermSet objects.</span></span> <span data-ttu-id="e35ec-227">하위 Term 및 TermSet 인스턴스 편집 권한은 그룹에서 지정됩니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-227">Permissions for editing child Term and TermSet instances is specified on the group.</span></span> 

<span data-ttu-id="e35ec-228">이는 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)과 계층적으로 관련되게 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-228">This hierarchically relates a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) to another [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term).</span></span>

<span data-ttu-id="e35ec-229">하위 항목을 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-229">The syntax to define a child is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:child    ex:TermA1.
```

<span data-ttu-id="e35ec-230">즉 TermA가 상위 항목이 될 수 있으며 TermA가 하위 항목이 될 수 있음을 의미합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-230">This means that TermA is the parent and  TermA is the child.</span></span>

## <a name="documentation-notes"></a><span data-ttu-id="e35ec-231">문서 노트</span><span class="sxs-lookup"><span data-stu-id="e35ec-231">Documentation notes</span></span>

<span data-ttu-id="e35ec-232">이 섹션에서는 Microsoft.SharePoint.Taxonomy Namespace에서 상세하게 나온 분류에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-232">This section discusses the taxonomy detailed in the Microsoft.SharePoint.Taxonomy Namespace.</span></span>

<span data-ttu-id="e35ec-233">**sharepoint-taxonomy:description**</span><span class="sxs-lookup"><span data-stu-id="e35ec-233">**sharepoint-taxonomy:description**</span></span>

<span data-ttu-id="e35ec-234">이는 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) 용어 엔터티에 대한 자세한 설명입니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-234">This is a detailed explanation of any [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) vocabulary entity.</span></span> 

<span data-ttu-id="e35ec-235">설명을 추가하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-235">The syntax to add a description is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:description    “Term A is the top level term of TermSetA”@en-us.
```

## <a name="custom-properties"></a><span data-ttu-id="e35ec-236">사용자 지정 속성</span><span class="sxs-lookup"><span data-stu-id="e35ec-236">Custom properties</span></span>

<span data-ttu-id="e35ec-237">읽기 전용 사전에서 현재 Term 개체에 대한 사용자 지정 속성 개체의 컬렉션을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-237">Gets the collection of custom property objects for the current Term object from the read-only dictionary.</span></span>

<span data-ttu-id="e35ec-238">사용자 지정 속성은 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 정의할 수 있는 키 값 쌍으로서 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)에 대해 상세히 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-238">Custom Properties are key-values pairs that can be defined for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset), to further the description of the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset).</span></span> <span data-ttu-id="e35ec-239">SharePoint는 propertyName에 대한 도움말이 있는 사용자 지정 속성의 키를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-239">SharePoint specifies the key of the custom property with the help of propertyName.</span></span>

<span data-ttu-id="e35ec-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span><span class="sxs-lookup"><span data-stu-id="e35ec-240">**sharepoint-taxonomy:CustomPropertyForTermSet**</span></span>

<span data-ttu-id="e35ec-241">이를 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-241">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp1    rdf:type    sharepoint-taxonomy:CustomPropertyForTermSet;
    sharepoint-taxonomy:propertyName “Colour”.

ex:TermSetA    ex:CustomProp1    “Red”@en-us.
```

<span data-ttu-id="e35ec-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="e35ec-242">**sharepoint-taxonomy:SharedCustomPropertyForTerm**</span></span>

<span data-ttu-id="e35ec-243">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 사용자 지정 속성을 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)함께 사용해야 하는 경우 해당 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 위치에서 재사용한 다음 SharedCustomPropertyForTerm에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-243">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) needs to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to be define it under SharedCustomPropertyForTerm.</span></span>

<span data-ttu-id="e35ec-244">이를 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-244">The syntax to define this is:</span></span>

``` SKOS
ex:CustomProp2    rdf:type sharepoint-taxonomy:SharedCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “Length”.

ex:TermA    ex:CustomProp2    “5 cm”@en-us.
```
<span data-ttu-id="e35ec-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span><span class="sxs-lookup"><span data-stu-id="e35ec-245">**sharepoint-taxonomy:LocalCustomPropertyForTerm**</span></span>

<span data-ttu-id="e35ec-246">[Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)에 대한 사용자 지정 속성을 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)함께 사용하지 않아야 하는 경우 해당 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term)을 다른 위치에서 재사용한 다음 LocalCustomPropertyForTerm에서 정의해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-246">If the custom property for a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) does not need to be carried along with the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term), when you reuse the [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) somewhere else, then you need to define it under LocalCustomPropertyForTerm.</span></span>

<span data-ttu-id="e35ec-247">이를 정의하는 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-247">The syntax to define this is:</span></span>

```SKOS
ex:CustomProp3    rdf:type sharepoint-taxonomy:LocalCustomPropertyForTerm;
    sharepoint-taxonomy:propertyName “width”.

ex:TermA    ex:CustomProp3    “5 cm”@en-us.
```

## <a name="data-properties"></a><span data-ttu-id="e35ec-248">데이터 속성</span><span class="sxs-lookup"><span data-stu-id="e35ec-248">Data properties</span></span>

<span data-ttu-id="e35ec-249">각 계층 수준에서 Term이나 TermSet의 특정 데이터 속성을 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-249">At each level of the hierarchy, you can configure specific data properties for a Term or TermSet.</span></span>

<span data-ttu-id="e35ec-250">**sharepoint-taxonomy:isAvailableForTagging**</span><span class="sxs-lookup"><span data-stu-id="e35ec-250">**sharepoint-taxonomy:isAvailableForTagging**</span></span>

<span data-ttu-id="e35ec-251">이 속성을 사용하여 [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) 또는 [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset)을 SharePoint 목록 및 라이브러리에서 사용할 수 있는지 여부를 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-251">Use this to specify if a [Term](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.term) or a [TermSet](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy.termset) available in SharePoint Lists and Libraries.</span></span>  

<span data-ttu-id="e35ec-252">이에 대한 구문은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-252">The syntax for this is:</span></span>

```SKOS
ex:TermA    sharepoint-taxonomy:isAvailableForTagging     "true"^^xsd:Boolean;
```

## <a name="domain-and-range"></a><span data-ttu-id="e35ec-253">도메인 및 범위</span><span class="sxs-lookup"><span data-stu-id="e35ec-253">Domain and range</span></span>

<span data-ttu-id="e35ec-254">아래 표에서는 SharePoint 분류 용어의 도메인 및 범위에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-254">The table below describes the domain and range of SharePoint taxonomy vocabulary.</span></span>

|<span data-ttu-id="e35ec-255">조건부/동사</span><span class="sxs-lookup"><span data-stu-id="e35ec-255">Predicates/verb</span></span>|<span data-ttu-id="e35ec-256">의미</span><span class="sxs-lookup"><span data-stu-id="e35ec-256">Meaning</span></span>|<span data-ttu-id="e35ec-257">도메인</span><span class="sxs-lookup"><span data-stu-id="e35ec-257">Domain</span></span>|<span data-ttu-id="e35ec-258">범위</span><span class="sxs-lookup"><span data-stu-id="e35ec-258">Range</span></span>|
|:--------------|:------|:-----|:----|
<span data-ttu-id="e35ec-259">inTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-259">inTermSet</span></span>|<span data-ttu-id="e35ec-260">용어 집합에 속함</span><span class="sxs-lookup"><span data-stu-id="e35ec-260">In term set</span></span>|<span data-ttu-id="e35ec-261">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-261">Term</span></span>|<span data-ttu-id="e35ec-262">용어 집합</span><span class="sxs-lookup"><span data-stu-id="e35ec-262">Term Set</span></span>|
<span data-ttu-id="e35ec-263">inTermGroup</span><span class="sxs-lookup"><span data-stu-id="e35ec-263">inTermGroup</span></span>|<span data-ttu-id="e35ec-264">용어 그룹에 속함</span><span class="sxs-lookup"><span data-stu-id="e35ec-264">In term group</span></span>|<span data-ttu-id="e35ec-265">TermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-265">TermSet</span></span>|<span data-ttu-id="e35ec-266">TermGroup</span><span class="sxs-lookup"><span data-stu-id="e35ec-266">TermGroup</span></span>|
<span data-ttu-id="e35ec-267">topLevelTermOf</span><span class="sxs-lookup"><span data-stu-id="e35ec-267">topLevelTermOf</span></span>|<span data-ttu-id="e35ec-268">최상위 용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-268">Is Top Level Term Of</span></span>|<span data-ttu-id="e35ec-269">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-269">Term</span></span>|<span data-ttu-id="e35ec-270">TermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-270">TermSet</span></span>|
<span data-ttu-id="e35ec-271">hasTopLevelTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-271">hasTopLevelTerm</span></span>|<span data-ttu-id="e35ec-272">최상위 용어 보유</span><span class="sxs-lookup"><span data-stu-id="e35ec-272">Has top level term</span></span>|<span data-ttu-id="e35ec-273">용어 집합</span><span class="sxs-lookup"><span data-stu-id="e35ec-273">Term Set</span></span>|<span data-ttu-id="e35ec-274">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-274">Term</span></span>|
<span data-ttu-id="e35ec-275">termSetName</span><span class="sxs-lookup"><span data-stu-id="e35ec-275">termSetName</span></span>|<span data-ttu-id="e35ec-276">용어 집합에 이름이 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-276">Term set has Name</span></span>|<span data-ttu-id="e35ec-277">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-277">Term</span></span>|<span data-ttu-id="e35ec-278">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="e35ec-278">Plain literal</span></span>|
<span data-ttu-id="e35ec-279">defaultLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-279">defaultLabel</span></span>|<span data-ttu-id="e35ec-280">용어에 기본 레이블이 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-280">Term has default label</span></span>|<span data-ttu-id="e35ec-281">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-281">Term</span></span>|<span data-ttu-id="e35ec-282">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="e35ec-282">Plain literal</span></span>|
<span data-ttu-id="e35ec-283">otherLabel</span><span class="sxs-lookup"><span data-stu-id="e35ec-283">otherLabel</span></span>|<span data-ttu-id="e35ec-284">용어에 기타 레이블이 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-284">Term has other label</span></span>|<span data-ttu-id="e35ec-285">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-285">Term</span></span>|<span data-ttu-id="e35ec-286">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="e35ec-286">Plain literal</span></span>|
<span data-ttu-id="e35ec-287">propertyName</span><span class="sxs-lookup"><span data-stu-id="e35ec-287">propertyName</span></span>|<span data-ttu-id="e35ec-288">속성 레이블이 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-288">Has Property Label</span></span>|<span data-ttu-id="e35ec-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-289">SharedCustomPropertyForTerm, LocalCustomPropertyForTerm, CustomPropertyForTermSet</span></span> |<span data-ttu-id="e35ec-290">부울, 문자열, 정수, 소수, 실수</span><span class="sxs-lookup"><span data-stu-id="e35ec-290">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="e35ec-291">description</span><span class="sxs-lookup"><span data-stu-id="e35ec-291">description</span></span>|<span data-ttu-id="e35ec-292">설명 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-292">Has Description</span></span>|<span data-ttu-id="e35ec-293">모두</span><span class="sxs-lookup"><span data-stu-id="e35ec-293">All</span></span>|<span data-ttu-id="e35ec-294">일반 리터럴</span><span class="sxs-lookup"><span data-stu-id="e35ec-294">Plain literal</span></span>|
|<span data-ttu-id="e35ec-295">parent</span><span class="sxs-lookup"><span data-stu-id="e35ec-295">parent</span></span>|<span data-ttu-id="e35ec-296">상위 용어 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-296">Has parent</span></span>|<span data-ttu-id="e35ec-297">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-297">Term</span></span>|<span data-ttu-id="e35ec-298">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-298">Term</span></span>|
|<span data-ttu-id="e35ec-299">하위</span><span class="sxs-lookup"><span data-stu-id="e35ec-299">child</span></span>|<span data-ttu-id="e35ec-300">하위 용어 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-300">Has Child</span></span>|<span data-ttu-id="e35ec-301">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-301">Term</span></span>|<span data-ttu-id="e35ec-302">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-302">Term</span></span>|
|<span data-ttu-id="e35ec-303">isAvailableForTagging</span><span class="sxs-lookup"><span data-stu-id="e35ec-303">isAvailableForTagging</span></span>|<span data-ttu-id="e35ec-304">태그 지정 가능</span><span class="sxs-lookup"><span data-stu-id="e35ec-304">Is available for tagging</span></span>|<span data-ttu-id="e35ec-305">용어, 용어 집합</span><span class="sxs-lookup"><span data-stu-id="e35ec-305">Term, Term Set</span></span>|<span data-ttu-id="e35ec-306">부울</span><span class="sxs-lookup"><span data-stu-id="e35ec-306">Boolean</span></span>|
|<span data-ttu-id="e35ec-307">SharedCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-307">SharedCustomPropertyForTerm</span></span>|<span data-ttu-id="e35ec-308">공유 사용자 지정 속성 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-308">Has shared custom property</span></span>|<span data-ttu-id="e35ec-309">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-309">Term</span></span>|<span data-ttu-id="e35ec-310">부울, 문자열, 정수, 소수, 실수</span><span class="sxs-lookup"><span data-stu-id="e35ec-310">Boolean, string, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="e35ec-311">LocalCustomPropertyForTerm</span><span class="sxs-lookup"><span data-stu-id="e35ec-311">LocalCustomPropertyForTerm</span></span>|<span data-ttu-id="e35ec-312">로컬 사용자 지정 속성 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-312">Has local custom property</span></span>|<span data-ttu-id="e35ec-313">용어</span><span class="sxs-lookup"><span data-stu-id="e35ec-313">Term</span></span>|<span data-ttu-id="e35ec-314">부울, 문자열, 정수, 소수, 실수</span><span class="sxs-lookup"><span data-stu-id="e35ec-314">Boolean, String, Integer, Decimal, Double</span></span>|
|<span data-ttu-id="e35ec-315">CustomPropertyForTermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-315">CustomPropertyForTermSet</span></span>|<span data-ttu-id="e35ec-316">사용자 지정 속성 있음</span><span class="sxs-lookup"><span data-stu-id="e35ec-316">Has Custom Property</span></span>|<span data-ttu-id="e35ec-317">TermSet</span><span class="sxs-lookup"><span data-stu-id="e35ec-317">TermSet</span></span>|<span data-ttu-id="e35ec-318">부울, 문자열, 정수, 소수, 실수</span><span class="sxs-lookup"><span data-stu-id="e35ec-318">Boolean, String, Integer, Decimal, Double</span></span>|

<span data-ttu-id="e35ec-319">[SKOS](https://www.w3.org/TR/skos-primer/)는 [SharePoint 분류](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy)에서 허용하지 않는 유효한 시나리오를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-319">[SKOS](https://www.w3.org/TR/skos-primer/) valid scenarios that [SharePoint taxonomy](https://docs.microsoft.com/dotnet/api/microsoft.sharepoint.taxonomy) does not allow:</span></span>

- <span data-ttu-id="e35ec-320">계층 중복 - [SKOS](https://www.w3.org/TR/skos-primer/) 개념이 여러 광범위한 개념에 동시에 부여될 수 있지만 sharepoint-taxonomy:Term은 하나의 sharepoint-taxonomy:parent만 가지므로 Term의 주기적은 의존은 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-320">Hierarchical redundancy - A [SKOS](https://www.w3.org/TR/skos-primer/) concept can be attached to several broader concepts at the same time, but a sharepoint-taxonomy:Term can have only one sharepoint-taxonomy:parent, hence cyclic dependency, of Terms is also not allowed.</span></span>
- <span data-ttu-id="e35ec-321">분리된 용어는 SharePoint 분류에서 허용되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-321">Orphaned terms are not allowed in SharePoint taxonomy.</span></span> <span data-ttu-id="e35ec-322">모든 sharepoint-taxonomy:Term은 sharepoint-taxonomy:parent를 가지거나 sharepoint-taxonomy:topLevelTermOf a TermSet이어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-322">Every sharepoint-taxonomy:Term should either have a sharepoint-taxonomy:parent or it should be the sharepoint-taxonomy:topLevelTermOf a TermSet.</span></span>
- <span data-ttu-id="e35ec-323">SharePoint 분류는 결합형 관계를 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-323">SharePoint taxonomy does not support associative relations.</span></span>
- <span data-ttu-id="e35ec-324">SharePoint 분류는 sharepoint-taxonomy:parent 및 sharepoint-Taxonomy:child 두 가지 유형의 계층 관계만 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-324">SharePoint taxonomy only allows 2 types of Hierarchical relations – sharepoint-taxonomy:parent and sharepoint-Taxonomy:child.</span></span> 
- <span data-ttu-id="e35ec-325">[SKOS](https://www.w3.org/TR/skos-primer/)와 다르게 SharePoint 분류 용어의 계층적 관계는 동일한 TermSet 내에서만 Term으로 설정될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e35ec-325">Unlike [SKOS](https://www.w3.org/TR/skos-primer/) the hierarchical relationship in SharePoint taxonomy vocabulary, can only be established with Terms within the same TermSet.</span></span>

## <a name="see-also"></a><span data-ttu-id="e35ec-326">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e35ec-326">See also</span></span>

[<span data-ttu-id="e35ec-327">SKOS 기반 형식을 사용하여 용어 집합 가져오기</span><span class="sxs-lookup"><span data-stu-id="e35ec-327">Import a term set using a SKOS-based format</span></span>](import-term-set-skos.md)

