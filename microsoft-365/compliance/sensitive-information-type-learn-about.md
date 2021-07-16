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
description: 이 문서에서는 중요한 정보 유형에 대해 간략하게 설명하고 주민등의 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요한 정보를 검색하여 중요한 항목을 식별하는 방법을 제공합니다.
ms.openlocfilehash: dee4ec59ce5fe6140c4aef33d147e89e11facd59
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453624"
---
# <a name="learn-about-sensitive-information-types"></a><span data-ttu-id="4fb60-103">중요한 정보 유형에 대해 자세히 알아보기</span><span class="sxs-lookup"><span data-stu-id="4fb60-103">Learn about sensitive information types</span></span>

<span data-ttu-id="4fb60-104">조직에서 제어하는 중요한 항목을 식별하고 분류하는 것은 정보 보호 분야 의 [첫 번째 단계입니다.](./information-protection.md)</span><span class="sxs-lookup"><span data-stu-id="4fb60-104">Identifying and classifying sensitive items that are under your organizations control is the first step in the [Information Protection discipline](./information-protection.md).</span></span>  <span data-ttu-id="4fb60-105">Microsoft 365 분류할 수 있도록 항목을 식별하는 세 가지 방법을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-105">Microsoft 365 provides three ways of identifying items so that they can be classified:</span></span>

- <span data-ttu-id="4fb60-106">사용자가 수동으로</span><span class="sxs-lookup"><span data-stu-id="4fb60-106">manually by users</span></span>
- <span data-ttu-id="4fb60-107">중요한 정보 유형과 같은 자동화된 패턴 인식</span><span class="sxs-lookup"><span data-stu-id="4fb60-107">automated pattern recognition, like sensitive information types</span></span>
- [<span data-ttu-id="4fb60-108">기계 학습</span><span class="sxs-lookup"><span data-stu-id="4fb60-108">machine learning</span></span>](classifier-learn-about.md)

<span data-ttu-id="4fb60-109">중요한 정보 유형은 패턴 기반 분류자입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-109">Sensitive information types are pattern-based classifiers.</span></span> <span data-ttu-id="4fb60-110">또한 주민등의 보안, 신용 카드 또는 은행 계좌 번호와 같은 중요한 정보를 검색하여 중요한 항목을 식별합니다. 중요한 정보 유형 엔터티 정의를 [참조하세요.](sensitive-information-type-entity-definitions.md)</span><span class="sxs-lookup"><span data-stu-id="4fb60-110">They detect sensitive information like social security, credit card, or bank account numbers to identify sensitive items, see [Sensitive information types entity definitions](sensitive-information-type-entity-definitions.md)</span></span>

## <a name="sensitive-information-types-are-used-in"></a><span data-ttu-id="4fb60-111">중요한 정보 유형이 사용</span><span class="sxs-lookup"><span data-stu-id="4fb60-111">Sensitive information types are used in</span></span>

