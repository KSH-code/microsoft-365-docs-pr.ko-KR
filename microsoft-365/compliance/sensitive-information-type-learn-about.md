---
title: 중요한 정보 유형에 대해 자세히 알아보기
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: ''
ms.openlocfilehash: e125a6dfb35b7018b5f85100184c842da9231327
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407328"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="5b1d6-102">중요한 정보 유형에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="5b1d6-102">Learn about sensitive information types</span></span>

<span data-ttu-id="5b1d6-103">조직에서 제어하는 중요한 항목을 식별하고 분류하는 것은 정보 보호 분야 의 [첫 번째 단계입니다.](protect-information.md)</span><span class="sxs-lookup"><span data-stu-id="5b1d6-103">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](protect-information.md).</span></span>  <span data-ttu-id="5b1d6-104">Microsoft 365는 항목을 분류할 수 있도록 다음 세 가지 방법으로 항목을 식별합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-104">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="5b1d6-105">사용자가 수동으로</span><span class="sxs-lookup"><span data-stu-id="5b1d6-105">manually by users</span></span>
- <span data-ttu-id="5b1d6-106">중요한 정보 유형과 같은 자동화된 패턴 인식</span><span class="sxs-lookup"><span data-stu-id="5b1d6-106">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="5b1d6-107">기계 학습</span><span class="sxs-lookup"><span data-stu-id="5b1d6-107">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="5b1d6-108">중요한 정보 유형은 패턴 기반 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-108">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="5b1d6-109">또한 주민등의 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요한 정보를 검색하여 중요한 항목을 식별합니다. 중요한 정보 유형 엔터티 정의를 [참조하세요.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="5b1d6-109">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="5b1d6-110">중요한 정보 유형이 사용</span><span class="sxs-lookup"><span data-stu-id="5b1d6-110">Sensitive information types are used in</span></span>

