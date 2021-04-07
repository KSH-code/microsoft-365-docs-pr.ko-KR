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
ms.openlocfilehash: a5404230a59d1740a2b855527229a7aca92195a8
ms.sourcegitcommit: dc1ac43a57fac6f57438859dd668f927d94fdf34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2021
ms.locfileid: "51604408"
---
# <a name="introduction-to-explanation-types"></a><span data-ttu-id="7cad5-103">설명 유형 소개</span><span class="sxs-lookup"><span data-stu-id="7cad5-103">Introduction to explanation types</span></span>

<span data-ttu-id="7cad5-104">설명은 Microsoft SharePoint Syntex의 모델에 대한 이해를 바탕으로 문서에 표시하고 추출하고자 하는 정보를 정의하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="7cad5-105">설명을 만들 때는 설명 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-105">When creating an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="7cad5-106">이 문서는 다양한 설명 유형과 사용 방법을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-106">This article helps you understand the different explanation types and how they are used.</span></span> 

![설명 유형](../media/content-understanding/explanation-types.png) 
   
<span data-ttu-id="7cad5-108">다음과 같은 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-108">These explanation types are available:</span></span>

- <span data-ttu-id="7cad5-109">**구 목록**: 추출하려는 문서나 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-109">**Phrase list**: List of words, phrases, numbers, or other characters you can use in the document or information that you are extracting.</span></span> <span data-ttu-id="7cad5-110">예를 들어 **의사 추천** 이란 텍스트 문자열은 파악할 수 있는 모든 의료 리퍼럴 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-110">For example, the text string **Referring Doctor** is in all Medical Referral documents you are identifying.</span></span> <span data-ttu-id="7cad5-111">또는 식별되는 모든 의학 조회 문서에서 **전화번호** 를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-111">Or the **Phone number** of the referring doctor from all Medical Referral document that you are identifying.</span></span>

- <span data-ttu-id="7cad5-112">**근접**: 각각의 설명이 서로 얼마나 근접한지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-112">**Proximity**: Describes how close explanations are to each other.</span></span> <span data-ttu-id="7cad5-113">예를 들어 *번지 수* 의 구 목록은 *길 이름* 바로 전에 나오고 토큰은 둘 사이에 존재하지 않습니다.(토큰에 대한 자세한 정보는 본 문서의 뒷부분에 나옵니다.)</span><span class="sxs-lookup"><span data-stu-id="7cad5-113">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="7cad5-114">근사 유형을 사용하려면 모델에 두 개 이상의 설명이 있어야 하고, 그렇지 않으면 해당 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-114">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span> 
 
## <a name="phrase-list"></a><span data-ttu-id="7cad5-115">구 목록</span><span class="sxs-lookup"><span data-stu-id="7cad5-115">Phrase list</span></span>

<span data-ttu-id="7cad5-116">일반적으로 구 목록 설명 형식은 모델을 통해 문서를 식별하고 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-116">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="7cad5-117">*의사 추천* 레이블 예제에 설명된 바와 같이, 확인 중인 문서에서 일관되게 나타나는 일련의 단어, 구, 숫자 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-117">As described in the *Referring Doctor* label example, it is a string of words, phrases, numbers, or characters that is consistently in the documents that you are identifying.</span></span>

<span data-ttu-id="7cad5-118">요구 사항은 아니지만, 캡처링하는 구가 문서의 일관된 위치에 있는 경우 설명의 성공을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-118">While not a requirement, you can achieve better success with your explanation if the phrase you are capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="7cad5-119">예를 들어, *의사 추천* 이란 레이블이 문서의 첫 번째 문단에 일관되게 배치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-119">For example, the *Referring Doctor* label may be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="7cad5-120">또한 **[문서에서 구가 발생할 위치 구성](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** 고급 설정을 사용하여 구가 위치한 특정 영역을 선택할 수 있습니다. 특히, 구가 문서의 여러 위치에서 발생할 가능성이 있는 경우에 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-120">You can also use the **[Configure where phrases occur in the document](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there is a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="7cad5-121">레이블을 식별하는데 대/소문자 구분이 필요하다면, 구 목록 유형을 사용하하면 **정확한 대소문자 사용** 체크박스를 선택하여 이를 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-121">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![대/소문자 구분](../media/content-understanding/case-sensitivity.png) 

<span data-ttu-id="7cad5-123">구 유형은 날짜, 전화번호, 신용 카드 번호 등 다양한 형식으로 정보를 식별하고 추출하는 설명을 만들 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-123">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="7cad5-124">예를 들어 날짜의 경우 다양한 형식(2020/1/1, 2020-1-1, 20/01/01, 2020/01/01, 2020년 1월 1일 등)으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-124">For example, a date can be displayed in a number of different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, Jan 1,2020, etc.).</span></span> <span data-ttu-id="7cad5-125">구 목록을 정의하면 식별하고 추출하려는 데이터의 가능한 모든 변형을 캡처하여 더 효율적으로 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-125">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you are trying to identify and extract.</span></span> 