- [<span data-ttu-id="4fb60-112">데이터 손실 방지 정책</span><span class="sxs-lookup"><span data-stu-id="4fb60-112">Data loss prevention policies</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="4fb60-113">민감도 레이블</span><span class="sxs-lookup"><span data-stu-id="4fb60-113">Sensitivity labels</span></span>](sensitivity-labels.md)
- [<span data-ttu-id="4fb60-114">보존 레이블</span><span class="sxs-lookup"><span data-stu-id="4fb60-114">Retention labels</span></span>](retention.md)
- [<span data-ttu-id="4fb60-115">내부자 위험 관리</span><span class="sxs-lookup"><span data-stu-id="4fb60-115">Insider risk management</span></span>](insider-risk-management.md)
- [<span data-ttu-id="4fb60-116">커뮤니케이션 규정 준수</span><span class="sxs-lookup"><span data-stu-id="4fb60-116">Communication compliance</span></span>](communication-compliance.md)
- [<span data-ttu-id="4fb60-117">자동 레이블 지정 정책</span><span class="sxs-lookup"><span data-stu-id="4fb60-117">Auto-labelling policies</span></span>](apply-sensitivity-label-automatically.md#how-to-configure-auto-labeling-for-office-apps)
- [<span data-ttu-id="4fb60-118">개인 정보 관리(미리 보기)</span><span class="sxs-lookup"><span data-stu-id="4fb60-118">Privacy management (preview)</span></span>](privacy-management.md)

## <a name="fundamental-parts-of-a-sensitive-information-type"></a><span data-ttu-id="4fb60-119">중요한 정보 유형의 기본 부분</span><span class="sxs-lookup"><span data-stu-id="4fb60-119">Fundamental parts of a sensitive information type</span></span>

<span data-ttu-id="4fb60-120">모든 중요한 정보 유형 엔터티는 다음 필드에 의해 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-120">Every sensitive information type entity is defined by these fields:</span></span>

- <span data-ttu-id="4fb60-121">이름: 중요한 정보 유형을 참조하는 방법</span><span class="sxs-lookup"><span data-stu-id="4fb60-121">name: how the sensitive information type is referred to</span></span>
- <span data-ttu-id="4fb60-122">description: 중요한 정보 유형이 찾는 내용 설명</span><span class="sxs-lookup"><span data-stu-id="4fb60-122">description: describes what the sensitive information type is looking for</span></span>
- <span data-ttu-id="4fb60-123">패턴: 패턴은 중요한 정보 유형이 감지하는 것을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-123">pattern: A pattern defines what a sensitive information type detects.</span></span> <span data-ttu-id="4fb60-124">다음 구성 요소로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-124">It consists of the following components</span></span>
    - <span data-ttu-id="4fb60-125">Primary 요소 - 중요한 정보 유형이 찾는 주 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-125">Primary element – the main element that the sensitive information type is looking for.</span></span> <span data-ttu-id="4fb60-126">체크 um 유효성 **검사,** 키워드 목록, 키워드 사전 또는 함수가 있는 정규식일 수 **있습니다.**</span><span class="sxs-lookup"><span data-stu-id="4fb60-126">It can be a **regular expression** with or without a checksum validation, a **keyword list**, a **keyword dictionary**, or a **function**.</span></span>
    - <span data-ttu-id="4fb60-127">지원 요소 – 일치의 신뢰를 높이는 데 도움이 되는 증거 역할을 하는 요소입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-127">Supporting element – elements that act as supporting evidence that help in increasing the confidence of the match.</span></span> <span data-ttu-id="4fb60-128">예를 들어 SSN 번호와 근접한 키워드 "SSN"입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-128">For example, keyword “SSN” in proximity of an SSN number.</span></span> <span data-ttu-id="4fb60-129">체크 um 유효성 검사, 키워드 목록, 키워드 사전을 포함하거나 포함하지 않은 정규식일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-129">It can be a regular expression with or without a checksum validation, keyword list, keyword dictionary.</span></span>
    - <span data-ttu-id="4fb60-130">신뢰 수준 - 신뢰 수준(높음, 중간, 낮음)은 기본 요소와 함께 감지된 지원 증거의 수준을 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-130">Confidence Level - Confidence levels (high, medium, low) reflect how much supporting evidence was detected along with the primary element.</span></span> <span data-ttu-id="4fb60-131">항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에</span><span class="sxs-lookup"><span data-stu-id="4fb60-131">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span>
    - <span data-ttu-id="4fb60-132">근접 - 기본 요소와 지원 요소 사이의 문자 수</span><span class="sxs-lookup"><span data-stu-id="4fb60-132">Proximity – Number of characters between primary and supporting element</span></span>

![증빙 및 근접 범위 다이어그램](../media/dc68e38e-dfa1-45b8-b204-89c8ba121f96.png)

<span data-ttu-id="4fb60-134">이 비디오의 신뢰 수준에 대해 자세히 알아보시다</span><span class="sxs-lookup"><span data-stu-id="4fb60-134">Learn more about confidence levels in this video</span></span>


 > [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Hx60]  

### <a name="example-sensitive-information-type"></a><span data-ttu-id="4fb60-135">중요한 정보 유형 예</span><span class="sxs-lookup"><span data-stu-id="4fb60-135">Example sensitive information type</span></span>


## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="4fb60-136">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="4fb60-136">Argentina national identity (DNI) number</span></span>

### <a name="format"></a><span data-ttu-id="4fb60-137">형식</span><span class="sxs-lookup"><span data-stu-id="4fb60-137">Format</span></span>

<span data-ttu-id="4fb60-138">마침표로 구분된 8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="4fb60-138">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="4fb60-139">패턴</span><span class="sxs-lookup"><span data-stu-id="4fb60-139">Pattern</span></span>

<span data-ttu-id="4fb60-140">8자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="4fb60-140">Eight digits:</span></span>
- <span data-ttu-id="4fb60-141">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="4fb60-141">two digits</span></span>
- <span data-ttu-id="4fb60-142">기간</span><span class="sxs-lookup"><span data-stu-id="4fb60-142">a period</span></span>
- <span data-ttu-id="4fb60-143">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="4fb60-143">three digits</span></span>
- <span data-ttu-id="4fb60-144">기간</span><span class="sxs-lookup"><span data-stu-id="4fb60-144">a period</span></span>
- <span data-ttu-id="4fb60-145">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="4fb60-145">three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="4fb60-146">체크섬</span><span class="sxs-lookup"><span data-stu-id="4fb60-146">Checksum</span></span>

<span data-ttu-id="4fb60-147">아니요</span><span class="sxs-lookup"><span data-stu-id="4fb60-147">No</span></span>

### <a name="definition"></a><span data-ttu-id="4fb60-148">정의</span><span class="sxs-lookup"><span data-stu-id="4fb60-148">Definition</span></span>

<span data-ttu-id="4fb60-149">DLP 정책은 다음의 경우 이러한 유형의 중요한 정보가 300자 이내의 근접성으로 검색될 수 있다는 신뢰를 중간 정도 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-149">A DLP policy has medium confidence that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="4fb60-150">정규식 Regex_argentina_national_id 일치하는 콘텐츠를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-150">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="4fb60-151">검색된 Keyword_argentina_national_id 발견됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-151">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="4fb60-152">키워드</span><span class="sxs-lookup"><span data-stu-id="4fb60-152">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="4fb60-153">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="4fb60-153">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="4fb60-154">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="4fb60-154">Argentina National Identity number</span></span> 
- <span data-ttu-id="4fb60-155">ID</span><span class="sxs-lookup"><span data-stu-id="4fb60-155">Identity</span></span> 
- <span data-ttu-id="4fb60-156">Identification National Identity Card</span><span class="sxs-lookup"><span data-stu-id="4fb60-156">Identification National Identity Card</span></span> 
- <span data-ttu-id="4fb60-157">DNI</span><span class="sxs-lookup"><span data-stu-id="4fb60-157">DNI</span></span> 
- <span data-ttu-id="4fb60-158">NIC National Registry of Persons</span><span class="sxs-lookup"><span data-stu-id="4fb60-158">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="4fb60-159">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="4fb60-159">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="4fb60-160">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="4fb60-160">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="4fb60-161">Identidad</span><span class="sxs-lookup"><span data-stu-id="4fb60-161">Identidad</span></span> 
- <span data-ttu-id="4fb60-162">Identificación</span><span class="sxs-lookup"><span data-stu-id="4fb60-162">Identificación</span></span> 

### <a name="more-on-confidence-levels"></a><span data-ttu-id="4fb60-163">신뢰 수준에 대한 추가</span><span class="sxs-lookup"><span data-stu-id="4fb60-163">More on confidence levels</span></span>

<span data-ttu-id="4fb60-164">중요한 정보 유형 엔터티 정의에서 **신뢰** 수준은 기본 요소 외에 검색되는 증거의 수를 반영합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-164">In a sensitive information type entity definition, **confidence level** reflects how much supporting evidence is detected in addition to the primary element.</span></span> <span data-ttu-id="4fb60-165">항목에 포함된 증거가 수록 일치하는 항목에 찾고 있는 중요한 정보가 포함되어 있다는 신뢰도가 높아지기 때문에</span><span class="sxs-lookup"><span data-stu-id="4fb60-165">The more supporting evidence an item contains, the higher the confidence that a matched item contains the sensitive info you're looking for.</span></span> <span data-ttu-id="4fb60-166">예를 들어 신뢰 수준이 높은 일치는 기본 요소와 근접한 더 많은 증거를 포함하나 신뢰 수준이 낮은 일치는 근접한 증거를 거의 또는 거의 포함하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-166">For example, matches with a high confidence level will contain more supporting evidence in close proximity of the primary element, whereas matches with a low confidence level would contain little to no supporting evidence in close proximity.</span></span> 

<span data-ttu-id="4fb60-167">신뢰도 수준이 높을수록 가음성은 가장 적지만 가음성은 더 많이 반환될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-167">A high confidence level returns the fewest false positives but might result in more false negatives.</span></span> <span data-ttu-id="4fb60-168">신뢰 수준이 낮거나 보통이면 가음성은 더 많이 반환하지만 가음성 수준은 0에서 0까지입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-168">Low or medium confidence levels returns more false positives but few to zero false negatives.</span></span>

- <span data-ttu-id="4fb60-169">**낮은 신뢰도:** 값 65, 일치 항목은 가음성은 가장 적지만 오음성은 가장 적습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-169">**low confidence**: Value of 65, matched items will contain the fewest false negatives but the most false positives.</span></span> <span data-ttu-id="4fb60-170">낮은 신뢰도는 낮은 신뢰도, 보통 및 높은 신뢰도 일치를 모두 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-170">Low confidence returns all low, medium, and high confidence matches.</span></span>
- <span data-ttu-id="4fb60-171">**중간 신뢰도**: 값 75, 일치 항목은 평균 가짓 긍정 양과 거짓 부정을 포함하게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-171">**medium confidence**: Value of 75, matched items will contain an average amount of false positives and false negatives.</span></span> <span data-ttu-id="4fb60-172">보통 신뢰도는 모든 중간 신뢰도 및 높은 신뢰도 일치를 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-172">Medium confidence returns all medium, and high confidence matches.</span></span>  
- <span data-ttu-id="4fb60-173">**높은 신뢰도:** 값이 85이면 일치하는 항목은 가음성은 가장 적지만 거짓 부정은 가장 적습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-173">**high confidence**: Value of 85, matched items will contain the fewest false positives but the most false negatives.</span></span> <span data-ttu-id="4fb60-174">높은 신뢰도는 높은 일치만 반환합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-174">High confidence only returns high confidence matches.</span></span>  

<span data-ttu-id="4fb60-175">신뢰도 패턴은 낮은 수로, 5~10개, 신뢰도가 높은 패턴은 20개 이상을 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="4fb60-175">You should use high confidence level patterns with low counts, say five to ten, and low confidence patterns with higher counts, say 20 or more.</span></span>

> [!NOTE]
> <span data-ttu-id="4fb60-176">숫자 기반 신뢰 수준(정확도로도 아는)을 사용하여 정의된 기존 정책 또는 사용자 지정 중요한 정보 유형(SITS)이 있는 경우 이러한 정책은 자동으로 3개의 불연산 신뢰 수준에 매핑됩니다. 보안 @ 준수 센터 UI 전반에서 신뢰도, 중간 신뢰도 및 높은 신뢰도</span><span class="sxs-lookup"><span data-stu-id="4fb60-176">If you have existing policies or custom sensitive information types (SITs) defined using number-based confidence levels (also know as accuracy), they will automatically be mapped to the three discrete confidence levels; low confidence, medium confidence, and high confidence, across the Security @ Compliance Center UI.</span></span>
> - <span data-ttu-id="4fb60-177">신뢰 수준이 76에서 100 사이인 최소 정확도 또는 사용자 지정 SIT 패턴이 있는 모든 정책은 높은 신뢰도로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-177">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 76 and 100 will be mapped to high confidence.</span></span> 
> - <span data-ttu-id="4fb60-178">신뢰 수준이 66에서 75 사이인 최소 정확도 또는 사용자 지정 SIT 패턴이 있는 모든 정책은 중간 신뢰도로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-178">All policies with minimum accuracy or custom SIT patterns with confidence levels of between 66 and 75 will be mapped to medium confidence.</span></span>
> - <span data-ttu-id="4fb60-179">신뢰 수준이 65 이하인 최소 정확도 또는 사용자 지정 SIT 패턴이 있는 모든 정책은 낮은 신뢰도로 매핑됩니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-179">All policies with minimum accuracy or custom SIT patterns with confidence levels less than or equal to 65 will be mapped to low confidence.</span></span> 

## <a name="creating-custom-sensitive-information-types"></a><span data-ttu-id="4fb60-180">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="4fb60-180">Creating custom sensitive information types</span></span>

<span data-ttu-id="4fb60-181">보안 및 준수 센터에서 사용자 지정 중요한 정보 유형을 만들려면 몇 가지 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-181">To create custom sensitive information types in the Security & Compliance Center, you can choose from several options:</span></span>

- <span data-ttu-id="4fb60-182">**UI 사용** 보안 및 준수 센터 UI를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니나.</span><span class="sxs-lookup"><span data-stu-id="4fb60-182">**Use the UI** You can set up a custom sensitive information type using the Security & Compliance Center UI.</span></span> <span data-ttu-id="4fb60-183">이 방법을 사용하면 정규식, 키워드 및 키워드 사전을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-183">With this method, you can use regular expressions, keywords, and keyword dictionaries.</span></span> <span data-ttu-id="4fb60-184">자세한 내용은 [사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type.md)을 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb60-184">To learn more, see [Create a custom sensitive information type](create-a-custom-sensitive-information-type.md).</span></span>

- <span data-ttu-id="4fb60-185">**EDM 사용** EDM(정확한 데이터 일치) 기반 분류를 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-185">**Use EDM** You can set up custom sensitive information types using Exact Data Match (EDM)-based classification.</span></span> <span data-ttu-id="4fb60-186">이 방법을 사용하면 주기적으로 새로 고칠 수 있는 보안 데이터베이스를 사용하여 동적인 중요한 정보 유형을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-186">This method enables you to create a dynamic sensitive information type using a secure database that you can refresh periodically.</span></span> <span data-ttu-id="4fb60-187">[분류에 기반한 정확한 데이터 매치를 사용한 사용자 지정 중요한 정보 유형 만들기](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb60-187">See [Create a custom sensitive information type with Exact Data Match based classification](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md).</span></span>

- <span data-ttu-id="4fb60-188">**PowerShell을 사용** PowerShell을 사용하여 사용자 지정 중요한 정보 유형을 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-188">**Use PowerShell** You can set up custom sensitive information types using PowerShell.</span></span> <span data-ttu-id="4fb60-189">이 방법은 UI를 사용하는 것보다 복잡하지만 더 다양한 구성 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-189">Although this method is more complex than using the UI, you have more configuration options.</span></span> <span data-ttu-id="4fb60-190">[보안 및 준수 센터 PowerShell에서 사용자 지정 중요한 정보 유형 만들기](create-a-custom-sensitive-information-type-in-scc-powershell.md)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb60-190">See [Create a custom sensitive information type in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md).</span></span>



> [!NOTE]
> <span data-ttu-id="4fb60-191">향상된 신뢰도 수준은 Microsoft 365 서비스에 대한 데이터 손실 방지, Microsoft Information Protection 서비스, 통신 준수Microsoft Information Protection 정보 거버넌스 및 레코드 관리에 Microsoft 365 즉시 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-191">Improved confidence levels are available for immediate use within Data Loss Prevention for Microsoft 365 services, Microsoft Information Protection for Microsoft 365 services, Communication Compliance, Information Governance, and Records Management.</span></span>
> <span data-ttu-id="4fb60-192">Microsoft 365 정보 보호는 이제 다음에 대한 더블 문자 집합 언어를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-192">Microsoft 365 Information Protection now  supports double byte character set languages for:</span></span>
> - <span data-ttu-id="4fb60-193">중국어(간체)</span><span class="sxs-lookup"><span data-stu-id="4fb60-193">Chinese (simplified)</span></span>
> - <span data-ttu-id="4fb60-194">중국어(번체)</span><span class="sxs-lookup"><span data-stu-id="4fb60-194">Chinese (traditional)</span></span>
> - <span data-ttu-id="4fb60-195">한국어</span><span class="sxs-lookup"><span data-stu-id="4fb60-195">Korean</span></span>
> - <span data-ttu-id="4fb60-196">일본어</span><span class="sxs-lookup"><span data-stu-id="4fb60-196">Japanese</span></span>
> 
> <span data-ttu-id="4fb60-197">이 지원은 중요한 정보 유형에 대해 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-197">This support is available for sensitive information types.</span></span> <span data-ttu-id="4fb60-198">자세한 정보는 [더블 바이트 문자 집합 릴리스 정보(미리 보기)에 대한 정보 보호 지원](mip-dbcs-relnotes.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="4fb60-198">See, [Information protection support for double byte character sets release notes (preview)](mip-dbcs-relnotes.md) for more information.</span></span>

> [!TIP]
> <span data-ttu-id="4fb60-199">중국어/일본어 문자와 단일 바이트 문자가 포함된 패턴을 검색하거나 중국어/일본어 및 영어가 포함된 패턴을 검색하려면 키워드 또는 regex의 두 가지 변형을 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-199">To detect patterns containing Chinese/Japanese characters and single byte characters or to detect patterns containing Chinese/Japanese and English, define two variants of the keyword or regex.</span></span>
> 
> <span data-ttu-id="4fb60-200">예를 들어 "机密的document"와 같은 키워드를 검색하려면 해당 키워드의 두 변형을 사용합니다. 일본어와 영어 텍스트 사이에 공백이 있고 일본어 텍스트와 영어 텍스트 사이에 공백이 없는 다른 텍스트가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-200">For example, to detect a keyword like "机密的document", use two variants of the keyword; one with a space between the Japanese and English text and another without a space between the Japanese and English text.</span></span> <span data-ttu-id="4fb60-201">따라서 SIT에 추가할 키워드는 "机密的 document" 및 "机密的document"여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-201">So, the keywords to be added in the SIT should be "机密的 document" and "机密的document".</span></span> <span data-ttu-id="4fb60-202">마찬가지로 "東京オリンピック2020"라는 구를 검색하려면 두 가지 변형("東京オリンピック 2020" 및 "東京オリンピック2020")을 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-202">Similarly, to detect a phrase "東京オリンピック2020", two variants should be used; "東京オリンピック 2020" and "東京オリンピック2020".</span></span>
> 
> <span data-ttu-id="4fb60-p118">더블 바이트 하이픈 또는 더블 바이트 마침표로 regex를 만드는 동안 regex에서 하이픈이나 마침표가 이스케이프되는 것처럼 두 문자를 모두 이스케이프해야 합니다. 다음은 참조용 샘플 regex입니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-p118">While creating a regex using a double byte hyphen or a double byte period, make sure to escape both the characters like one would escape a hyphen or period in a regex. Here is a sample regex for reference:</span></span>
>    - <span data-ttu-id="4fb60-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span><span class="sxs-lookup"><span data-stu-id="4fb60-205">(?<!\d)([４][０-９]{3}[\-?\－\t]\*[０-９]{4}</span></span>
>
> <span data-ttu-id="4fb60-206">키워드 목록에서 단어 일치 대신 문자열 일치를 사용하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="4fb60-206">We recommend using string match instead of word match in a keyword list.</span></span>

## <a name="for-further-information"></a><span data-ttu-id="4fb60-207">자세한 내용은</span><span class="sxs-lookup"><span data-stu-id="4fb60-207">For further information</span></span>
- [<span data-ttu-id="4fb60-208">중요한 정보 유형 엔터티 정의</span><span class="sxs-lookup"><span data-stu-id="4fb60-208">Sensitive information type entity definitions</span></span>](sensitive-information-type-entity-definitions.md)
- [<span data-ttu-id="4fb60-209">사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="4fb60-209">Create a custom sensitive information type</span></span>](create-a-custom-sensitive-information-type.md)
- [<span data-ttu-id="4fb60-210">PowerShell에서 사용자 지정 중요한 정보 유형 만들기</span><span class="sxs-lookup"><span data-stu-id="4fb60-210">Create a custom sensitive information type in PowerShell</span></span>](create-a-custom-sensitive-information-type-in-scc-powershell.md)

<span data-ttu-id="4fb60-211">중요한 정보 유형을 사용하여 데이터 개인 정보 보호 규정을 준수하는 방법에 대한 자세한 내용은 [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md) (aka.ms/m365dataprivacy)를 참조하십시오.</span><span class="sxs-lookup"><span data-stu-id="4fb60-211">To learn how to use sensitive information types to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>

<!-- fwlink for this topic https://go.microsoft.com/fwlink/?linkid=2135644-->
