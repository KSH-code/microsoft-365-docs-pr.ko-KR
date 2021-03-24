---
title: 설명 유형
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex에서 설명 유형에 대해 자세히 알아보세요.
ms.openlocfilehash: b34de9ffc565e3d1a17cac05084e4e4b4113a3c6
ms.sourcegitcommit: 3d3c446d5e2e90369be1339dd0a33e71432fbc36
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/22/2021
ms.locfileid: "50994631"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="8cb5a-103">설명 유형 소개</span><span class="sxs-lookup"><span data-stu-id="8cb5a-103">Introduction to explanation types</span></span>

<span data-ttu-id="8cb5a-104">설명은 Microsoft SharePoint Syntex의 모델에 대한 이해를 바탕으로 문서에 표시하고 추출하고자 하는 정보를 정의하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="8cb5a-105">설명을 만들 때는 설명 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="8cb5a-106">이 문서는 다양한 설명 유형과 사용 방법을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-106">This article helps you understand the different explanation types and how they are used.</span></span> 

   ![설명 유형](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="8cb5a-108">다음과 같은 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-108">These explanation types are available:</span></span>

- <span data-ttu-id="8cb5a-109">**구 목록**: 추출하려는 문서나 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="8cb5a-110">예를 들어 **의사 추천** 이란 텍스트 문자열은 파악할 수 있는 모든 의료 리퍼럴 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="8cb5a-111">**패턴 목록**: 추출하려는 정보를 식별하는 데 사용되는 숫자, 문자 또는 기타 문자의 패턴 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="8cb5a-112">예를 들어 식별되는 모든 의학 조회 문서에서 **전화 번호** 를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="8cb5a-113">**근접**: 각각의 설명이 서로 얼마나 근접한지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="8cb5a-114">예를 들어 *번지 수* 의 패턴 목록은 *길 이름* 바로 전에 나오고 토큰은 둘 사이에 존재하지 않습니다.(토큰에 대한 자세한 정보는 본 문서의 뒷부분에 나옵니다.)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="8cb5a-115">근사 유형을 사용하려면 모델에 두 개 이상의 설명이 있어야 하고, 그렇지 않으면 해당 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-115">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="8cb5a-116">구 목록</span><span class="sxs-lookup"><span data-stu-id="8cb5a-116">Phrase list</span></span>

<span data-ttu-id="8cb5a-117">일반적으로 구 목록 설명 형식은 모델을 통해 문서를 식별하고 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="8cb5a-118">*의사 추천* 레이블 예제에 설명된 바와 같이, 확인 중인 문서에서 일관되게 나타나는 일련의 단어, 구, 숫자 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="8cb5a-119">요구 사항은 아니지만, 캡처링하는 구가 문서의 일관된 위치에 있는 경우 설명의 성공을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-119">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="8cb5a-120">예를 들어, *의사 추천* 이란 레이블이 문서의 첫 번째 문단에 일관되게 배치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="8cb5a-121">레이블을 식별하는데 대/소문자 구분이 필요하다면, 구 목록 유형을 사용하하면 **정확한 대소문자 사용** 체크박스를 선택하여 이를 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![대/소문자 구분](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="8cb5a-123">패턴 목록</span><span class="sxs-lookup"><span data-stu-id="8cb5a-123">Pattern lists</span></span>

<span data-ttu-id="8cb5a-124">패턴 목록 유형은 문서에서 정보를 식별하고 추출하는 설명을 만드는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="8cb5a-125">일반적으로 날짜, 전화 번호, 신용카드 번호와 같은 다양한 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-125">It is typically presented in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="8cb5a-126">예를 들어 날짜의 경우 다양한 형식(2020/1/1, 2020-1-1, 20/01/01, 2020/01/01, 2020년 1월 1일 등)으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="8cb5a-127">패턴 목록을 정의하면 식별하고 추출하려는 데이터의 가능한 모든 변형을 캡처하여 더 효율적으로 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="8cb5a-128">**전화 번호** 샘플의 경우, 모델이 식별하는 모든 의학 조회 문서에서 각각 추천하는 의사의 전화 번호를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-128">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="8cb5a-129">설명을 만들 때 패턴 목록 유형을 선택하면 돌아올 수 있는 다양한 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![전화 번호 패턴 목록](../media/content-understanding/pattern-list.png)

<span data-ttu-id="8cb5a-131">이 예에서는 **0-9 사이의 임의의 수** 확인란을 선택하여 패턴 목록에 사용된 각 "0" 값을 0부터 9까지의 숫자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-131">For this example, select the **Any digit from 0-9** checkbox to recognize each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0부터 9 사이 아무 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="8cb5a-133">마찬가지로 텍스트 문자를 포함하는 패턴 목록을 만들 경우 **a-z 사이의 임의의 문자** 확인란을 선택하여 패턴 목록에 사용된 각 "a" 문자를 "a"에서 "z"까지의 문자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="8cb5a-134">예를 들어 **날짜** 패턴 목록을 만들 때 *2020년 1월 1일* 과 같은 날짜 서식이 인식되도록 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-134">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="8cb5a-135">*0000 aaa 0* 과 *0000 aaa 00* 을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="8cb5a-136">**a부터 z 사이 아무 문자** 를 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-136">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![a부터 z 사이 아무 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="8cb5a-138">또한 패턴 목록에 대문자화 요구 사항이 있는 경우에는 **정확한 대소문자 사용** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-138">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="8cb5a-139">날짜 예제의 경우 달의 첫 글자를 대문자로 표기하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-139">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="8cb5a-140">*0000 Aaa 0* 과 *0000 Aaa 00* 을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="8cb5a-141">**정확한 대소문자 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-141">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![정확한 대소문자 사용](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="8cb5a-143">패턴 목록 설명을 수동으로 만드는 대신 [설명 라이브러리](#use-explanation-templates)를 사용하여 *날짜*, *전화 번호*, *신용카드 번호* 등 일반 패턴 목록의 서식파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-143">Instead of manually creating a pattern list explanation, use the [explanation library](#use-explanation-templates) to use pattern list templates for a common pattern list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="8cb5a-144">근접</span><span class="sxs-lookup"><span data-stu-id="8cb5a-144">Proximity</span></span> 

<span data-ttu-id="8cb5a-145">근접 설명 유형은 사용자의 모델이 각각의 데이터가 서로 얼마나 근접해 있는지를 규정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-145">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="8cb5a-146">예를 들어 모델에서 고객의 *거리 주소 번호* 와 *전화 번호* 를 둘 다 표시하는 두 개의 설명을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-146">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="8cb5a-147">또한 고객 전화 번호는 항상 거리 주소 번호 앞에 표시된다는 것을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-147">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="8cb5a-148">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="8cb5a-148">Alex Wilburn</span></span><br>
<span data-ttu-id="8cb5a-149">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="8cb5a-149">555-555-5555</span></span><br>
<span data-ttu-id="8cb5a-150">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="8cb5a-150">One Microsoft Way</span></span><br>
<span data-ttu-id="8cb5a-151">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="8cb5a-151">Redmond, WA 98034</span></span><br>

<span data-ttu-id="8cb5a-152">근접 설명을 사용하여 전화 번호 설명이 문서에서 거리 주소 번호를 식별해내기에 근접하지 않은 설명이라는 것을 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-152">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![근접 설명](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="8cb5a-154">토큰이란?</span><span class="sxs-lookup"><span data-stu-id="8cb5a-154">What are tokens?</span></span>

<span data-ttu-id="8cb5a-155">근사 설명 유형을 사용하려면 근접 설명이 두 개의 설명 간의 거리를 어떻게 측정하는지 토큰의 수로 알 수 있으므로 토큰이 무엇인지를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-155">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="8cb5a-156">토큰은 문자와 숫자의 연속 범위(공백이나 문장 부호 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-156">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="8cb5a-157">다음 표는 한 개의 구에서 토큰 수를 확인하는 방법에 대해 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-157">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="8cb5a-158">구</span><span class="sxs-lookup"><span data-stu-id="8cb5a-158">Phrase</span></span>|<span data-ttu-id="8cb5a-159">토큰 수</span><span class="sxs-lookup"><span data-stu-id="8cb5a-159">Number of tokens</span></span>|<span data-ttu-id="8cb5a-160">설명</span><span class="sxs-lookup"><span data-stu-id="8cb5a-160">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="8cb5a-161">1</span><span class="sxs-lookup"><span data-stu-id="8cb5a-161">1</span></span>|<span data-ttu-id="8cb5a-162">문장 부호나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-162">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="8cb5a-163">1</span><span class="sxs-lookup"><span data-stu-id="8cb5a-163">1</span></span>|<span data-ttu-id="8cb5a-164">레코드 로케이터 번호</span><span class="sxs-lookup"><span data-stu-id="8cb5a-164">A record locator number.</span></span> <span data-ttu-id="8cb5a-165">숫자와 문자가 포함될 수 있지만 문장 부호는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-165">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="8cb5a-166">5</span><span class="sxs-lookup"><span data-stu-id="8cb5a-166">5</span></span>|<span data-ttu-id="8cb5a-167">전화 번호</span><span class="sxs-lookup"><span data-stu-id="8cb5a-167">A phone number.</span></span> <span data-ttu-id="8cb5a-168">각 문장 부호 기호는 단일 토큰이므로 `425-555-5555`의 경우 5개의 토큰이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-168">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="8cb5a-169">7</span><span class="sxs-lookup"><span data-stu-id="8cb5a-169">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="8cb5a-170">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="8cb5a-170">Configure the proximity explanation type</span></span>

<span data-ttu-id="8cb5a-171">샘플에 대한 근접 설정을 구성하여 *거리 주소 번호* 설명으로부터 *전화 번호* 설명의 토큰 수 범위를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-171">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="8cb5a-172">전화 번호와 거리 주소 번호 사이에는 토큰이 없기 때문에 최소 범위는 "0" 이라는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-172">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="8cb5a-173">그러나 샘플 문서의 일부 전화 번호에는 *(휴대폰)* 이 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-173">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="8cb5a-174">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="8cb5a-174">Nestor Wilke</span></span><br>
<span data-ttu-id="8cb5a-175">111-111-1111(휴대폰)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-175">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="8cb5a-176">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="8cb5a-176">One Microsoft Way</span></span><br>
<span data-ttu-id="8cb5a-177">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="8cb5a-177">Redmond, WA 98034</span></span><br>

<span data-ttu-id="8cb5a-178">*(휴대폰)* 에는 세 개의 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-178">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="8cb5a-179">구</span><span class="sxs-lookup"><span data-stu-id="8cb5a-179">Phrase</span></span>|<span data-ttu-id="8cb5a-180">토큰 수</span><span class="sxs-lookup"><span data-stu-id="8cb5a-180">Token count</span></span>|
|--|--|
|<span data-ttu-id="8cb5a-181">(</span><span class="sxs-lookup"><span data-stu-id="8cb5a-181">(</span></span>|<span data-ttu-id="8cb5a-182">1</span><span class="sxs-lookup"><span data-stu-id="8cb5a-182">1</span></span>|
|<span data-ttu-id="8cb5a-183">휴대폰</span><span class="sxs-lookup"><span data-stu-id="8cb5a-183">mobile</span></span>|<span data-ttu-id="8cb5a-184">2</span><span class="sxs-lookup"><span data-stu-id="8cb5a-184">2</span></span>|
|<span data-ttu-id="8cb5a-185">)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-185">)</span></span>|<span data-ttu-id="8cb5a-186">3</span><span class="sxs-lookup"><span data-stu-id="8cb5a-186">3</span></span>|

<span data-ttu-id="8cb5a-187">근접 설정이 0에서 3의 범위를 갖도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-187">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![근접의 예](../media/content-understanding/proximity-example.png)</br>


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="8cb5a-189">문서에서 구가 발생하는 위치 구성</span><span class="sxs-lookup"><span data-stu-id="8cb5a-189">Configure where phrases occur in the document</span></span>

<span data-ttu-id="8cb5a-190">설명을 만들 때 기본적으로 전체 문서에서 추출하려는 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-190">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="8cb5a-191">그러나 <b>문서에서 이 구가 발생하는 위치</b> 고급 설정을 사용하면 문서에서 이러한 구가 발생하는 위치를 설정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-191">However, you can use the <b>Where these phrases occur</b> advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="8cb5a-192">이 기능은 문서의 다른 위치에서 구와 비슷한 인스턴스가 표시되고 올바른 구가 선택되어 있는지 확인하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-192">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="8cb5a-193">의료 의뢰 문서를 예로 들면 **의사 의뢰** 는 항상 문서의 첫 번째 단락에 언급되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-193">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="8cb5a-194">이 예에서는 <b>이러한 구가 발생하는 위치</b> 설정을 사용하여 문서의 시작 부분 또는 이 구가 발생할 수 있는 다른 위치에서만 이 레이블을 검색하도록 설명을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-194">With the <b>Where these phrases occur</b> setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

   ![이러한 구가 발생하는 위치 설정](../media/content-understanding/phrase-location.png)</br>

<span data-ttu-id="8cb5a-196">이 설정에 대해 다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-196">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="8cb5a-197">파일의 모든 위치: 전체 문서에서 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-197">Anywhere in the file: The entire document is searched for the phrase.</span></span>
- <span data-ttu-id="8cb5a-198">파일의 시작: 문서가 처음부터 구 위치까지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-198">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span></br> 
   <span data-ttu-id="8cb5a-199">![파일의 시작](../media/content-understanding/beginning-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-199">![Beginning of file](../media/content-understanding/beginning-of-file.png)</span></span></br>
<span data-ttu-id="8cb5a-200">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-200">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="8cb5a-201"><b>끝 위치</b> 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-201">The <b>End position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="8cb5a-202">끝 위치 값을 업데이트하여 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-202">Note that you can update the End position value as well to adjust the selected area.</span></span></br>
   <span data-ttu-id="8cb5a-203">![파일 위치 상자의 시작](../media/content-understanding/beginning-box.png)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-203">![Beginning of file position box](../media/content-understanding/beginning-box.png)</span></span></br>

- <span data-ttu-id="8cb5a-204">파일의 끝 위치: 문서가 끝부터 구 위치까지 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-204">End of the file:  The document is searched from the end to the phrase location.</span></span></br> 
   <span data-ttu-id="8cb5a-205">![파일의 끝](../media/content-understanding/end-of-file.png)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-205">![End of file](../media/content-understanding/end-of-file.png)</span></span></br>
<span data-ttu-id="8cb5a-206">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-206">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="8cb5a-207"><b>시작 위치</b> 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-207">The <b>Starting position</b> value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="8cb5a-208">시작 위치 값을 업데이트하여 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-208">Note that you can update the Starting position value as well to adjust the selected area.</span></span></br> 
   <span data-ttu-id="8cb5a-209">![파일 끝 상자의 끝](../media/content-understanding/end-box.png)</span><span class="sxs-lookup"><span data-stu-id="8cb5a-209">![End of file end box](../media/content-understanding/end-box.png)</span></span></br>
- <span data-ttu-id="8cb5a-210">사용자 지정 범위: 문서가 구 위치에 대해 지정된 범위 내에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-210">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span></br> 
   <span data-ttu-id="8cb5a-211">![사용자 지정 범위](../media/content-understanding/custom-file.png).</span><span class="sxs-lookup"><span data-stu-id="8cb5a-211">![Custom range](../media/content-understanding/custom-file.png)</span></span></br>
<span data-ttu-id="8cb5a-212">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-212">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="8cb5a-213">이 설정의 경우 시작 <b>시작</b>과 <b>끝</b> 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-213">For this setting, you need to select a <b>Start</b> and an <b>End</b> position.</span></span> <span data-ttu-id="8cb5a-214">이러한 값은 문서 시작에서 토큰 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-214">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="8cb5a-215">이러한 값은 수동으로 입력할 수 있지만 뷰어에서 선택 상자를 수동으로 조정하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-215">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span></br> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="8cb5a-216">설명 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="8cb5a-216">Use explanation templates</span></span>

<span data-ttu-id="8cb5a-217">설명에 대한 다양한 구 목록 값을 수동으로 추가할 수 있지만, 설명 라이브러리에서 미리 작성된 서식 파일을 찾아 사용하는 것이 훨씬 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-217">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="8cb5a-218">예를 들어 *날짜* 에 대한 모든 변형을 수동으로 추가하는 대신 이미 여러 구 목록 값을 포함하고 있는 *날짜* 구 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-218">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span></br>

   ![설명 라이브러리](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="8cb5a-220">설명 라이브러리에는 다음을 비롯하여 일반적으로 사용되는 몇 가지 구 목록 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-220">The explanation library includes commonly used phrase list explanations, including:</span></span></br>

- <span data-ttu-id="8cb5a-221">날짜: 달력 날짜, 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-221">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="8cb5a-222">텍스트 및 숫자를 포함합니다(예: "2020년 12월 9일").</span><span class="sxs-lookup"><span data-stu-id="8cb5a-222">Includes text and numbers (for example, "Dec 9, 2020").</span></span></br>
- <span data-ttu-id="8cb5a-223">날짜(숫자): 달력 날짜, 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-223">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="8cb5a-224">숫자를 포함합니다(예: 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="8cb5a-224">Includes numbers (for example 1-11-2020).</span></span></br>
- <span data-ttu-id="8cb5a-225">시간: 12시간 및 24시간 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-225">Time: 12 and 24 hour formats.</span></span></br>
- <span data-ttu-id="8cb5a-226">숫자: 소수점 두 개까지 양수와 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-226">Number: Positive and negative numbers up to 2 decimals.</span></span> </br>
- <span data-ttu-id="8cb5a-227">백분율: 백분율을 나타내는 패턴 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-227">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="8cb5a-228">예: 1%, 11%, 100%, 11.11% 등.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-228">For example, 1%, 11%, 100%, 11.11%, etc.</span></span></br>
- <span data-ttu-id="8cb5a-229">전화번호: 일반적인 미국 및 국제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-229">Phone number: Common US and International formats.</span></span> <span data-ttu-id="8cb5a-230">예: 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000 등.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-230">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span></br>
- <span data-ttu-id="8cb5a-231">우편 번호: 미국 우편 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-231">Zip code: US Zip code formats.</span></span> <span data-ttu-id="8cb5a-232">예: 11111, 11111-1111</span><span class="sxs-lookup"><span data-stu-id="8cb5a-232">For example, 11111, 11111-1111.</span></span></br>
- <span data-ttu-id="8cb5a-233">문장의 첫 번째 단어: 최대 9자 단어의 공통 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-233">First word of sentence: Common patterns for words up to 9 characters.</span></span> </br>
- <span data-ttu-id="8cb5a-234">문장의 끝: 문장의 끝용 일반적인 문장 부호</span><span class="sxs-lookup"><span data-stu-id="8cb5a-234">End of sentence: Common punctuation for end of a sentence</span></span></br>
- <span data-ttu-id="8cb5a-235">신용 카드: 일반 신용 카드 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-235">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="8cb5a-236">예: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-236">For example, 1111-1111-1111-1111.</span></span> </br>
- <span data-ttu-id="8cb5a-237">사회보장번호: 미국 사회보장번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-237">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="8cb5a-238">예: 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-238">For example, 111-11-1111.</span></span> </br>
- <span data-ttu-id="8cb5a-239">확인란: 입력된 확인란의 변형을 나타내는 구 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-239">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="8cb5a-240">예: _x_, _ _X_ 등.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-240">For example, _X_, _ _X_, etc.</span></span></br>
- <span data-ttu-id="8cb5a-241">통화: 주요 국제 기호</span><span class="sxs-lookup"><span data-stu-id="8cb5a-241">Currency: Major international symbols.</span></span> <span data-ttu-id="8cb5a-242">예: $.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-242">For example, $.</span></span> </br>
- <span data-ttu-id="8cb5a-243">전자 메일 CC: 'CC:'라는 용어가 있는 구 목록입니다. 대개 메시지가 전송된 추가 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-243">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span></br>
- <span data-ttu-id="8cb5a-244">전자 메일 날짜: '보낸 날짜:'라는 용어가 있는 구 목록입니다. 대개 전자 메일을 보낸 날짜 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-244">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span></br>
- <span data-ttu-id="8cb5a-245">전자 메일 인사말: 전자 메일의 일반적인 첫 문장입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-245">Email greeting: Common opening lines for emails.</span></span></br>
- <span data-ttu-id="8cb5a-246">전자 메일 받는 사람: '받는 사람:'이라는 용어가 있는 구 목록입니다. 대개 메시지가 전송된 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-246">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> </br>
- <span data-ttu-id="8cb5a-247">전자 메일 보낸 사람: '보낸 사람:'이라는 용어가 있는 구 목록입니다. 대개 보낸 사람 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-247">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> </br>
- <span data-ttu-id="8cb5a-248">전자 메일 제목: '제목:'이라는 용어가 있는 구 목록입니다. 대개 전자 메일의 제목 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-248">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> </br>

<span data-ttu-id="8cb5a-249">설명 라이브러리에는 예제 파일에 레이블이 지정되어 있는 데이터를 사용하는 세 가지 자동 서식 파일 유형도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-249">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="8cb5a-250">레이블 뒤: 예제 파일의 레이블 뒤에서 발생하는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-250">After label: The words or characters that occur after the labels in the example files.</span></span></br>
- <span data-ttu-id="8cb5a-251">레이블 전: 예제 파일의 레이블 앞에 있는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-251">Before label: The words or characters that occur before the labels in the example files.</span></span></br>
- <span data-ttu-id="8cb5a-252">레이블: 예제 파일에서 처음 10개 레이블까지입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-252">Labels: Up to the first 10 labels from the example files.</span></span></br>

<span data-ttu-id="8cb5a-253">자동 서식 파일의 작동 방식에 대한 예제를 설명하기 위해 다음 예제 파일에서 레이블 전 설명 서식 파일을 사용하여 모델에 더 많은 정보를 제공하여 보다 정확한 일치를 얻을 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-253">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

   ![예제 파일](../media/content-understanding/before-label.png)</br>

<span data-ttu-id="8cb5a-255">레이블 전 설명 서식 파일을 선택하면 예제 파일의 레이블 앞에 나타나는 첫 번째 단어 집합이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-255">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="8cb5a-256">예를 들어 첫번째 예제 파일에서 식별되는 단어는 “As of”입니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-256">In the example, the words that are identified in the first example file is "As of".</span></span>

   ![레이블 서식 파일 전](../media/content-understanding/before-label-explanation.png)</br>

<span data-ttu-id="8cb5a-258">서식 파일에서 <b>추가</b>를 선택하여 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-258">You can select <b>Add</b> to create an explanation from the template.</span></span>  <span data-ttu-id="8cb5a-259">예제 파일을 더 추가하면 추가 단어가 식별되어 구 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-259">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

   ![레이블 추가](../media/content-understanding/before-label-add.png)</br>
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="8cb5a-261">설명 라이브러리에서 서식 파일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="8cb5a-261">To use a template from the explanation library</span></span>

1. <span data-ttu-id="8cb5a-262">모델의 **교육** 페이지의 **설명** 구역에서 **신규** 를 선택한 다음 **서식 파일 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-262">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![레이블 전에 추가](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="8cb5a-264">**설명 서식 파일** 페이지에서 사용하려는 설명을 선택하고 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-264">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span></br>

       ![서식 파일 선택](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="8cb5a-266">선택한 서식 파일에 대한 정보는 **설명 만들기** 페이지에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-266">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="8cb5a-267">필요한 경우 설명 이름을 편집하고 구 목록에서 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-267">If needed, edit the explanation name and add or remove items from the phrase list.</span></span> </br> 

   ![서식 파일 편집](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="8cb5a-269">작업을 끝낸 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="8cb5a-269">When finished, select **Save**.</span></span>