- [<span data-ttu-id="5b1d6-111">데이터 손실 방지 정책</span><span class="sxs-lookup"><span data-stu-id="5b1d6-111">Data loss prevention policies</span></span>](data-loss-prevention-policies.md) 
- [<span data-ttu-id="5b1d6-112">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="5b1d6-112">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="5b1d6-113">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="5b1d6-113">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="5b1d6-114">커뮤니케이션 규정 준수</span><span class="sxs-lookup"><span data-stu-id="5b1d6-114">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="5b1d6-115">자동 레이블 지정 정책</span><span class="sxs-lookup"><span data-stu-id="5b1d6-115">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="5b1d6-116">중요한 정보 유형의 기본 부분</span><span class="sxs-lookup"><span data-stu-id="5b1d6-116">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="5b1d6-117">모든 중요한 정보 유형 엔터티는 다음 필드에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-117">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="5b1d6-118">이름: 중요한 정보 유형을 참조하는 방법</span><span class="sxs-lookup"><span data-stu-id="5b1d6-118">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="5b1d6-119">description: 중요한 정보 유형이 찾는 내용 설명</span><span class="sxs-lookup"><span data-stu-id="5b1d6-119">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="5b1d6-120">패턴: 패턴은 중요한 정보 유형이 감지하는 것을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-120">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="5b1d6-121">다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-121">It consists of the following components</span></span>
    - <span data-ttu-id="5b1d6-122">Primary 요소 - 중요한 정보 유형이 찾는 주 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-122">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="5b1d6-123">체크 um 유효성 **검사,** 키워드 목록, 키워드 사전 또는 함수가 있는 정규식일 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="5b1d6-123">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="5b1d6-124">지원 요소 – 일치의 신뢰를 높이는 데 도움이 되는 증거 역할을 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-124">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="5b1d6-125">예를 들어 SSN 번호와 근접한 키워드 "SSN"입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-125">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="5b1d6-126">체크 um 유효성 검사, 키워드 목록, 키워드 사전을 포함하거나 포함하지 않은 정규식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-126">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="5b1d6-127">신뢰 수준 - 신뢰 수준(높음, 중간, 낮음)은 기본 요소와 함께 감지된 지원 증거의 수준을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-127">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="5b1d6-128">항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에</span><span class="sxs-lookup"><span data-stu-id="5b1d6-128">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="5b1d6-129">근접 - 기본 요소와 지원 요소 사이의 문자 수</span><span class="sxs-lookup"><span data-stu-id="5b1d6-129">Proximity – Number of characters between primary and supporting element</span></span>

![증빙 및 근접 범위 다이어그램](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="5b1d6-131">이 비디오의 신뢰 수준에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="5b1d6-131">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="5b1d6-132">중요한 정보 유형 예</span><span class="sxs-lookup"><span data-stu-id="5b1d6-132">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="5b1d6-133">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="5b1d6-133">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="5b1d6-134">형식</span><span class="sxs-lookup"><span data-stu-id="5b1d6-134">Format</span></span>

<span data-ttu-id="5b1d6-135">마침표로 구분된 8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="5b1d6-135">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="5b1d6-136">패턴</span><span class="sxs-lookup"><span data-stu-id="5b1d6-136">Pattern</span></span>

<span data-ttu-id="5b1d6-137">8자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="5b1d6-137">Eight digits:</span></span>
- <span data-ttu-id="5b1d6-138">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="5b1d6-138">two digits</span></span>
- <span data-ttu-id="5b1d6-139">기간</span><span class="sxs-lookup"><span data-stu-id="5b1d6-139">a period</span></span>
- <span data-ttu-id="5b1d6-140">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="5b1d6-140">three digits</span></span>
- <span data-ttu-id="5b1d6-141">기간</span><span class="sxs-lookup"><span data-stu-id="5b1d6-141">a period</span></span>
- <span data-ttu-id="5b1d6-142">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="5b1d6-142">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="5b1d6-143">체크 um</span><span class="sxs-lookup"><span data-stu-id="5b1d6-143">Checksum</span></span>

<span data-ttu-id="5b1d6-144">아니요</span><span class="sxs-lookup"><span data-stu-id="5b1d6-144">No</span></span>

### <a name="definition"></a><span data-ttu-id="5b1d6-145">정의</span><span class="sxs-lookup"><span data-stu-id="5b1d6-145">Definition</span></span>

<span data-ttu-id="5b1d6-146">DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-146">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="5b1d6-147">정규식 Regex_argentina_national_id 일치하는 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-147">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="5b1d6-148">검색된 Keyword_argentina_national_id 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-148">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="5b1d6-149">키워드</span><span class="sxs-lookup"><span data-stu-id="5b1d6-149">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="5b1d6-150">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="5b1d6-150">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="5b1d6-151">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="5b1d6-151">Argentina National Identity number</span></span> 
- <span data-ttu-id="5b1d6-152">ID</span><span class="sxs-lookup"><span data-stu-id="5b1d6-152">Identity</span></span> 
- <span data-ttu-id="5b1d6-153">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="5b1d6-153">Identification National Identity Card</span></span> 
- <span data-ttu-id="5b1d6-154">DNI</span><span class="sxs-lookup"><span data-stu-id="5b1d6-154">DNI</span></span> 
- <span data-ttu-id="5b1d6-155">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="5b1d6-155">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="5b1d6-156">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="5b1d6-156">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="5b1d6-157">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="5b1d6-157">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="5b1d6-158">Identidad</span><span class="sxs-lookup"><span data-stu-id="5b1d6-158">Identidad</span></span> 
- <span data-ttu-id="5b1d6-159">Identificación</span><span class="sxs-lookup"><span data-stu-id="5b1d6-159">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="5b1d6-160">신뢰 수준에 대한 추가</span><span class="sxs-lookup"><span data-stu-id="5b1d6-160">More on confidence levels</span></span>

<span data-ttu-id="5b1d6-161">중요한 정보 유형 엔터티 정의에서 **신뢰** 수준은 기본 요소 외에 검색되는 증거의 수를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-161">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="5b1d6-162">항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에</span><span class="sxs-lookup"><span data-stu-id="5b1d6-162">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="5b1d6-163">예를 들어 신뢰 수준이 높은 일치는 기본 요소와 근접한 더 많은 증거를 포함하나 신뢰 수준이 낮은 일치는 근접한 증거를 거의 또는 거의 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-163">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="5b1d6-164">신뢰도 수준이 높을수록 가음성은 가장 적지만 가음성은 더 많이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-164">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="5b1d6-165">신뢰 수준이 낮거나 보통이면 가음성은 더 많이 반환하지만 가음성 수준은 0에서 0까지입니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-165">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="5b1d6-166">**낮은 신뢰도:** 값 65, 일치 항목은 가음성은 가장 적지만 오음성은 가장 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-166">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="5b1d6-167">낮은 신뢰도는 낮은 신뢰도, 보통 및 높은 신뢰도 일치를 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-167">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="5b1d6-168">**중간 신뢰도**: 값 75, 일치 항목은 평균 가짓 긍정 양과 거짓 부정을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-168">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="5b1d6-169">보통 신뢰도는 모든 중간 신뢰도 및 높은 신뢰도 일치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-169">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="5b1d6-170">**높은 신뢰도:** 값이 85이면 일치하는 항목은 가음성은 가장 적지만 거짓 부정은 가장 적습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-170">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="5b1d6-171">높은 신뢰도는 높은 일치만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-171">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="5b1d6-172">신뢰도 패턴은 낮은 수로, 5~10개, 신뢰도가 높은 패턴은 20개 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-172">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="5b1d6-173">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="5b1d6-173">Creating custom sensitive information types</span></span>

<span data-ttu-id="5b1d6-174">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형을 만들려면 몇 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-174">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="5b1d6-175">**UI 사용** 보안 및 준수 센터 UI를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니나.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-175">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="5b1d6-176">이 방법을 사용하면 정규식, 키워드 및 키워드 사전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-176">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="5b1d6-177">자세한 내용은 [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-177">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="5b1d6-178">**EDM 사용** EDM(정확한 데이터 일치) 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-178">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="5b1d6-179">이 방법을 사용하면 주기적으로 새로 고칠 수 있는 보안 데이터베이스를 사용하여 동적인 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-179">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="5b1d6-180">[분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-180">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="5b1d6-181">**PowerShell을 사용** PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-181">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="5b1d6-182">이 방법은 UI를 사용하는 것보다 복잡하지만 더 다양한 구성 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-182">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="5b1d6-183">[보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-183">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="5b1d6-184">Microsoft 365 서비스에 대한 데이터 손실 방지, Microsoft 365 서비스에 대한 Microsoft Information Protection, 통신 규정 준수, 정보 거버넌스 및 레코드 관리 내에서 향상된 신뢰 수준을 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-184">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>

> <span data-ttu-id="5b1d6-185">Microsoft 365 Information Protection은 이제 다음에 대해 미리보기 더블 바이트 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-185">Microsoft 365 Information Protection now  supports in preview double byte character set languages for:</span></span>
> - <span data-ttu-id="5b1d6-186">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="5b1d6-186">Chinese (simplified)</span></span>
> - <span data-ttu-id="5b1d6-187">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="5b1d6-187">Chinese (traditional)</span></span>
> - <span data-ttu-id="5b1d6-188">한국어</span><span class="sxs-lookup"><span data-stu-id="5b1d6-188">Korean</span></span>
> - <span data-ttu-id="5b1d6-189">일본어</span><span class="sxs-lookup"><span data-stu-id="5b1d6-189">Japanese</span></span>

><span data-ttu-id="5b1d6-190">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-190">This support is available for sensitive information types.</span></span> <span data-ttu-id="5b1d6-191">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="5b1d6-191">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="5b1d6-192">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="5b1d6-192">For further information</span></span>
- [<span data-ttu-id="5b1d6-193">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="5b1d6-193">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="5b1d6-194">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="5b1d6-194">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="5b1d6-195">PowerShell에서 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="5b1d6-195">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