<span data-ttu-id="7cad5-126">**전화번호** 샘플의 경우, 모델이 식별하는 모든 의학 조회 문서에서 각각 추천하는 의사의 전화번호를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-126">For the **Phone number** example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="7cad5-127">설명을 만들 때 가능한 변형을 파악할 수 있도록 문서에 표시할 수 있는 다양한 전화번호 형식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-127">When you create the explanation, type the different formats a phone number might display in your document so that you are able to capture possible variations.</span></span> 

![전화번호 구 패턴](../media/content-understanding/pattern-list.png)

<span data-ttu-id="7cad5-129">이 예에서는 **고급 설정** 에서 **0-9 사이의 임의의 수** 확인란을 선택하여 구 목록에 사용된 각 "0" 값을 0부터 9까지의 숫자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-129">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![0부터 9 사이 아무 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="7cad5-131">마찬가지로 텍스트 문자를 포함하는 구 목록을 만들 경우 **a-z 사이의 임의의 문자** 확인란을 선택하여 구 목록에 사용된 각 "a" 문자를 "a"에서 "z"까지의 문자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-131">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="7cad5-132">예를 들어 **날짜** 구 목록을 만들 때 *2020년 1월 1일* 과 같은 날짜 서식이 인식되도록 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-132">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>
- <span data-ttu-id="7cad5-133">구 목록에 *aaa 0, 0000* 및 *aaa 00, 0000* 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-133">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="7cad5-134">**a부터 z 사이 아무 문자** 를 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-134">Make sure that **Any letter from a-z** is also selected.</span></span>

