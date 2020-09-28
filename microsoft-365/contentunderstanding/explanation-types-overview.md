---
title: 설명 유형
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 10/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Microsoft SharePoint Syntex의 설명 유형에 대해 자세히 알아보기
ms.openlocfilehash: f4f5dbc24bef57b1801f7df1b7e2fc7ef9b08116
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295992"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="1dec4-103">설명 유형 소개</span><span class="sxs-lookup"><span data-stu-id="1dec4-103">Introduction to explanation types</span></span>

<span data-ttu-id="1dec4-104">설명을 사용 하 여 레이블을 지정할 정보를 정의 하 고 문서에서 추출 하는 데 도움이 되는 Microsoft SharePoint Syntex 모델을 파악 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-104">Use explanations to help to define the information that you want to label, and extract in your document the understanding models for Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="1dec4-105">설명을 만들 때 설명 유형을 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-105">When you create an explanation, be sure to select an explanation type.</span></span> 

<span data-ttu-id="1dec4-106">이 문서는 다양 한 설명 유형 및 사용 방법을 이해 하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-106">This article helps you understand the different explanation types and how they are used.</span></span>

   ![설명 유형](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="1dec4-108">이러한 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-108">These explanation types are available:</span></span>

- <span data-ttu-id="1dec4-109">**구 목록**: 추출 하려는 문서나 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자에 대 한 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="1dec4-110">예를 들어 **의사를 참조** 하는 텍스트 문자열은 식별 하려는 모든 의료 리퍼럴 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span></br>

- <span data-ttu-id="1dec4-111">**패턴 목록**: 추출할 정보를 식별 하는 데 사용할 수 있는 숫자, 문자 또는 기타 문자의 패턴을 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-111">**Pattern list**: List patterns of numbers, letters, or other characters that you can use to identify the information that you are extracting.</span></span> <span data-ttu-id="1dec4-112">예를 들어 식별 중인 모든 의료 리퍼럴 문서에서 참조 하는 의사 결정의 **전화 번호** 를 추출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-112">For example, you can extract the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span></br>

- <span data-ttu-id="1dec4-113">**근접성**: 서로 근접 한 설명을 어떻게 들을 것인지 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-113">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="1dec4-114">예를 들어 *전화 번호* 패턴 목록은 다음 사이에 토큰 없이 (이 문서의 뒷부분에 나오는 토큰에 대해 자세히 알아봅니다.) *주소* 구문 목록 바로 앞에 옵니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-114">For example, a *street number* pattern list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="1dec4-115">구 목록</span><span class="sxs-lookup"><span data-stu-id="1dec4-115">Phrase list</span></span>

<span data-ttu-id="1dec4-116">구 목록 설명 유형은 일반적으로 모델을 통해 문서를 식별 하 고 분류 하는 데 사용 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="1dec4-117">*참조 의사* 레이블 예제에 설명 된 것 처럼 식별 하려는 문서에서 일관 되 게 사용할 수 있는 단어, 구, 숫자 또는 문자 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="1dec4-118">요구 사항은 아니지만 캡처가 있는 구가 문서에서 일관 된 위치에 있는 경우에는 설명에 따라 성공을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-118">While not a requirement, you can acheive better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="1dec4-119">예를 들어 참조 하는 *의사* 레이블은 문서의 첫 번째 단락에 일관 되 게 배치 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span>

<span data-ttu-id="1dec4-120">레이블을 식별 하는 데 대/소문자 구분이 요구 되는 경우 구 목록 형식을 사용 하면 **정확한 대문자화** 확인란을 선택 하 여 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-120">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

   ![대/소문자 구분](../media/content-understanding/case-sensitivity.png) 

## <a name="pattern-lists"></a><span data-ttu-id="1dec4-122">패턴 목록</span><span class="sxs-lookup"><span data-stu-id="1dec4-122">Pattern lists</span></span>

<span data-ttu-id="1dec4-123">패턴 목록 유형은 특히 문서에서 정보를 식별 하 고 추출 하는 설명을 작성할 때 유용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-123">A pattern list type is especially useful when you create an explanation that identifies and extracts information from a document.</span></span> <span data-ttu-id="1dec4-124">일반적으로 날짜, 전화 번호 또는 신용 카드 번호와 같은 다양 한 형식으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-124">It is typically presented in different formats, such as dates, phone numbers, or credit card numbers.</span></span> <span data-ttu-id="1dec4-125">예를 들어 날짜는 여러 가지 형식으로 표시할 수 있습니다 (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1, 2020 등).</span><span class="sxs-lookup"><span data-stu-id="1dec4-125">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="1dec4-126">패턴 목록을 정의 하면 식별 하 고 추출할 데이터에서 가능한 변형을 캡처하여 보다 효율적으로 설명을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-126">Defining a pattern list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="1dec4-127">**전화 번호** 예제에서 모델이 식별 하는 모든 의료 리퍼럴 문서에서 각 참조 하는 의사에 대 한 전화 번호를 추출 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-127">For the **Phone number** sample, extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="1dec4-128">설명을 만들 때 패턴 목록 유형을 선택 하 여 반환 될 것으로 예상 되는 다양 한 형식을 허용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-128">When you create the explanation, select the Pattern list type to allow the different formats that you may expect to be returned.</span></span>

   ![전화 번호 패턴 목록](../media/content-understanding/pattern-list.png)

<span data-ttu-id="1dec4-130">이 예제에서는 **0-9에서 임의의 숫자** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-130">For this sample, select the **Any digit from 0-9** checkbox.</span></span> <span data-ttu-id="1dec4-131">이 항목을 선택 하면 패턴 목록에서 사용 되는 각 "0" 값이 0부터 9 까지의 숫자로 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-131">Selecting this recognizes each "0" value used in your pattern list to be any digit from 0 through 9.</span></span>

   ![0-9부터 시작 하는 모든 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="1dec4-133">마찬가지로 텍스트 문자를 포함 하는 패턴 목록을 만드는 경우 **에는 a-z** 확인란을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-133">Similarly, if you create a pattern list that includes text characters, select the **Any letter from a-z** checkbox.</span></span> <span data-ttu-id="1dec4-134">이 항목을 선택 하면 패턴 목록에서 사용 되는 각 "a" 문자가 "a"에서 "z" 까지의 문자로 인식 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-134">Selecting this recognizes each "a" character used in the pattern list to be any character from "a" to "z".</span></span>

<span data-ttu-id="1dec4-135">예를 들어 **날짜** 패턴 목록을 만들고 *2020 년 1 월 2* 일과 같은 날짜 형식이 인식 되도록 하려면 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-135">For example, if you create a **Date** pattern list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="1dec4-136">패턴 목록에 *aaa 0, 0000* 및 *aaa 00, 0000* 을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-136">Add *aaa 0, 0000* and *aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1dec4-137">**A-z의 문자도** 선택 되어 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-137">Make sure that **Any letter from a-z** is also selected.</span></span>

   ![A-z의 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="1dec4-139">또한 패턴 목록에 대문자화 요구 사항이 있는 경우 **정확히 대문자** 표시 확인란을 선택 하는 옵션이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-139">Additionally, if you have capitalization requirements in your pattern list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="1dec4-140">날짜 예제에서 월의 첫 글자가 대문자로 시작 해야 하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-140">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="1dec4-141">패턴 목록에 *Aaa 0, 0000* 및 *Aaa 00, 0000* 을 추가 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-141">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your pattern list.</span></span>
- <span data-ttu-id="1dec4-142">정확 하 게 **대/소문자** 도 선택 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-142">Make sure that **Only exact capitalization** is also selected.</span></span>

   ![정확한 대/소문자만](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="1dec4-144">패턴 목록 설명을 수동으로 만드는 대신, [설명 라이브러리]() 를 사용 하 여 *날짜*, *전화 번호*, *신용 카드 번호*등의 일반 패턴 목록에 미리 구성 된 패턴 목록 서식 파일을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-144">Instead of manually creating pattern list explanation, use the [explanation library]() to use pre-made pattern list templates for common pattern list, such as *date*, *phone number*, *credit card number*, etc..</span></span> 

## <a name="proximity"></a><span data-ttu-id="1dec4-145">근접</span><span class="sxs-lookup"><span data-stu-id="1dec4-145">Proximity</span></span> 

<span data-ttu-id="1dec4-146">근접 설명 유형을 사용 하면 모델에서 다른 데이터에 얼마나 근접 하는지 정의 하는 방식으로 데이터를 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-146">The proximity explanation type helps your model identify data through defining how close another piece of data is to it.</span></span> <span data-ttu-id="1dec4-147">예를 들어 모델에서 고객의 *주소 번호* 와 *전화 번호*에 레이블을 지정 하는 두 가지 설명을 정의 했습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-147">For example, in your model, you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="1dec4-148">또한 고객 전화 번호가 항상 주소 번호 보다 앞에 표시 되는 것을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-148">You also notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="1dec4-149">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="1dec4-149">Alex Wilburn</span></span><br>
<span data-ttu-id="1dec4-150">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="1dec4-150">555-555-5555</span></span><br>
<span data-ttu-id="1dec4-151">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1dec4-151">One Microsoft Way</span></span><br>
<span data-ttu-id="1dec4-152">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="1dec4-152">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1dec4-153">근접 설명을 사용 하 여 문서에서 주소 번호를 보다 쉽게 식별할 수 있도록 전화 번호 설명의 거리를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-153">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

   ![근접 설명](../media/content-understanding/proximity.png)</br>

#### <a name="what-are-tokens"></a><span data-ttu-id="1dec4-155">토큰 이란?</span><span class="sxs-lookup"><span data-stu-id="1dec4-155">What are tokens?</span></span>

<span data-ttu-id="1dec4-156">근사 설명 유형을 사용 하기 위해 토큰의 수는 근접 설명에서 한 설명 간의 거리를 측정 하는 방식을 이해 하는 것과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-156">In order to use the proximity explanation type, understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span>  

<span data-ttu-id="1dec4-157">토큰은 문자와 숫자의 연속 범위 (공백이 나 문장 부호 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-157">A token is a continuous span (no spaces or punctuation) of letters and numbers.</span></span> <span data-ttu-id="1dec4-158">공간이 토큰이 아닙니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-158">A space is NOT a token.</span></span> <span data-ttu-id="1dec4-159">각 문장 부호 문자는 토큰입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-159">Each punctuation character is a token.</span></span> <span data-ttu-id="1dec4-160">다음 표에서는 구의 토큰 수를 결정 하는 방법에 대 한 몇 가지 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-160">The following table shows some examples of how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="1dec4-161">어간</span><span class="sxs-lookup"><span data-stu-id="1dec4-161">Phrase</span></span>|<span data-ttu-id="1dec4-162">토큰 수</span><span class="sxs-lookup"><span data-stu-id="1dec4-162">Number of tokens</span></span>|<span data-ttu-id="1dec4-163">설명</span><span class="sxs-lookup"><span data-stu-id="1dec4-163">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="1dec4-164">1 </span><span class="sxs-lookup"><span data-stu-id="1dec4-164">1</span></span>|<span data-ttu-id="1dec4-165">문장 부호 나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-165">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="1dec4-166">1 </span><span class="sxs-lookup"><span data-stu-id="1dec4-166">1</span></span>|<span data-ttu-id="1dec4-167">레코드 로케이터 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-167">A record locator number.</span></span> <span data-ttu-id="1dec4-168">숫자와 문자를 포함할 수 있지만 문장 부호를 포함 하지는 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-168">It may have numbers and letters, but does not have any punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="1dec4-169">5 </span><span class="sxs-lookup"><span data-stu-id="1dec4-169">5</span></span>|<span data-ttu-id="1dec4-170">전화 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-170">A phone number.</span></span> <span data-ttu-id="1dec4-171">각 문장 부호는 단일 토큰이 며  `425-555-5555` 5 개의 토큰으로 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-171">Each punctuation mark is a single token so  `425-555-5555` would be 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="1dec4-172">7 </span><span class="sxs-lookup"><span data-stu-id="1dec4-172">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="1dec4-173">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="1dec4-173">Configure the proximity explanation type</span></span>

<span data-ttu-id="1dec4-174">예제의 경우 *전화 번호* 설명이 *주소 번호* 설명에서 가져온 토큰 수 범위를 정의할 수 있도록 근접 설정을 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-174">For the sample, configure the proximity setting so that we can define the range of the number of tokens the *Phone number* explanation is from the *Street address number* explanation.</span></span>

<span data-ttu-id="1dec4-175">전화 번호와 주소 번호 사이에는 토큰이 없기 때문에 최소 범위는 "0"입니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-175">You should see that the minimum range is "0" since there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="1dec4-176">그러나 예제 문서에 있는 일부 전화 번호에는 *(mobile)* 이 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-176">However, some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="1dec4-177">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="1dec4-177">Nestor Wilke</span></span><br>
<span data-ttu-id="1dec4-178">111-111-1111 (모바일)</span><span class="sxs-lookup"><span data-stu-id="1dec4-178">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="1dec4-179">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="1dec4-179">One Microsoft Way</span></span><br>
<span data-ttu-id="1dec4-180">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="1dec4-180">Redmond, WA 98034</span></span><br>

<span data-ttu-id="1dec4-181">다음의 세 가지 토큰이 있습니다 *(모바일)*.</span><span class="sxs-lookup"><span data-stu-id="1dec4-181">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="1dec4-182">어간</span><span class="sxs-lookup"><span data-stu-id="1dec4-182">Phrase</span></span>|<span data-ttu-id="1dec4-183">토큰 수</span><span class="sxs-lookup"><span data-stu-id="1dec4-183">Token count</span></span>|
|--|--|
|<span data-ttu-id="1dec4-184">(</span><span class="sxs-lookup"><span data-stu-id="1dec4-184">(</span></span>|<span data-ttu-id="1dec4-185">1 </span><span class="sxs-lookup"><span data-stu-id="1dec4-185">1</span></span>|
|<span data-ttu-id="1dec4-186">이동성</span><span class="sxs-lookup"><span data-stu-id="1dec4-186">mobile</span></span>|<span data-ttu-id="1dec4-187">2 </span><span class="sxs-lookup"><span data-stu-id="1dec4-187">2</span></span>|
|<span data-ttu-id="1dec4-188">)</span><span class="sxs-lookup"><span data-stu-id="1dec4-188">)</span></span>|<span data-ttu-id="1dec4-189">3 </span><span class="sxs-lookup"><span data-stu-id="1dec4-189">3</span></span>|

<span data-ttu-id="1dec4-190">근사 설정은 0에서 3 사이의 범위로 구성 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-190">Configure the proximity setting to have a range of 0 through 3.</span></span>

   ![근접 예](../media/content-understanding/proximity-example.png)</br>

## <a name="use-the-explanation-library"></a><span data-ttu-id="1dec4-192">설명 라이브러리 사용</span><span class="sxs-lookup"><span data-stu-id="1dec4-192">Use the explanation library</span></span>

<span data-ttu-id="1dec4-193">설명에 대해 다양 한 패턴 목록 값을 수동으로 추가할 수 있지만 설명 라이브러리에서 제공 하는 미리 만들어진 서식 파일을 사용 하는 것이 훨씬 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-193">While you can manually add various pattern list values for your explanation, it's much easier to use the pre-created templates provided to you in the explanation library.</span></span>

<span data-ttu-id="1dec4-194">예를 들어, *날짜*에 대 한 모든 변형을 수동으로 추가 하는 대신 패턴 목록 서식 파일 *에 패턴을 사용*하 여 해당 값을 이미 많이 포함 하는 것이 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-194">For example, instead of manually adding all the variations for *Date*, use the pattern list template for *Date*, that already includes a number of pattern lists values:</span></span></br>

   ![설명 라이브러리](../media/content-understanding/explanation-template.png)</br>
 
<span data-ttu-id="1dec4-196">설명 라이브러리에는 다음을 비롯 하 여 일반적으로 사용 되는 패턴 목록 설명이 많이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-196">The explanation library includes a number of commonly used pattern list explanations, including:</span></span></br>

- <span data-ttu-id="1dec4-197">날짜</span><span class="sxs-lookup"><span data-stu-id="1dec4-197">Date</span></span></br>
- <span data-ttu-id="1dec4-198">날짜 (숫자)</span><span class="sxs-lookup"><span data-stu-id="1dec4-198">Date (numeric)</span></span></br>
- <span data-ttu-id="1dec4-199">Time</span><span class="sxs-lookup"><span data-stu-id="1dec4-199">Time</span></span></br>
- <span data-ttu-id="1dec4-200">숫자</span><span class="sxs-lookup"><span data-stu-id="1dec4-200">Number</span></span></br>
- <span data-ttu-id="1dec4-201">전화 번호</span><span class="sxs-lookup"><span data-stu-id="1dec4-201">Phone number</span></span></br>
- <span data-ttu-id="1dec4-202">우편번호</span><span class="sxs-lookup"><span data-stu-id="1dec4-202">Zip code</span></span></br>
- <span data-ttu-id="1dec4-203">문장의 첫 번째 단어</span><span class="sxs-lookup"><span data-stu-id="1dec4-203">First word of sentence</span></span></br>
- <span data-ttu-id="1dec4-204">신용 카드</span><span class="sxs-lookup"><span data-stu-id="1dec4-204">Credit card</span></span></br>
- <span data-ttu-id="1dec4-205">주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="1dec4-205">Social security number</span></span></br>

<span data-ttu-id="1dec4-206">설명 라이브러리에는 다음과 같은 용어 목록 설명 템플릿도 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-206">Note that the explanation library also includes templates for phrase list explanations as well, including:</span></span>
- <span data-ttu-id="1dec4-207">문장의 끝</span><span class="sxs-lookup"><span data-stu-id="1dec4-207">End of sentence</span></span>
- <span data-ttu-id="1dec4-208">통화</span><span class="sxs-lookup"><span data-stu-id="1dec4-208">Currency</span></span>

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="1dec4-209">설명 라이브러리의 서식 파일을 사용 하려면</span><span class="sxs-lookup"><span data-stu-id="1dec4-209">To use a template from the explanation library</span></span>

1. <span data-ttu-id="1dec4-210">모델 **학습** 페이지의 설명 섹션에서 **새로 만들기**를 선택한 다음 **템플릿에서**를 **선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="1dec4-210">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span></br>

   ![템플릿에서 만들기](../media/content-understanding/from-template.png)</br>

2.  <span data-ttu-id="1dec4-212">**설명 템플릿** 페이지에서 사용 하려는 설명을 선택 하 고 **추가**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-212">On the **Explanation templates** page, select the explanation you want to use, and then select **Add**.</span></span></br>

       ![서식 파일 선택](../media/content-understanding/phone-template.png)</br>

3. <span data-ttu-id="1dec4-214">선택한 서식 파일에 대 한 정보가 **설명 만들기** 페이지에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-214">The information for the template you selected will display on the **Create an explanation** page.</span></span> <span data-ttu-id="1dec4-215">필요한 경우 설명 이름을 편집 하 고 패턴 목록에서 항목을 추가 하거나 제거 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-215">If needed, edit the explanation name, and add or remove items from the pattern list.</span></span> </br> 

   ![서식 파일 편집](../media/content-understanding/phone-template-live.png)</br>

4. <span data-ttu-id="1dec4-217">완료 되 면 **저장**을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="1dec4-217">When finished, select **Save**.</span></span>
