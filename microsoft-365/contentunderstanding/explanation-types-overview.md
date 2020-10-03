---
title: 설명 유형
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: Microsoft SharePoint Syntex에서 설명 유형에 대해 자세히 알아보세요.
ms.openlocfilehash: 7d78337fd91bc7e5a71bccd4867f019ae663417a
ms.sourcegitcommit: f7ca339bdcad38796c550064fb152ea09687d0f3
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/30/2020
ms.locfileid: "48321800"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="aabb3-103">설명 유형 소개</span><span class="sxs-lookup"><span data-stu-id="aabb3-103">Introduction to explanation types</span></span>

<span data-ttu-id="aabb3-104">설명은 Microsoft SharePoint Syntex의 모델에 대한 이해를 바탕으로 문서에 표시하고 추출하고자 하는 정보를 정의하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="aabb3-105">설명을 만들 때는 설명 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="aabb3-106">이 문서에는 다양한 설명 유형과 각각의 사용 방법을 잘 이해하도록 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-106">This article will help you learn more to better understand the different explanation types and how they are used.</span></span> 

   ![설명 유형](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="aabb3-108">다음과 같은 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-108">These explanation types are available:</span></span>

- <span data-ttu-id="aabb3-109">**구 목록**: 추출하려는 문서나 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="aabb3-110">예를 들어 **의사 추천**이란 텍스트 문자열은 파악할 수 있는 모든 의료 리퍼럴 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="aabb3-111">**패턴 목록**: 추출하려는 정보를 식별하는 데 사용되는 숫자, 문자 또는 기타 문자의 패턴 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="aabb3-112">예를 들어 식별되는 모든 의학 조회 문서에서 **전화 번호**를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="aabb3-113">**근접**: 각각의 설명이 서로 얼마나 근접한지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="aabb3-114">예를 들어 *번지 수*의 패턴 목록은 *길 이름* 바로 전에 나오고 토큰은 둘 사이에 존재하지 않습니다.(토큰에 대한 자세한 정보는 본 문서의 뒷부분에 나옵니다.)</span><span class="sxs-lookup"><span data-stu-id="aabb3-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="aabb3-115">근사 유형을 사용하려면 모델에 두 개 이상의 설명이 있어야 하고, 그렇지 않으면 해당 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-115">Using the proximity type requires you to have at least two explanations in your model, or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="aabb3-116">구 목록</span><span class="sxs-lookup"><span data-stu-id="aabb3-116">Phrase list</span></span>

<span data-ttu-id="aabb3-117">일반적으로 구 목록 설명 형식은 모델을 통해 문서를 식별하고 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-117">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="aabb3-118">*의사 추천* 레이블 예제에 설명 된 바와 같이 식별하는 문서에서 일관되게 나타나는 단어, 구, 숫자 또는 문자의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-118">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="aabb3-119">요구 사항은 아니지만, 캡처링하는 구가 문서의 일관된 위치에 있는 경우 설명의 성공를 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-119">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="aabb3-120">예를 들어 *의사 추천*이란 레이블이 문서의 첫 번째 문단에 일관되 게 배치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-120">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="aabb3-121">레이블을 식별하는데 대/소문자 구분이 필요하다면, 구 목록 유형을 사용하하면 **정확한 대소문자 사용** 체크박스를 선택하여 이를 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![대/소문자 구분](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="aabb3-123">패턴 목록</span><span class="sxs-lookup"><span data-stu-id="aabb3-123">Pattern lists</span></span>

<span data-ttu-id="aabb3-124">패턴 목록 유형은 문서에서 정보를 식별하고 추출하는 설명을 만드는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-124">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="aabb3-125">일반적으로 날짜, 전화 번호, 신용카드 번호와 같은 다양한 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-125">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="aabb3-126">예를 들어 날짜의 경우 다양한 형식(2020/1/1, 2020-1-1, 20/01/01, 2020/01/01, 2020년 1월 1일 등)으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-126">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="aabb3-127">패턴 목록을 정의하면 식별하고 추출하려는 데이터의 가능한 모든 변형을 캡처하여 더 효율적으로 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-127">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="aabb3-128">**전화 번호** 샘플의 경우, 모델이 식별하는 모든 의학 조회 문서에서 각각 추천하는 의사의 전화 번호를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-128">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="aabb3-129">설명을 만들 때 패턴 목록 유형을 선택하면 돌아올 수 있는 다양한 형식을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-129">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![전화 번호 패턴 목록](../media/content-understanding/pattern-list.png)

<span data-ttu-id="aabb3-131">이 샘플의 경우 **0부터 9 사이 아무 숫자** 체크박스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-131">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="aabb3-132">이 값을 선택하면 패턴 목록에서 사용되는 각각의 "0" 값이 0부터 9 사이의 어떤 숫자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-132">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0부터 9 사이 아무 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="aabb3-134">마찬가지로 텍스트 문자를 포함하는 패턴 목록을 만드는 경우에는 **a부터 z 사이 아무 문자** 체크박스를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-134">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="aabb3-135">이를 선택하면 패턴 목록에서 사용되는 각 "a" 문자가 "a"부터 "z" 사이의 아무 문자로 인식됩니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-135">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="aabb3-136">예를 들어 **날짜** 패턴 목록을 만들 때 *2020년 1월 1일*과 같은 날짜 서식이 인식되도록 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-136">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="aabb3-137">*0000 aaa 0*과 *0000 aaa 00*을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-137">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="aabb3-138">**a부터 z 사이 아무 문자**를 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-138">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![a부터 z 사이 아무 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="aabb3-140">또한 패턴 목록에 대문자화 요구 사항이 있는 경우에는 **정확한 대소문자 사용** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-140">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="aabb3-141">날짜 예제의 경우 달의 첫 글자를 대문자로 표기하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-141">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="aabb3-142">*0000 Aaa 0*과 *0000 Aaa 00*을 패턴 목록에 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-142">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="aabb3-143">**정확한 대소문자 사용**이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-143">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![정확한 대소문자 사용](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="aabb3-145">패턴 목록 설명을 수동으로 만드는 대신 [설명 라이브러리]()를 사용하여 *날짜*, *전화 번호*, *신용카드 번호* 등 미리 만들어진 일반 패턴 목록의 서식파일을 사용할 수 있습니다.  </span><span class="sxs-lookup"><span data-stu-id="aabb3-145">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="aabb3-146">근접</span><span class="sxs-lookup"><span data-stu-id="aabb3-146">Proximity</span></span> 

<span data-ttu-id="aabb3-147">근접 설명 유형은 사용자의 모델이 각각의 데이터가 서로 얼마나 근접해 있는지를 규정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-147">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="aabb3-148">예를 들어 모델에서 고객의 *거리 주소 번호*와 *전화 번호*를 둘 다 표시하는 두 개의 설명을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-148">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="aabb3-149">또한 고객 전화 번호는 항상 거리 주소 번호 앞에 표시된다는 것을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-149">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="aabb3-150">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="aabb3-150">Alex Wilburn</span></span><br>
<span data-ttu-id="aabb3-151">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="aabb3-151">555-555-5555</span></span><br>
<span data-ttu-id="aabb3-152">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="aabb3-152">One Microsoft Way</span></span><br>
<span data-ttu-id="aabb3-153">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="aabb3-153">Redmond, WA 98034</span></span><br>

<span data-ttu-id="aabb3-154">근접 설명을 사용하여 전화 번호 설명이 문서에서 거리 주소 번호를 식별해내기에 근접하지 않은 설명이라는 것을 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-154">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![근접 설명](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="aabb3-156">토큰이란?</span><span class="sxs-lookup"><span data-stu-id="aabb3-156">What are tokens?</span></span>

<span data-ttu-id="aabb3-157">근사 설명 유형을 사용하려면 토큰이 무엇인지 이해하고 근접 설명이 두 개의 설명 간의 거리를 어떻게 측정하는지 토큰의 수로 알 수 있다는 점을 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-157">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="aabb3-158">토큰은 문자와 숫자의 연속 범위(공백이나 문장 부호 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-158">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="aabb3-159">공백은 토큰이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-159">A space is NOT a token.</span></span> <span data-ttu-id="aabb3-160">각 문장 부호는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-160">Each punctuation character is a token.</span></span> <span data-ttu-id="aabb3-161">다음 표는 한 개의 구에서 토큰 수를 확인하는 방법에 대해 몇 가지 예로 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-161">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="aabb3-162">구</span><span class="sxs-lookup"><span data-stu-id="aabb3-162">Phrase</span></span>|<span data-ttu-id="aabb3-163">토큰 수</span><span class="sxs-lookup"><span data-stu-id="aabb3-163">Number of tokens</span></span>|<span data-ttu-id="aabb3-164">설명</span><span class="sxs-lookup"><span data-stu-id="aabb3-164">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="aabb3-165">1</span><span class="sxs-lookup"><span data-stu-id="aabb3-165">1</span></span>|<span data-ttu-id="aabb3-166">문장 부호나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-166">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="aabb3-167">1</span><span class="sxs-lookup"><span data-stu-id="aabb3-167">1</span></span>|<span data-ttu-id="aabb3-168">레코드 로케이터 번호</span><span class="sxs-lookup"><span data-stu-id="aabb3-168">A record locator number.</span></span> <span data-ttu-id="aabb3-169">숫자와 문자가 포함될 수 있지만 문장 부호는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-169">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="aabb3-170">5</span><span class="sxs-lookup"><span data-stu-id="aabb3-170">5</span></span>|<span data-ttu-id="aabb3-171">전화 번호</span><span class="sxs-lookup"><span data-stu-id="aabb3-171">A phone number.</span></span> <span data-ttu-id="aabb3-172">각 문장 부호 기호는 단일 토큰이므로 `425-555-5555`의 경우 5개의 토큰이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-172">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="aabb3-173">7</span><span class="sxs-lookup"><span data-stu-id="aabb3-173">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="aabb3-174">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="aabb3-174">Configure the proximity explanation type</span></span>

<span data-ttu-id="aabb3-175">샘플에 대한 근접 설정을 구성하여 *거리 주소 번호* 설명으로부터 *전화 번호* 설명의 토큰 수 범위를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-175">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="aabb3-176">전화 번호와 거리 주소 번호 사이에는 토큰이 없기 때문에 최소 범위는 "0" 이라는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-176">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="aabb3-177">그러나 샘플 문서의 일부 전화 번호에는 *(휴대폰)* 이 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-177">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="aabb3-178">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="aabb3-178">Nestor Wilke</span></span><br>
<span data-ttu-id="aabb3-179">111-111-1111(휴대폰)</span><span class="sxs-lookup"><span data-stu-id="aabb3-179">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="aabb3-180">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="aabb3-180">One Microsoft Way</span></span><br>
<span data-ttu-id="aabb3-181">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="aabb3-181">Redmond, WA 98034</span></span><br>

<span data-ttu-id="aabb3-182">*(휴대폰)* 에는 세 개의 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-182">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="aabb3-183">구</span><span class="sxs-lookup"><span data-stu-id="aabb3-183">Phrase</span></span>|<span data-ttu-id="aabb3-184">토큰 수</span><span class="sxs-lookup"><span data-stu-id="aabb3-184">Token count</span></span>|
|--|--|
|<span data-ttu-id="aabb3-185">(</span><span class="sxs-lookup"><span data-stu-id="aabb3-185">(</span></span>|<span data-ttu-id="aabb3-186">1</span><span class="sxs-lookup"><span data-stu-id="aabb3-186">1</span></span>|
|<span data-ttu-id="aabb3-187">휴대폰</span><span class="sxs-lookup"><span data-stu-id="aabb3-187">mobile</span></span>|<span data-ttu-id="aabb3-188">2</span><span class="sxs-lookup"><span data-stu-id="aabb3-188">2</span></span>|
|<span data-ttu-id="aabb3-189">)</span><span class="sxs-lookup"><span data-stu-id="aabb3-189">)</span></span>|<span data-ttu-id="aabb3-190">3</span><span class="sxs-lookup"><span data-stu-id="aabb3-190">3</span></span>|

<span data-ttu-id="aabb3-191">근접 설정이 0에서 3의 범위를 갖도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-191">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![근접의 예](../media/content-understanding/proximity-example.png)</br>

## <a name="use-explanation-templates"></a><span data-ttu-id="aabb3-193">설명 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="aabb3-193">Use explanation templates</span></span>

<span data-ttu-id="aabb3-194">설명에 대한 다양한 패턴 목록 값을 수동으로 추가할 수 있지만, 설명 라이브러리에서 미리 작성된 서식 파일을 찾아 사용하는 것이 훨씬 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-194">While you can manually add various pattern list values for your explanation, it can be much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="aabb3-195">예를 들어 *날짜*에 대한 모든 변형을 수동으로 추가하는 대신 이미 여러 패턴 목록 값을 포함하고 있는 *날짜* 패턴 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-195">For example, instead of manually adding all the variations for *Date*, you can use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![설명 라이브러리](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="aabb3-197">설명 라이브러리에는 다음을 비롯하여 일반적으로 많이 사용되는 몇 가지 패턴 목록 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-197">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="aabb3-198">날짜</span><span class="sxs-lookup"><span data-stu-id="aabb3-198">Date</span></span></br>
- <span data-ttu-id="aabb3-199">날짜(숫자)</span><span class="sxs-lookup"><span data-stu-id="aabb3-199">Date (numeric)</span></span></br>
- <span data-ttu-id="aabb3-200">시간</span><span class="sxs-lookup"><span data-stu-id="aabb3-200">Time</span></span></br>
- <span data-ttu-id="aabb3-201">숫자</span><span class="sxs-lookup"><span data-stu-id="aabb3-201">Number</span></span></br>
- <span data-ttu-id="aabb3-202">전화 번호</span><span class="sxs-lookup"><span data-stu-id="aabb3-202">Phone number</span></span></br>
- <span data-ttu-id="aabb3-203">우편 번호</span><span class="sxs-lookup"><span data-stu-id="aabb3-203">Zip code</span></span></br>
- <span data-ttu-id="aabb3-204">문장의 첫 번째 단어</span><span class="sxs-lookup"><span data-stu-id="aabb3-204">First word of sentence</span></span></br>
- <span data-ttu-id="aabb3-205">신용카드</span><span class="sxs-lookup"><span data-stu-id="aabb3-205">Credit card</span></span></br>
- <span data-ttu-id="aabb3-206">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="aabb3-206">Social security number</span></span></br>

<span data-ttu-id="aabb3-207">또한 설명 라이브러리에는 다음을 포함한 구 목록 설명의 서식 파일도 포함하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-207">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="aabb3-208">문장의 끝</span><span class="sxs-lookup"><span data-stu-id="aabb3-208">End of sentence</span></span>
- <span data-ttu-id="aabb3-209">통화</span><span class="sxs-lookup"><span data-stu-id="aabb3-209">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="aabb3-210">설명 라이브러리에서 서식 파일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="aabb3-210">To use a template from the explanation library</span></span>

1. <span data-ttu-id="aabb3-211">모델의 **교육** 페이지의 **설명** 구역에서 **신규**를 선택한 다음 **서식 파일 사용**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-211">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![서식 파일로 만들기](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="aabb3-213">**설명 서식 파일** 페이지에서 사용하려는 설명을 선택하고 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-213">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![서식 파일 선택](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="aabb3-215">선택한 서식 파일에 대한 정보는 **설명 만들기** 페이지에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-215">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="aabb3-216">필요한 경우 설명 이름을 편집하고 패턴 목록에서 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-216">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![서식 파일 편집](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="aabb3-218">작업을 끝낸 후 **저장**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="aabb3-218">When finished, select **Save**.</span></span>