![a부터 z 사이 아무 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="7cad5-136">또한 구 목록에 대문자화 요구 사항이 있는 경우에는 **정확한 대소문자 사용** 옵션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-136">Additionally, if you have capitalization requirements in your phrase list, you have the option to select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="7cad5-137">날짜 예제의 경우 달의 첫 글자를 대문자로 표기하는 경우 다음을 수행 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-137">For the Date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="7cad5-138">구 목록에 *Aaa 0, 0000* 및 *Aaa 00, 0000* 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-138">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="7cad5-139">**정확한 대소문자 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-139">Make sure that **Only exact capitalization** is also selected.</span></span>

![정확한 대소문자 사용](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="7cad5-141">구 목록 설명을 수동으로 만드는 대신 [설명 라이브러리](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates)를 사용하여 *날짜*, *전화번호*, *신용카드 번호* 등 일반 구 목록에 구 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-141">Instead of manually creating a phrase list explanation, use the [explanation library](https://docs.microsoft.com/microsoft-365/contentunderstanding/explanation-types-overview#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, *credit card number*, etc.</span></span>

## <a name="proximity"></a><span data-ttu-id="7cad5-142">근접</span><span class="sxs-lookup"><span data-stu-id="7cad5-142">Proximity</span></span> 

<span data-ttu-id="7cad5-143">근접 설명 유형은 사용자의 모델이 각각의 데이터가 서로 얼마나 근접해 있는지를 규정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-143">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="7cad5-144">예를 들어 모델에서 고객의 *거리 주소 번호* 와 *전화 번호* 를 둘 다 표시하는 두 개의 설명을 규정합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-144">For example, in your model say you have defined two explanations that label both the customer *Street address number* and *Phone number*.</span></span> 

<span data-ttu-id="7cad5-145">또한 고객 전화 번호는 항상 거리 주소 번호 앞에 표시된다는 것을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-145">Notice that customer phone numbers always appear before the street address number.</span></span> 

<span data-ttu-id="7cad5-146">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="7cad5-146">Alex Wilburn</span></span><br>
<span data-ttu-id="7cad5-147">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="7cad5-147">555-555-5555</span></span><br>
<span data-ttu-id="7cad5-148">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="7cad5-148">One Microsoft Way</span></span><br>
<span data-ttu-id="7cad5-149">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="7cad5-149">Redmond, WA 98034</span></span><br>

<span data-ttu-id="7cad5-150">근접 설명을 사용하여 전화 번호 설명이 문서에서 거리 주소 번호를 식별해내기에 근접하지 않은 설명이라는 것을 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-150">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![근접 설명](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="7cad5-152">토큰이란?</span><span class="sxs-lookup"><span data-stu-id="7cad5-152">What are tokens?</span></span>

<span data-ttu-id="7cad5-153">근사 설명 유형을 사용하려면 근접 설명이 두 개의 설명 간의 거리를 어떻게 측정하는지 토큰의 수로 알 수 있으므로 토큰이 무엇인지를 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-153">In order to use the proximity explanation type, you need to understand what a token is, as the number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="7cad5-154">토큰은 문자와 숫자의 연속 범위(공백이나 문장 부호 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-154">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span> 

<span data-ttu-id="7cad5-155">다음 표는 한 개의 구에서 토큰 수를 확인하는 방법에 대해 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-155">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="7cad5-156">구</span><span class="sxs-lookup"><span data-stu-id="7cad5-156">Phrase</span></span>|<span data-ttu-id="7cad5-157">토큰 수</span><span class="sxs-lookup"><span data-stu-id="7cad5-157">Number of tokens</span></span>|<span data-ttu-id="7cad5-158">설명</span><span class="sxs-lookup"><span data-stu-id="7cad5-158">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="7cad5-159">1</span><span class="sxs-lookup"><span data-stu-id="7cad5-159">1</span></span>|<span data-ttu-id="7cad5-160">문장 부호나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-160">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="7cad5-161">1</span><span class="sxs-lookup"><span data-stu-id="7cad5-161">1</span></span>|<span data-ttu-id="7cad5-162">레코드 로케이터 번호</span><span class="sxs-lookup"><span data-stu-id="7cad5-162">A record locator number.</span></span> <span data-ttu-id="7cad5-163">숫자와 문자가 포함될 수 있지만 문장 부호는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-163">It may include numbers and letters, but does not have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="7cad5-164">5</span><span class="sxs-lookup"><span data-stu-id="7cad5-164">5</span></span>|<span data-ttu-id="7cad5-165">전화 번호</span><span class="sxs-lookup"><span data-stu-id="7cad5-165">A phone number.</span></span> <span data-ttu-id="7cad5-166">각 문장 부호 기호는 단일 토큰이므로 `425-555-5555`의 경우 5개의 토큰이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-166">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="7cad5-167">7</span><span class="sxs-lookup"><span data-stu-id="7cad5-167">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="7cad5-168">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="7cad5-168">Configure the proximity explanation type</span></span>

<span data-ttu-id="7cad5-169">샘플에 대한 근접 설정을 구성하여 *거리 주소 번호* 설명으로부터 *전화 번호* 설명의 토큰 수 범위를 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-169">For the example, configure the proximity setting to define the range of the number of tokens in the *Phone number* explanation from the *Street address number* explanation.</span></span> <span data-ttu-id="7cad5-170">전화 번호와 거리 주소 번호 사이에는 토큰이 없기 때문에 최소 범위는 "0" 이라는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-170">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="7cad5-171">그러나 샘플 문서의 일부 전화 번호에는 *(휴대폰)* 이 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-171">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="7cad5-172">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="7cad5-172">Nestor Wilke</span></span><br>
<span data-ttu-id="7cad5-173">111-111-1111(휴대폰)</span><span class="sxs-lookup"><span data-stu-id="7cad5-173">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="7cad5-174">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="7cad5-174">One Microsoft Way</span></span><br>
<span data-ttu-id="7cad5-175">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="7cad5-175">Redmond, WA 98034</span></span><br>

<span data-ttu-id="7cad5-176">*(휴대폰)* 에는 세 개의 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-176">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="7cad5-177">구</span><span class="sxs-lookup"><span data-stu-id="7cad5-177">Phrase</span></span>|<span data-ttu-id="7cad5-178">토큰 수</span><span class="sxs-lookup"><span data-stu-id="7cad5-178">Token count</span></span>|
|--|--|
|<span data-ttu-id="7cad5-179">(</span><span class="sxs-lookup"><span data-stu-id="7cad5-179">(</span></span>|<span data-ttu-id="7cad5-180">1</span><span class="sxs-lookup"><span data-stu-id="7cad5-180">1</span></span>|
|<span data-ttu-id="7cad5-181">휴대폰</span><span class="sxs-lookup"><span data-stu-id="7cad5-181">mobile</span></span>|<span data-ttu-id="7cad5-182">2</span><span class="sxs-lookup"><span data-stu-id="7cad5-182">2</span></span>|
|<span data-ttu-id="7cad5-183">)</span><span class="sxs-lookup"><span data-stu-id="7cad5-183">)</span></span>|<span data-ttu-id="7cad5-184">3</span><span class="sxs-lookup"><span data-stu-id="7cad5-184">3</span></span>|

<span data-ttu-id="7cad5-185">근접 설정이 0에서 3의 범위를 갖도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-185">Configure the proximity setting to have a range of 0 through 3.</span></span>

![근접의 예](../media/content-understanding/proximity-example.png)


## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="7cad5-187">문서에서 구가 발생하는 위치 구성</span><span class="sxs-lookup"><span data-stu-id="7cad5-187">Configure where phrases occur in the document</span></span>

<span data-ttu-id="7cad5-188">설명을 만들 때 기본적으로 전체 문서에서 추출하려는 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-188">When you create an explanation, by default the entire document is searched for the phrase you are trying to extract.</span></span> <span data-ttu-id="7cad5-189">그러나 **문서에서 이 구가 발생하는 위치** 고급 설정을 사용하면 문서에서 이러한 구가 발생하는 위치를 설정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-189">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="7cad5-190">이 기능은 문서의 다른 위치에서 구와 비슷한 인스턴스가 표시되고 올바른 구가 선택되어 있는지 확인하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-190">This is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span> <span data-ttu-id="7cad5-191">의료 의뢰 문서를 예로 들면 **의사 의뢰** 는 항상 문서의 첫 번째 단락에 언급되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-191">Referring to our Medical Referral document example, the **Referring Doctor** is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="7cad5-192">이 예에서는 \*\*이러한 구가 발생하는 위치 설정을 사용하여 문서의 시작 부분 또는 이 구가 발생할 수 있는 다른 위치에서만 이 레이블을 검색하도록 설명을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-192">With the \*\*Where these phrases occur setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![이러한 구가 발생하는 위치 설정](../media/content-understanding/phrase-location.png)

<span data-ttu-id="7cad5-194">이 설정에 대해 다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-194">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="7cad5-195">파일의 모든 위치: 전체 문서에서 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-195">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="7cad5-196">파일의 시작: 문서가 처음부터 구 위치까지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-196">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![파일의 시작 부분](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="7cad5-198">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-198">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="7cad5-199">**끝 위치** 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-199">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="7cad5-200">끝 위치 값을 업데이트하여 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-200">Note that you can update the End position value as well to adjust the selected area.</span></span>

   ![파일 위치 상자의 시작 부분](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="7cad5-202">파일의 끝 위치: 문서가 끝부터 구 위치까지 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-202">End of the file:  The document is searched from the end to the phrase location.</span></span>

   ![파일의 끝 부분](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="7cad5-204">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-204">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="7cad5-205">**시작 위치** 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-205">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="7cad5-206">시작 위치 값을 업데이트하여 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-206">Note that you can update the Starting position value as well to adjust the selected area.</span></span>

   ![파일 끝 상자의 끝 부분](../media/content-understanding/end-box.png)

- <span data-ttu-id="7cad5-208">사용자 지정 범위: 문서가 구 위치에 대해 지정된 범위 내에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-208">Custom range:  The document is searched in a specified range within the it for the phrase location.</span></span>

   ![사용자 지정 범위](../media/content-understanding/custom-file.png)

    <span data-ttu-id="7cad5-210">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-210">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="7cad5-211">이 설정의 경우 시작 **시작** 과 **끝** 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-211">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="7cad5-212">이러한 값은 문서 시작에서 토큰 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-212">These values represent the number of tokens from the begging of the document.</span></span> <span data-ttu-id="7cad5-213">이러한 값은 수동으로 입력할 수 있지만 뷰어에서 선택 상자를 수동으로 조정하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-213">While you can manually enter in these values, it is easier to manually adjust the select box in the viewer.</span></span> 
   
## <a name="use-explanation-templates"></a><span data-ttu-id="7cad5-214">설명 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="7cad5-214">Use explanation templates</span></span>

<span data-ttu-id="7cad5-215">설명에 대한 다양한 구 목록 값을 수동으로 추가할 수 있지만, 설명 라이브러리에서 미리 작성된 서식 파일을 찾아 사용하는 것이 훨씬 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-215">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="7cad5-216">예를 들어 *날짜* 에 대한 모든 변형을 수동으로 추가하는 대신 이미 여러 구 목록 값을 포함하고 있는 *날짜* 구 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-216">For example, instead of manually adding all the variations for *Date*, you can use the phrase list template for *Date* as it already includes a number of phrase lists values:</span></span>

![설명 라이브러리](../media/content-understanding/explanation-template.png)
 
<span data-ttu-id="7cad5-218">설명 라이브러리에는 다음을 비롯하여 일반적으로 사용되는 몇 가지 구 목록 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-218">The explanation library includes commonly used phrase list explanations, including:</span></span>

- <span data-ttu-id="7cad5-219">날짜: 달력 날짜, 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-219">Date: Calendar dates, all formats.</span></span> <span data-ttu-id="7cad5-220">텍스트 및 숫자를 포함합니다(예: "2020년 12월 9일").</span><span class="sxs-lookup"><span data-stu-id="7cad5-220">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="7cad5-221">날짜(숫자): 달력 날짜, 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-221">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="7cad5-222">숫자를 포함합니다(예: 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="7cad5-222">Includes numbers (for example 1-11-2020).</span></span>
- <span data-ttu-id="7cad5-223">시간: 12시간 및 24시간 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-223">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="7cad5-224">숫자: 소수점 두 개까지 양수와 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-224">Number: Positive and negative numbers up to 2 decimals.</span></span> 
- <span data-ttu-id="7cad5-225">백분율: 백분율을 나타내는 패턴 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-225">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="7cad5-226">예: 1%, 11%, 100%, 11.11% 등.</span><span class="sxs-lookup"><span data-stu-id="7cad5-226">For example, 1%, 11%, 100%, 11.11%, etc.</span></span>
- <span data-ttu-id="7cad5-227">전화번호: 일반적인 미국 및 국제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-227">Phone number: Common US and International formats.</span></span> <span data-ttu-id="7cad5-228">예: 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000 등.</span><span class="sxs-lookup"><span data-stu-id="7cad5-228">For example, 000 000 0000, 000-000-0000, (000)000-0000, (000) 000-0000, etc.</span></span>
- <span data-ttu-id="7cad5-229">우편 번호: 미국 우편 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-229">Zip code: US Zip code formats.</span></span> <span data-ttu-id="7cad5-230">예: 11111, 11111-1111</span><span class="sxs-lookup"><span data-stu-id="7cad5-230">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="7cad5-231">문장의 첫 번째 단어: 최대 9자 단어의 공통 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-231">First word of sentence: Common patterns for words up to 9 characters.</span></span> 
- <span data-ttu-id="7cad5-232">문장의 끝: 문장의 끝용 일반적인 문장 부호</span><span class="sxs-lookup"><span data-stu-id="7cad5-232">End of sentence: Common punctuation for end of a sentence</span></span>
- <span data-ttu-id="7cad5-233">신용 카드: 일반 신용 카드 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-233">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="7cad5-234">예: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="7cad5-234">For example, 1111-1111-1111-1111.</span></span> 
- <span data-ttu-id="7cad5-235">사회보장번호: 미국 사회보장번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-235">Social security number: US Social Security Number format.</span></span> <span data-ttu-id="7cad5-236">예: 111-11-1111.</span><span class="sxs-lookup"><span data-stu-id="7cad5-236">For example, 111-11-1111.</span></span> 
- <span data-ttu-id="7cad5-237">확인란: 입력된 확인란의 변형을 나타내는 구 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-237">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="7cad5-238">예: _x_, _ _X_ 등.</span><span class="sxs-lookup"><span data-stu-id="7cad5-238">For example, _X_, _ _X_, etc.</span></span>
- <span data-ttu-id="7cad5-239">통화: 주요 국제 기호</span><span class="sxs-lookup"><span data-stu-id="7cad5-239">Currency: Major international symbols.</span></span> <span data-ttu-id="7cad5-240">예: $.</span><span class="sxs-lookup"><span data-stu-id="7cad5-240">For example, $.</span></span> 
- <span data-ttu-id="7cad5-241">전자 메일 CC: 'CC:'라는 용어가 있는 구 목록입니다. 대개 메시지가 전송된 추가 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-241">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of additional people or groups the message was sent to.</span></span>
- <span data-ttu-id="7cad5-242">전자 메일 날짜: '보낸 날짜:'라는 용어가 있는 구 목록입니다. 대개 전자 메일을 보낸 날짜 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-242">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="7cad5-243">전자 메일 인사말: 전자 메일의 일반적인 첫 문장입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-243">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="7cad5-244">전자 메일 받는 사람: '받는 사람:'이라는 용어가 있는 구 목록입니다. 대개 메시지가 전송된 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-244">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span> 
- <span data-ttu-id="7cad5-245">전자 메일 보낸 사람: '보낸 사람:'이라는 용어가 있는 구 목록입니다. 대개 보낸 사람 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-245">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span> 
- <span data-ttu-id="7cad5-246">전자 메일 제목: '제목:'이라는 용어가 있는 구 목록입니다. 대개 전자 메일의 제목 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-246">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span> 

<span data-ttu-id="7cad5-247">설명 라이브러리에는 예제 파일에 레이블이 지정되어 있는 데이터를 사용하는 세 가지 자동 서식 파일 유형도 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-247">The explanation library also includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="7cad5-248">레이블 뒤: 예제 파일의 레이블 뒤에서 발생하는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-248">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="7cad5-249">레이블 전: 예제 파일의 레이블 앞에 있는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-249">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="7cad5-250">레이블: 예제 파일에서 처음 10개 레이블까지입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-250">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="7cad5-251">자동 서식 파일의 작동 방식에 대한 예제를 설명하기 위해 다음 예제 파일에서 레이블 전 설명 서식 파일을 사용하여 모델에 더 많은 정보를 제공하여 보다 정확한 일치를 얻을 수 있도록 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-251">To give you an example of how automatic templates work, in the following example file, we will use the Before Label explanation template to help give the model more information to get a more accurate match.</span></span>

![예제 파일](../media/content-understanding/before-label.png)

<span data-ttu-id="7cad5-253">레이블 전 설명 서식 파일을 선택하면 예제 파일의 레이블 앞에 나타나는 첫 번째 단어 집합이 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-253">When you select the Before Label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="7cad5-254">예를 들어 첫번째 예제 파일에서 식별되는 단어는 “As of”입니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-254">In the example, the words that are identified in the first example file is "As of".</span></span>

![레이블 서식 파일 전](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="7cad5-256">서식 파일에서 **추가** 를 선택하여 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-256">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="7cad5-257">예제 파일을 더 추가하면 추가 단어가 식별되어 구 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-257">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![레이블 추가](../media/content-understanding/before-label-add.png)
 
#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="7cad5-259">설명 라이브러리에서 서식 파일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7cad5-259">To use a template from the explanation library</span></span>

1. <span data-ttu-id="7cad5-260">모델의 **교육** 페이지의 **설명** 구역에서 **신규** 를 선택한 다음 **서식 파일 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-260">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![레이블 전에 추가](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="7cad5-262">**설명 서식 파일** 페이지에서 사용하려는 설명을 선택하고 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-262">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![서식 파일 선택](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="7cad5-264">선택한 서식 파일에 대한 정보는 **설명 만들기** 페이지에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-264">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="7cad5-265">필요한 경우 설명 이름을 편집하고 구 목록에서 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-265">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>  

    ![서식 파일 편집](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="7cad5-267">작업을 끝낸 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7cad5-267">When finished, select **Save**.</span></span>