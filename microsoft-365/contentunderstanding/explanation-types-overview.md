---
title: 설명 유형
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection: enabler-strategic
localization_priority: Priority
description: Microsoft SharePoint Syntex에서 설명 유형에 대해 자세히 알아보세요.
ms.openlocfilehash: f01529199bf4dea0a14c7dc30b39fcaa5078931b
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087646"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="8d991-103">설명 유형 소개</span><span class="sxs-lookup"><span data-stu-id="8d991-103">Introduction to explanation types</span></span>

<span data-ttu-id="8d991-p101">설명은 Microsoft SharePoint Syntex의 모델을 이해하는 문서에서 레이블을 지정하고 추출할 정보를 정의하는 데 도움이 됩니다. 설명을 작성할 때 설명 유형을 선택해야 합니다. 이 문서는 다양한 설명 유형과 사용 방법을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p101">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex. When creating an explanation, you need to select an explanation type. This article helps you understand the different explanation types and how they are used.</span></span> 

   ![설명 유형](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="8d991-108">다음과 같은 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-108">These explanation types are available:</span></span>

- <span data-ttu-id="8d991-p102">**구문 목록**: 추출하는 문서 또는 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자의 목록입니다. 예를 들어, 텍스트 문자열 **참조 의사** 는 식별 중인 모든 의료 참조 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p102">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting. For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="8d991-p103">**패턴 목록**: 추출하는 정보를 식별하는 데 사용할 수 있는 숫자, 문자 또는 기타 문자의 패턴을 나열합니다. 예를 들어, 식별 중인 모든 의료 참조 문서에서 참조 의사의 **전화 번호** 를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p103">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting. For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="8d991-p104">**근접**: 서로에 대한 설명이 얼마나 가까운지 설명합니다. 예를 들어, *번지 번호* 패턴 목록은 *번지 이름* 구 목록 바로 앞에 있으며, 그 사이에 토큰이 없습니다(이 문서의 뒷부분에서 토큰에 대해 배우게 됩니다). 근접 유형을 사용하려면 모델에서 두 개 이상의 설명이 있어야 합니다. 그렇지 않으면 옵션이 비활성화됩니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p104">**Proximity**: Describes how close explanations are to each other. For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article). Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="8d991-116">구 목록</span><span class="sxs-lookup"><span data-stu-id="8d991-116">Phrase list</span></span>

<span data-ttu-id="8d991-p105">구문 목록 설명 유형은 일반적으로 모델을 통해 문서를 식별하고 분류하는 데 사용됩니다. *참조 의사* 라벨 예에서 설명한 대로, 식별하는 문서에서 일관되게 단어, 구, 숫자 또는 문자의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p105">A phrase list explanation type is typically used to identify and classify a document through your model. As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="8d991-p106">캡처 중인 구문이 문서의 일관된 위치에 있는 경우 설명을 통해 더 나은 성공을 거둘 수 있습니다. 예를 들어, *참조 의사* 라벨은 문서의 첫 번째 단락에 일관되게 위치할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p106">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document. For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="8d991-121">레이블을 식별하는데 대/소문자 구분이 필요하다면, 구 목록 유형을 사용하하면 **정확한 대소문자 사용** 체크박스를 선택하여 이를 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![대/소문자 구분](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="8d991-123">패턴 목록</span><span class="sxs-lookup"><span data-stu-id="8d991-123">Pattern lists</span></span>

<span data-ttu-id="8d991-p107">패턴 목록 유형은 문서를 식별하고 문서에서 정보를 추출하는 설명을 작성할 때 특히 유용합니다. 일반적으로 날짜, 전화 번호 및 신용카드 번호와 같은 다양한 형식으로 표시됩니다. 예를 들어, 날짜는 다양한 형식(1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, 2020년 1월 1일 등)으로 표시할 수 있습니다. 패턴 목록을 정의하면 식별 및 추출하려는 데이터의 가능한 변형을 캡처하여 설명을 보다 효율적으로 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p107">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document. It is typically presented in different formats, such as dates, phone numbers, and credit card numbers. For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.). Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="8d991-p108">**전화 번호** 예제의 경우 모델이 식별하는 모든 의료 참조 문서에서 각 참조 의사의 전화 번호를 추출합니다. 설명을 만들 때 패턴 목록 유형을 선택하여 반환될 것으로 예상되는 다양한 형식을 허용합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p108">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies. When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![전화 번호 패턴 목록](../media/content-understanding/pattern-list.png)

<span data-ttu-id="8d991-131">이 예에서는 **0-9 사이의 임의의 수** 확인란을 선택하여 패턴 목록에 사용된 각 "0" 값을 0부터 9까지의 숫자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0부터 9 사이 아무 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="8d991-133">마찬가지로 텍스트 문자를 포함하는 패턴 목록을 만들 경우 **a-z 사이의 임의의 문자** 확인란을 선택하여 패턴 목록에 사용된 각 "a" 문자를 "a"에서 "z"까지의 문자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="8d991-134">예를 들어 **날짜** 패턴 목록을 만들 때 *2020년 1월 1일* 과 같은 날짜 서식이 인식되도록 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="8d991-135">*0000 aaa 0* 과 *0000 aaa 00* 을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="8d991-136">**a부터 z 사이 아무 문자** 를 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![a부터 z 사이 임의의 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="8d991-p109">또한 패턴 목록에 대문자화 요구 사항이 있는 경우 **정확한 대문자화만** 확인란을 선택할 수 있습니다. 날짜 예제의 경우 월의 첫 번째 문자를 대문자로 표시해야 하는 경우 다음이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p109">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox. For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="8d991-140">*0000 Aaa 0* 과 *0000 Aaa 00* 을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="8d991-141">**정확한 대소문자 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![정확한 대소문자 사용](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="8d991-143">패턴 목록 설명을 수동으로 만드는 대신 [설명 라이브러리](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates)를 사용하여 *날짜*, *전화 번호*, *신용카드 번호* 등 일반 패턴 목록의 서식파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-143">Instead of manually creating a pattern list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="8d991-144">근접</span><span class="sxs-lookup"><span data-stu-id="8d991-144">Proximity</span></span> 

<span data-ttu-id="8d991-p110">근접 설명 유형을 사용하면 다른 데이터가 얼마나 가까운지 정의하여 모델을 통해 데이터를 식별할 수 있습니다. 예를 들어 모델에서 고객 *거리 주소 번호* 및 *전화 번호* 모두에 레이블을 지정하는 두 가지 설명을 정의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p110">The proximity explanation type helps your model identify data by defining how close another piece of data is to it. For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="8d991-147">또한 고객 전화 번호는 항상 거리 주소 번호 앞에 표시된다는 것을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="8d991-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="8d991-148">Alex Wilburn</span></span><br>
<span data-ttu-id="8d991-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="8d991-149">555-555-5555</span></span><br>
<span data-ttu-id="8d991-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="8d991-150">One Microsoft Way</span></span><br>
<span data-ttu-id="8d991-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="8d991-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="8d991-152">근접 설명을 사용하여 전화 번호 설명이 문서에서 거리 주소 번호를 식별해내기에 근접하지 않은 설명이라는 것을 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![근접 설명](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="8d991-154">토큰이란?</span><span class="sxs-lookup"><span data-stu-id="8d991-154">What are tokens?</span></span>

<span data-ttu-id="8d991-p111">근사 설명 유형을 사용하려면 근접 설명이 두 개의 설명 간의 거리를 어떻게 측정하는지 토큰의 수로 알 수 있으므로 토큰이 무엇인지를 이해해야 합니다. 토큰은 문자와 숫자의 연속적인 범위(공백이나 구두점은 포함하지 않음)입니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p111">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another. A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="8d991-157">다음 표는 한 개의 구에서 토큰 수를 확인하는 방법에 대해 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="8d991-158">구</span><span class="sxs-lookup"><span data-stu-id="8d991-158">Phrase</span></span>|<span data-ttu-id="8d991-159">토큰 수</span><span class="sxs-lookup"><span data-stu-id="8d991-159">Number of tokens</span></span>|<span data-ttu-id="8d991-160">설명</span><span class="sxs-lookup"><span data-stu-id="8d991-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="8d991-161">1</span><span class="sxs-lookup"><span data-stu-id="8d991-161">1</span></span>|<span data-ttu-id="8d991-162">문장 부호나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="8d991-163">1</span><span class="sxs-lookup"><span data-stu-id="8d991-163">1</span></span>|<span data-ttu-id="8d991-p112">레코드 로케이터 번호입니다. 숫자 및 문자를 포함할 수 있지만 구두점이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p112">A record locator number. It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="8d991-166">5</span><span class="sxs-lookup"><span data-stu-id="8d991-166">5</span></span>|<span data-ttu-id="8d991-p113">전화 번호입니다. 각 문장 부호는 단일 토큰이므로 `425-555-5555`은(는) 5개의 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p113">A phone number. Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="8d991-169">7</span><span class="sxs-lookup"><span data-stu-id="8d991-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="8d991-170">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="8d991-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="8d991-p114">예를 들어 *거리 주소 번호* 설명에서 *전화 번호* 설명에 있는 토큰 수 범위를 정의하도록 근접 설정을 구성합니다. 전화 번호와 거리 주소 번호 사이에는 토큰이 없으므로 최소 범위는 "0"입니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p114">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation. Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="8d991-173">그러나 샘플 문서의 일부 전화 번호에는 *(휴대폰)* 이 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="8d991-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="8d991-174">Nestor Wilke</span></span><br>
<span data-ttu-id="8d991-175">111-111-1111(휴대폰)</span><span class="sxs-lookup"><span data-stu-id="8d991-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="8d991-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="8d991-176">One Microsoft Way</span></span><br>
<span data-ttu-id="8d991-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="8d991-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="8d991-178">*(휴대폰)* 에는 세 개의 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="8d991-179">구</span><span class="sxs-lookup"><span data-stu-id="8d991-179">Phrase</span></span>|<span data-ttu-id="8d991-180">토큰 수</span><span class="sxs-lookup"><span data-stu-id="8d991-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="8d991-181">(</span><span class="sxs-lookup"><span data-stu-id="8d991-181">(</span></span>|<span data-ttu-id="8d991-182">1</span><span class="sxs-lookup"><span data-stu-id="8d991-182">1</span></span>|
|<span data-ttu-id="8d991-183">휴대폰</span><span class="sxs-lookup"><span data-stu-id="8d991-183">mobile</span></span>|<span data-ttu-id="8d991-184">2</span><span class="sxs-lookup"><span data-stu-id="8d991-184">2</span></span>|
|<span data-ttu-id="8d991-185">)</span><span class="sxs-lookup"><span data-stu-id="8d991-185">)</span></span>|<span data-ttu-id="8d991-186">3</span><span class="sxs-lookup"><span data-stu-id="8d991-186">3</span></span>|

<span data-ttu-id="8d991-187">근접 설정이 0에서 3의 범위를 갖도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![근접의 예](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="8d991-189">설명 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="8d991-189">Use explanation templates</span></span>

<span data-ttu-id="8d991-190">설명에 대한 다양한 패턴 목록 값을 수동으로 추가할 수 있지만, 설명 라이브러리에서 미리 작성된 서식 파일을 찾아 사용하는 것이 훨씬 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-190">While you can manually add various pattern list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="8d991-191">예를 들어 *날짜* 에 대한 모든 변형을 수동으로 추가하는 대신 이미 여러 패턴 목록 값을 포함하고 있는 *날짜* 패턴 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-191">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date* as it already includes a number of pattern lists values:</span></span></br>

   ![설명 라이브러리](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="8d991-193">설명 라이브러리에는 다음을 비롯하여 일반적으로 사용되는 몇 가지 패턴 목록 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-193">The explanation library includes commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="8d991-194">날짜</span><span class="sxs-lookup"><span data-stu-id="8d991-194">Date</span></span></br>
- <span data-ttu-id="8d991-195">날짜(숫자)</span><span class="sxs-lookup"><span data-stu-id="8d991-195">Date (numeric)</span></span></br>
- <span data-ttu-id="8d991-196">시간</span><span class="sxs-lookup"><span data-stu-id="8d991-196">Time</span></span></br>
- <span data-ttu-id="8d991-197">숫자</span><span class="sxs-lookup"><span data-stu-id="8d991-197">Number</span></span></br>
- <span data-ttu-id="8d991-198">전화 번호</span><span class="sxs-lookup"><span data-stu-id="8d991-198">Phone number</span></span></br>
- <span data-ttu-id="8d991-199">우편 번호</span><span class="sxs-lookup"><span data-stu-id="8d991-199">Zip code</span></span></br>
- <span data-ttu-id="8d991-200">문장의 첫 번째 단어</span><span class="sxs-lookup"><span data-stu-id="8d991-200">First word of sentence</span></span></br>
- <span data-ttu-id="8d991-201">신용카드</span><span class="sxs-lookup"><span data-stu-id="8d991-201">Credit card</span></span></br>
- <span data-ttu-id="8d991-202">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="8d991-202">Social security number</span></span></br>

<span data-ttu-id="8d991-203">또한 설명 라이브러리에는 다음을 포함한 구 목록 설명의 서식 파일도 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-203">Note that the explanation library also includes templates for phrase list explanations:</span></span>
- <span data-ttu-id="8d991-204">문장의 끝</span><span class="sxs-lookup"><span data-stu-id="8d991-204">End of sentence</span></span>
- <span data-ttu-id="8d991-205">통화</span><span class="sxs-lookup"><span data-stu-id="8d991-205">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="8d991-206">설명 라이브러리에서 서식 파일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8d991-206">To use a template from the explanation library</span></span>

1. <span data-ttu-id="8d991-207">모델의 **교육** 페이지의 **설명** 구역에서 **신규** 를 선택한 다음 **서식 파일 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-207">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![서식 파일로 만들기](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="8d991-209">**설명 서식 파일** 페이지에서 사용하려는 설명을 선택하고 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-209">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![서식 파일 선택](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="8d991-p115">선택한 템플릿에 대한 정보가 **설명 만들기** 페이지에 표시됩니다. 필요한 경우 설명 이름을 편집하고 패턴 목록에서 항목을 추가하거나 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-p115">The information for the template you selected displays on the **Create an explanation** page. If needed, edit the explanation name and add or remove items from the pattern list. </span></span></br> 

   ![서식 파일 편집](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="8d991-214">작업을 끝낸 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8d991-214">When finished, select **Save**.</span></span>
