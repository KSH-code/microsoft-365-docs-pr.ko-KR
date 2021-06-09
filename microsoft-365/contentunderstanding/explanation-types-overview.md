---
title: Microsoft SharePoint Syntex의 설명 유형
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: Microsoft SharePoint Syntex의 구문 목록, 정규식 및 근접 설명 유형에 대해 자세히 알아보세요.
ms.openlocfilehash: cfc217d9e671f2a3a9daa89f80e7d932adeac2c0
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843353"
---
# <a name="explanation-types-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="cadac-103">Microsoft SharePoint Syntex의 설명 유형</span><span class="sxs-lookup"><span data-stu-id="cadac-103">Explanation types in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="cadac-104">설명은 Microsoft SharePoint Syntex의 모델에 대한 이해를 바탕으로 문서에 표시하고 추출하고자 하는 정보를 정의하는데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-104">Explanations are used to help to define the information you want to label and extract in your document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="cadac-105">설명을 만들 때 설명 유형을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-105">When you create an explanation, you need to select an explanation type.</span></span> <span data-ttu-id="cadac-106">이 문서는 다양한 설명 유형과 사용 방법을 이해하는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-106">This article helps you understand the different explanation types and how they're used.</span></span>

![세 가지 설명 유형을 보여 주는 설명 만들기 패널의 스크린샷입니다.](../media/content-understanding/explanation-types.png)

<span data-ttu-id="cadac-108">다음 설명 유형을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-108">These explanation types are available:</span></span>

- <span data-ttu-id="cadac-109">[**구 목록**](#phrase-list): 추출하는 문서나 정보에 사용할 수 있는 단어, 구, 숫자 또는 기타 문자의 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-109">[**Phrase list**](#phrase-list): List of words, phrases, numbers, or other characters you can use in the document or information that you're extracting.</span></span> <span data-ttu-id="cadac-110">예를 들어 *의사 추천* 이란 텍스트 문자열은 식별 중인 모든 의료 추천 문서에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-110">For example, the text string *referring doctor* is in all Medical Referral documents you're identifying.</span></span> <span data-ttu-id="cadac-111">또는 식별 중인 모든 의료 추천 문서에서 의사 추천의 *전화 번호* 를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-111">Or the *phone number* of the referring doctor from all Medical Referral documents that you're identifying.</span></span>

- <span data-ttu-id="cadac-112">[**정규식**](#regular-expression): 패턴 일치 표기법을 사용하여 특정 문자 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-112">[**Regular expression**](#regular-expression): Uses a pattern-matching notation to find specific character patterns.</span></span> <span data-ttu-id="cadac-113">예를 들어 정규식을 사용하여 문서 집합에서 *전자 메일 주소* 패턴의 모든 인스턴스를 찾을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-113">For example, you can use a regular expression to find all instances of an *email address* pattern in a set of documents.</span></span>

- <span data-ttu-id="cadac-114">[**근접**](#proximity): 설명이 서로 얼마나 근접한지 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-114">[**Proximity**](#proximity): Describes how close explanations are to each other.</span></span> <span data-ttu-id="cadac-115">예를 들어 *번지 수* 의 구 목록은 *길 이름* 바로 전에 나오고 토큰은 둘 사이에 존재하지 않습니다.(토큰에 대한 자세한 정보는 본 문서의 뒷부분에 나옵니다.)</span><span class="sxs-lookup"><span data-stu-id="cadac-115">For example, a *street number* phrase list goes right before the *street name* phrase list, with no tokens in between (you'll learn about tokens later in this article).</span></span> <span data-ttu-id="cadac-116">근사 유형을 사용하려면 모델에 두 개 이상의 설명이 있어야 하고, 그렇지 않으면 해당 옵션을 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-116">Using the proximity type requires you to have at least two explanations in your model or the option will be disabled.</span></span>

## <a name="phrase-list"></a><span data-ttu-id="cadac-117">구 목록</span><span class="sxs-lookup"><span data-stu-id="cadac-117">Phrase list</span></span>

<span data-ttu-id="cadac-118">일반적으로 구 목록 설명 형식은 모델을 통해 문서를 식별하고 분류하는 데 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-118">A phrase list explanation type is typically used to identify and classify a document through your model.</span></span> <span data-ttu-id="cadac-119">*의사 추천* 레이블 예제에 설명 된 바와 같이 식별 중인 문서에서 일관되게 나타나는 단어, 구, 숫자 또는 문자의 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-119">As described in the *referring doctor* label example, it's a string of words, phrases, numbers, or characters that is consistently in the documents that you're identifying.</span></span>

<span data-ttu-id="cadac-120">요구 사항은 아니지만 캡처하는 구가 문서의 일관된 위치에 있는 경우 설명으로 성공률을 높일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-120">While not a requirement, you can achieve better success with your explanation if the phrase you're capturing is located in a consistent location in your document.</span></span> <span data-ttu-id="cadac-121">예를 들어, *의사 추천* 이란 레이블이 문서의 첫 번째 문단에 일관되게 배치되어 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-121">For example, the *referring doctor* label might be consistently located in the first paragraph of the document.</span></span> <span data-ttu-id="cadac-122">또한 **[문서에서 구가 발생할 위치 구성](explanation-types-overview.md#configure-where-phrases-occur-in-the-document)** 고급 설정을 사용하여 구가 위치한 특정 영역을 선택할 수 있습니다. 특히, 구가 문서의 여러 위치에서 발생할 가능성이 있는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-122">You can also use the **[Configure where phrases occur in the document](explanation-types-overview.md#configure-where-phrases-occur-in-the-document)** advanced setting to select specific areas where the phrase is located, especially if there's a chance that the phrase might occur in multiple locations in your document.</span></span>

<span data-ttu-id="cadac-123">레이블을 식별하는데 대/소문자 구분이 필요하다면, 구 목록 유형을 사용하하면 **정확한 대소문자 사용** 체크박스를 선택하여 이를 설명에 지정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-123">If case sensitivity is a requirement in identifying your label, using the phrase list type allows you to specify it in your explanation by selecting the **Only exact capitalization** checkbox.</span></span>

![대/소문자 구분](../media/content-understanding/case-sensitivity.png)

<span data-ttu-id="cadac-125">구 유형은 날짜, 전화번호, 신용 카드 번호 등 다양한 형식으로 정보를 식별하고 추출하는 설명을 만들 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-125">A phrase type is especially useful when you create an explanation that identifies and extracts information in different formats, such as dates, phone numbers, and credit card numbers.</span></span> <span data-ttu-id="cadac-126">예를 들어 날짜는 다양한 형식(1/1/2020, 1-1-2020, 01/01/20, 01/01/2020 혹은 2020년 1월 1일)으로 표시될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-126">For example, a date can be displayed in many different formats (1/1/2020, 1-1-2020, 01/01/20, 01/01/2020, or Jan 1,2020).</span></span> <span data-ttu-id="cadac-127">구 목록을 정의하면 식별하고 추출하려는 데이터의 가능한 변형을 캡처하여 설명을 더 효율적으로 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-127">Defining a phrase list makes your explanation more efficient by capturing any possible variations in the data that you're trying to identify and extract.</span></span>

<span data-ttu-id="cadac-128">*전화 번호* 예제의 경우 모델이 식별하는 모든 의료 추천 문서에서 각 추천 의사의 전화 번호를 추출합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-128">For the *phone number* example, you extract the phone number for each referring doctor from all Medical Referral documents that the model identifies.</span></span> <span data-ttu-id="cadac-129">설명을 만들 때 가능한 변형을 캡처할 수 있도록 문서에 표시할 수 있는 다양한 전화 번호 형식을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-129">When you create the explanation, type the different formats a phone number might display in your document so that you're able to capture possible variations.</span></span>

![전화번호 구 패턴](../media/content-understanding/pattern-list.png)

<span data-ttu-id="cadac-131">이 예에서는 **고급 설정** 에서 **0-9 사이의 임의의 수** 확인란을 선택하여 구 목록에 사용된 각 "0" 값을 0부터 9까지의 숫자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-131">For this example, in **Advanced Settings** select the **Any digit from 0-9** checkbox to recognize each "0" value used in your phrase list to be any digit from 0 through 9.</span></span>

![0부터 9 사이 아무 숫자](../media/content-understanding/digit-identity.png)

<span data-ttu-id="cadac-133">마찬가지로 텍스트 문자를 포함하는 구 목록을 만들 경우 **a-z 사이의 임의의 문자** 확인란을 선택하여 구 목록에 사용된 각 "a" 문자를 "a"에서 "z"까지의 문자로 인식합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-133">Similarly, if you create a phrase list that includes text characters, select the **Any letter from a-z** checkbox to recognize each "a" character used in the phrase list to be any character from "a" to "z".</span></span>

<span data-ttu-id="cadac-134">예를 들어 **날짜** 구 목록을 만들 때 *2020년 1월 1일* 과 같은 날짜 서식이 인식되도록 하려면 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-134">For example, if you create a **Date** phrase list and you want to make sure that a date format such as *Jan 1, 2020* is recognized, you need to:</span></span>

- <span data-ttu-id="cadac-135">구 목록에 *aaa 0, 0000* 및 *aaa 00, 0000* 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-135">Add *aaa 0, 0000* and *aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="cadac-136">**a부터 z 사이 아무 문자** 를 선택했는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-136">Make sure that **Any letter from a-z** is also selected.</span></span>

![a부터 z 사이 아무 문자](../media/content-understanding/any-letter.png)

<span data-ttu-id="cadac-138">구 목록에 대문자 표시 요구 사항이 있는 경우 **정확한 대문자 표시** 확인란을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-138">If you have capitalization requirements in your phrase list, you can select the **Only exact capitalization** checkbox.</span></span> <span data-ttu-id="cadac-139">날짜 예제의 경우 월의 첫 글자를 대문자로 표기해야 하는 경우 다음을 수행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-139">For the date example, if you require the first letter of the month to be capitalized, you need to:</span></span>

- <span data-ttu-id="cadac-140">구 목록에 *Aaa 0, 0000* 및 *Aaa 00, 0000* 을 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-140">Add *Aaa 0, 0000* and *Aaa 00, 0000* to your phrase list.</span></span>
- <span data-ttu-id="cadac-141">**정확한 대소문자 사용** 이 선택되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-141">Make sure that **Only exact capitalization** is also selected.</span></span>

![정확한 대소문자 사용](../media/content-understanding/exact-caps.png)

> [!NOTE]
> <span data-ttu-id="cadac-143">구 목록 설명을 수동으로 만드는 대신 [설명 라이브러리](explanation-types-overview.md#use-explanation-templates)를 사용하여 *날짜*, *전화 번호* 또는 *신용 카드 번호* 와 같은 일반적인 구 목록 서식 파일을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-143">Instead of manually creating a phrase list explanation, use the [explanation library](explanation-types-overview.md#use-explanation-templates) to use phrase list templates for a common phrase list, such as *date*, *phone number*, or *credit card number*.</span></span>

## <a name="regular-expression"></a><span data-ttu-id="cadac-144">정규식</span><span class="sxs-lookup"><span data-stu-id="cadac-144">Regular expression</span></span>

<span data-ttu-id="cadac-145">정규식 설명 형식을 사용하면 문서에서 특정 텍스트 문자열을 찾고 식별하는 데 도움이 되는 패턴을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-145">A regular expression explanation type allows you to create patterns that help find and identify certain text strings in documents.</span></span> <span data-ttu-id="cadac-146">정규식을 사용하여 대량의 텍스트를 신속하게 구문 분석하여 다음을 수행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-146">You can use regular expressions to quickly parse large amounts of text to:</span></span>

- <span data-ttu-id="cadac-147">특정 문자 패턴을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-147">Find specific character patterns.</span></span>
- <span data-ttu-id="cadac-148">텍스트의 유효성을 검사하여 미리 정의된 패턴(예: 전자 메일 주소)과 일치하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-148">Validate text to ensure that it matches a predefined pattern (such as an email address).</span></span>
- <span data-ttu-id="cadac-149">텍스트 하위 문자열을 추출, 편집, 바꾸기 또는 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-149">Extract, edit, replace, or delete text substrings.</span></span>

<span data-ttu-id="cadac-150">정규식 유형은 전자 메일 주소, 은행 계좌 번호 또는 URL과 같은 유사한 형식의 정보를 식별하고 추출하는 설명을 만들 때 특히 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-150">A regular expression type is especially useful when you create an explanation that identifies and extracts information in similar formats, such as email addresses, bank account numbers, or URLs.</span></span> <span data-ttu-id="cadac-151">예를 들어 megan@contoso.com와 같은 전자 메일 주소가 특정 패턴으로 표시됩니다("megan"이 첫 번째 부분이고 "com"이 마지막 부분임).</span><span class="sxs-lookup"><span data-stu-id="cadac-151">For example, an email address, such as megan@contoso.com, is displayed in a certain pattern ("megan" is the first part, and "com" is the last part).</span></span>

<span data-ttu-id="cadac-152">전자 메일 주소의 정규식은 **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+[A-Za-z]{2,6}** 입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-152">The regular expression for an email address is: **[A-Za-z0-9._%-]+@[A-Za-z0-9.-]+.[A-Za-z]{2,6}**.</span></span>

<span data-ttu-id="cadac-153">이 식은 다음 순서로 5개의 부분으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-153">This expression consists of five parts, in this order:</span></span>

1. <span data-ttu-id="cadac-154">다음 문자의 양:</span><span class="sxs-lookup"><span data-stu-id="cadac-154">Any amount of the following characters:</span></span>

   <span data-ttu-id="cadac-p112">a. a에서 z까지의 문자</span><span class="sxs-lookup"><span data-stu-id="cadac-p112">a. Letters from a to z</span></span>

   <span data-ttu-id="cadac-p113">b. 0-9의 숫자</span><span class="sxs-lookup"><span data-stu-id="cadac-p113">b. Numbers from 0-9</span></span>

   <span data-ttu-id="cadac-p114">c. 마침표, 밑줄, 백분율 또는 대시</span><span class="sxs-lookup"><span data-stu-id="cadac-p114">c. Period, underscore, percent, or dash</span></span>

2. <span data-ttu-id="cadac-161">@ 기호</span><span class="sxs-lookup"><span data-stu-id="cadac-161">The @ symbol</span></span>

3. <span data-ttu-id="cadac-162">전자 메일 주소의 첫 부분과 동일한 문자의 양</span><span class="sxs-lookup"><span data-stu-id="cadac-162">Any amount of the same characters as the first part of the email address</span></span>

4. <span data-ttu-id="cadac-163">마침표</span><span class="sxs-lookup"><span data-stu-id="cadac-163">A period</span></span>

5. <span data-ttu-id="cadac-164">2~6자</span><span class="sxs-lookup"><span data-stu-id="cadac-164">Two to six letters</span></span>

<span data-ttu-id="cadac-165">정규식 설명 형식을 추가하려면 다음을 수행합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-165">To add a regular expression explanation type:</span></span>

1. <span data-ttu-id="cadac-166">**설명 만들기** 패널의 **설명 유형** 에서 **정규식** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-166">From the **Create an explanation** panel, under **Explanation type**, select **Regular expression**.</span></span>

   ![정규식이 선택된 설명 만들기 패널을 보여 주는 스크린샷입니다.](../media/content-understanding/create-regular-expression.png)

2. <span data-ttu-id="cadac-168">**정규식** 텍스트 상자에 식을 입력하거나 **템플릿에서 정규식 추가** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-168">You can either type an expression in the **Regular expression** text box or select **Add a regular expression from a template**.</span></span>

   <span data-ttu-id="cadac-169">템플릿을 사용하여 정규식을 추가하면 텍스트 상자에 이름과 정규식이 자동으로 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-169">When you add a regular expression by using a template, it automatically adds the name and the regular expression to the text box.</span></span> <span data-ttu-id="cadac-170">예를 들어 **전자 메일 주소** 템플릿을 선택하면 **설명 만들기** 패널이 채워집니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-170">For example, if you choose the **Email address** template, the **Create an explanation** panel will be populated.</span></span>

   ![전자 메일 주소 템플릿이 적용된 설명 만들기 패널을 보여 주는 스크린샷입니다.](../media/content-understanding/create-regular-expression-email.png)

### <a name="limitations"></a><span data-ttu-id="cadac-172">제한 사항</span><span class="sxs-lookup"><span data-stu-id="cadac-172">Limitations</span></span>

<span data-ttu-id="cadac-173">다음 표는 현재 정규식 패턴에 사용할 수 없는 인라인 문자 옵션을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-173">The following table shows inline character options that currently are not available for use in regular expression patterns.</span></span>

|<span data-ttu-id="cadac-174">옵션</span><span class="sxs-lookup"><span data-stu-id="cadac-174">Option</span></span>  |<span data-ttu-id="cadac-175">시/도</span><span class="sxs-lookup"><span data-stu-id="cadac-175">State</span></span>  |<span data-ttu-id="cadac-176">현재 기능</span><span class="sxs-lookup"><span data-stu-id="cadac-176">Current functionality</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="cadac-177">대/소문자 구분</span><span class="sxs-lookup"><span data-stu-id="cadac-177">Case sensitivity</span></span> | <span data-ttu-id="cadac-178">현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-178">Currently not supported.</span></span> | <span data-ttu-id="cadac-179">수행되는 모든 일치 항목은 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-179">All matches performed are case-insensitive.</span></span>  |
|<span data-ttu-id="cadac-180">줄 앵커</span><span class="sxs-lookup"><span data-stu-id="cadac-180">Line anchors</span></span>     | <span data-ttu-id="cadac-181">현재 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-181">Currently not supported.</span></span> | <span data-ttu-id="cadac-182">일치가 발생해야 하는 문자열의 특정 위치를 지정할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-182">Unable to specify a specific position in a string where a match must occur.</span></span>   |

## <a name="proximity"></a><span data-ttu-id="cadac-183">근접</span><span class="sxs-lookup"><span data-stu-id="cadac-183">Proximity</span></span>

<span data-ttu-id="cadac-184">근접 설명 유형은 사용자의 모델이 각각의 데이터가 서로 얼마나 근접해 있는지를 규정할 수 있도록 도와줍니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-184">The proximity explanation type helps your model identify data by defining how close another piece of data is to it.</span></span> <span data-ttu-id="cadac-185">예를 들어 모델에서 고객 *주소 번호* 및 *전화 번호* 둘 다에 레이블을 지정하는 두 가지 설명을 정의했다고 가정합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-185">For example, in your model say you have defined two explanations that label both the customer *street address number* and *phone number*.</span></span>

<span data-ttu-id="cadac-186">또한 고객 전화 번호는 항상 거리 주소 번호 앞에 표시된다는 것을 파악했습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-186">Notice that customer phone numbers always appear before the street address number.</span></span>

<span data-ttu-id="cadac-187">Alex Wilburn</span><span class="sxs-lookup"><span data-stu-id="cadac-187">Alex Wilburn</span></span><br>
<span data-ttu-id="cadac-188">555-555-5555</span><span class="sxs-lookup"><span data-stu-id="cadac-188">555-555-5555</span></span><br>
<span data-ttu-id="cadac-189">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cadac-189">One Microsoft Way</span></span><br>
<span data-ttu-id="cadac-190">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="cadac-190">Redmond, WA 98034</span></span><br>

<span data-ttu-id="cadac-191">근접 설명을 사용하여 전화 번호 설명이 문서에서 거리 주소 번호를 식별해내기에 근접하지 않은 설명이라는 것을 규정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-191">Use the proximity explanation to define how far away the phone number explanation is to better identify the street address number in your documents.</span></span>

![근접 설명](../media/content-understanding/proximity.png)

#### <a name="what-are-tokens"></a><span data-ttu-id="cadac-193">토큰이란?</span><span class="sxs-lookup"><span data-stu-id="cadac-193">What are tokens?</span></span>

<span data-ttu-id="cadac-194">근접 설명 유형을 사용하려면 토큰이 무엇인지 이해해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-194">To use the proximity explanation type, you need to understand what a token is.</span></span> <span data-ttu-id="cadac-195">토큰 수는 근접 설명이 한 설명에서 다른 설명까지의 거리를 측정하는 방법입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-195">The number of tokens is how the proximity explanation measures distance from one explanation to another.</span></span> <span data-ttu-id="cadac-196">토큰은 문자와 숫자의 연속 범위(공백이나 문장 부호 제외)입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-196">A token is a continuous span (not including spaces or punctuation) of letters and numbers.</span></span>

<span data-ttu-id="cadac-197">다음 표는 한 개의 구에서 토큰 수를 확인하는 방법에 대해 예를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-197">The following table shows examples for how to determine the number of tokens in a phrase.</span></span>

|<span data-ttu-id="cadac-198">구</span><span class="sxs-lookup"><span data-stu-id="cadac-198">Phrase</span></span>|<span data-ttu-id="cadac-199">토큰 수</span><span class="sxs-lookup"><span data-stu-id="cadac-199">Number of tokens</span></span>|<span data-ttu-id="cadac-200">설명</span><span class="sxs-lookup"><span data-stu-id="cadac-200">Explanation</span></span>|
|--|--|--|
|`Dog`|<span data-ttu-id="cadac-201">1</span><span class="sxs-lookup"><span data-stu-id="cadac-201">1</span></span>|<span data-ttu-id="cadac-202">문장 부호나 공백이 없는 단일 단어입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-202">A single word with no punctuation or spaces.</span></span>|
|`RMT33W`|<span data-ttu-id="cadac-203">1</span><span class="sxs-lookup"><span data-stu-id="cadac-203">1</span></span>|<span data-ttu-id="cadac-204">레코드 로케이터 번호</span><span class="sxs-lookup"><span data-stu-id="cadac-204">A record locator number.</span></span> <span data-ttu-id="cadac-205">숫자와 문자가 포함될 수 있지만 문장 부호는 포함되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-205">It might include numbers and letters, but doesn't have punctuation.</span></span>|
|`425-555-5555`|<span data-ttu-id="cadac-206">5</span><span class="sxs-lookup"><span data-stu-id="cadac-206">5</span></span>|<span data-ttu-id="cadac-207">전화 번호</span><span class="sxs-lookup"><span data-stu-id="cadac-207">A phone number.</span></span> <span data-ttu-id="cadac-208">각 문장 부호 기호는 단일 토큰이므로 `425-555-5555`의 경우 5개의 토큰이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-208">Each punctuation mark is a single token, so `425-555-5555` is 5 tokens:</span></span><br>`425`<br>`-`<br>`555`<br>`-`<br>`5555` |
|`https://luis.ai`|<span data-ttu-id="cadac-209">7</span><span class="sxs-lookup"><span data-stu-id="cadac-209">7</span></span>|`https`<br>`:`<br>`/`<br>`/`<br>`luis`<br>`.`<br>`ai`<br>|

#### <a name="configure-the-proximity-explanation-type"></a><span data-ttu-id="cadac-210">근접 설명 유형 구성</span><span class="sxs-lookup"><span data-stu-id="cadac-210">Configure the proximity explanation type</span></span>

<span data-ttu-id="cadac-211">예를 들어 근접 설정을 구성하여 *거리 주소 번호* 설명에서 *전화 번호* 설명에 있는 토큰 수의 범위를 정의합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-211">For the example, configure the proximity setting to define the range of the number of tokens in the *phone number* explanation from the *street address number* explanation.</span></span> <span data-ttu-id="cadac-212">전화 번호와 거리 주소 번호 사이에는 토큰이 없기 때문에 최소 범위는 "0" 이라는 것을 알 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-212">Notice that the minimum range is "0", because there are no tokens between the phone number and street address number.</span></span>

<span data-ttu-id="cadac-213">그러나 샘플 문서의 일부 전화 번호에는 *(휴대폰)* 이 추가되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-213">But some phone numbers in the sample documents are appended with *(mobile)*.</span></span>

<span data-ttu-id="cadac-214">Nestor Wilke</span><span class="sxs-lookup"><span data-stu-id="cadac-214">Nestor Wilke</span></span><br>
<span data-ttu-id="cadac-215">111-111-1111(휴대폰)</span><span class="sxs-lookup"><span data-stu-id="cadac-215">111-111-1111 (mobile)</span></span><br>
<span data-ttu-id="cadac-216">One Microsoft Way</span><span class="sxs-lookup"><span data-stu-id="cadac-216">One Microsoft Way</span></span><br>
<span data-ttu-id="cadac-217">Redmond, WA 98034</span><span class="sxs-lookup"><span data-stu-id="cadac-217">Redmond, WA 98034</span></span><br>

<span data-ttu-id="cadac-218">*(휴대폰)* 에는 세 개의 토큰이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-218">There are three tokens in *(mobile)*:</span></span>

|<span data-ttu-id="cadac-219">구</span><span class="sxs-lookup"><span data-stu-id="cadac-219">Phrase</span></span>|<span data-ttu-id="cadac-220">토큰 수</span><span class="sxs-lookup"><span data-stu-id="cadac-220">Token count</span></span>|
|--|--|
|<span data-ttu-id="cadac-221">(</span><span class="sxs-lookup"><span data-stu-id="cadac-221">(</span></span>|<span data-ttu-id="cadac-222">1</span><span class="sxs-lookup"><span data-stu-id="cadac-222">1</span></span>|
|<span data-ttu-id="cadac-223">휴대폰</span><span class="sxs-lookup"><span data-stu-id="cadac-223">mobile</span></span>|<span data-ttu-id="cadac-224">2</span><span class="sxs-lookup"><span data-stu-id="cadac-224">2</span></span>|
|<span data-ttu-id="cadac-225">)</span><span class="sxs-lookup"><span data-stu-id="cadac-225">)</span></span>|<span data-ttu-id="cadac-226">3</span><span class="sxs-lookup"><span data-stu-id="cadac-226">3</span></span>|

<span data-ttu-id="cadac-227">근접 설정이 0에서 3의 범위를 갖도록 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-227">Configure the proximity setting to have a range of 0 through 3.</span></span>

![근접의 예](../media/content-understanding/proximity-example.png)

## <a name="configure-where-phrases-occur-in-the-document"></a><span data-ttu-id="cadac-229">문서에서 구가 발생하는 위치 구성</span><span class="sxs-lookup"><span data-stu-id="cadac-229">Configure where phrases occur in the document</span></span>

<span data-ttu-id="cadac-230">설명을 만드는 경우 기본적으로 전체 문서에서 추출하려는 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-230">When you create an explanation, by default the entire document is searched for the phrase you're trying to extract.</span></span> <span data-ttu-id="cadac-231">그러나 **문서에서 이 구가 발생하는 위치** 고급 설정을 사용하면 문서에서 이러한 구가 발생하는 위치를 설정하는 데 도움이 될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-231">However, you can use the **Where these phrases occur** advanced setting to help in isolating a specific location in the document that a phrase occurs.</span></span> <span data-ttu-id="cadac-232">이 설정은 문서의 다른 위치에 유사한 구의 인스턴스가 표시될 수 있고 올바른 구가 선택되어 있는지 확인하려는 경우에 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-232">This setting is useful in situations where similar instances of a phrase might appear somewhere else in the document, and you want to make sure that the correct one is selected.</span></span>

<span data-ttu-id="cadac-233">의료 추천 문서 예제를 참조하면 *추천 의사* 는 항상 문서의 첫 번째 단락에서 언급됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-233">Referring to our Medical Referral document example, the *referring doctor* is always mentioned in the first paragraph of the document.</span></span> <span data-ttu-id="cadac-234">이 예에서는 **이러한 구가 발생하는 위치** 설정을 사용하여 문서의 시작 부분 또는 이 구가 발생할 수 있는 다른 위치에서만 이 레이블을 검색하도록 설명을 구성할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-234">With the **Where these phrases occur** setting, in this example you can configure your explanation to search for this label only in the beginning section of the document, or any other location in which it might occur.</span></span>

![이러한 구가 발생하는 위치 설정](../media/content-understanding/phrase-location.png)

<span data-ttu-id="cadac-236">이 설정에 대해 다음 옵션 중에서 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-236">You can choose the following options for this setting:</span></span>

- <span data-ttu-id="cadac-237">파일의 모든 위치: 전체 문서에서 구를 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-237">Anywhere in the file: The entire document is searched for the phrase.</span></span>

- <span data-ttu-id="cadac-238">파일의 시작: 문서가 처음부터 구 위치까지 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-238">Beginning of the file:  The document is searched from the beginning to the phrase location.</span></span>

   ![파일의 시작 부분](../media/content-understanding/beginning-of-file.png)

    <span data-ttu-id="cadac-240">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-240">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cadac-241">**끝 위치** 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-241">The **End position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="cadac-242">**끝 위치** 값을 업데이트하여 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-242">You can update the **End position** value as well to adjust the selected area.</span></span>

   ![파일 위치 상자의 시작 부분](../media/content-understanding/beginning-box.png)

- <span data-ttu-id="cadac-244">파일의 끝: 문서가 끝부터 구 위치까지 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-244">End of the file: The document is searched from the end to the phrase location.</span></span>

   ![파일의 끝 부분](../media/content-understanding/end-of-file.png)

    <span data-ttu-id="cadac-246">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-246">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cadac-247">**시작 위치** 값이 업데이트되어 선택한 영역에 포함된 토큰 수가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-247">The **Starting position** value will update to show the number of tokens your selected area includes.</span></span> <span data-ttu-id="cadac-248">시작 위치 값을 업데이트하고 선택한 영역을 조정할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-248">You can update the Starting position value as well to adjust the selected area.</span></span>

   ![파일 끝 상자의 끝](../media/content-understanding/end-box.png)

- <span data-ttu-id="cadac-250">사용자 지정 범위: 문서가 지정된 구 위치 범위 내에서 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-250">Custom range: The document is searched within a specified range for the phrase location.</span></span>

   ![사용자 지정 범위](../media/content-understanding/custom-file.png)

    <span data-ttu-id="cadac-252">뷰어에서 구가 발생하는 위치를 포함하기 위해 선택 상자를 수동으로 조정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-252">In the viewer, you can manually adjust the select box to include the location where the phase occurs.</span></span> <span data-ttu-id="cadac-253">이 설정의 경우 시작 **시작** 과 **끝** 위치를 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-253">For this setting, you need to select a **Start** and an **End** position.</span></span> <span data-ttu-id="cadac-254">이러한 값은 문서의 시작 부분의 토큰 수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-254">These values represent the number of tokens from the beginning of the document.</span></span> <span data-ttu-id="cadac-255">이러한 값은 수동으로 입력할 수 있지만 뷰어에서 선택 상자를 수동으로 조정하는 것이 더 쉽습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-255">While you can manually enter in these values, it's easier to manually adjust the select box in the viewer.</span></span>

## <a name="use-explanation-templates"></a><span data-ttu-id="cadac-256">설명 서식 파일 사용</span><span class="sxs-lookup"><span data-stu-id="cadac-256">Use explanation templates</span></span>

<span data-ttu-id="cadac-257">설명에 대한 다양한 구 목록 값을 수동으로 추가할 수 있지만, 설명 라이브러리에서 미리 작성된 서식 파일을 찾아 사용하는 것이 훨씬 쉬울 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-257">While you can manually add various phrase list values for your explanation, it can be easier to use the templates provided to you in the explanation library.</span></span>

<span data-ttu-id="cadac-258">예를 들어 *날짜* 에 대한 모든 변형을 수동으로 추가하는 대신 이미 많은 구 목록 값을 포함하고 있는 *날짜* 에 대한 구 목록 템플릿을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-258">For example, instead of manually adding all the variations for *date*, you can use the phrase list template for *date* because it already includes many phrase lists values:</span></span>

![설명 라이브러리](../media/content-understanding/explanation-template.png)

<span data-ttu-id="cadac-260&quot;>설명 라이브러리에는 다음을 비롯하여 일반적으로 사용되는 *구 목록* 설명이 포함되어 있습니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cadac-260&quot;>The explanation library includes commonly used *phrase list* explanations, including:</span></span>

- <span data-ttu-id=&quot;cadac-261&quot;>날짜: 달력 날짜, 모든 형식입니다.</span><span class=&quot;sxs-lookup&quot;><span data-stu-id=&quot;cadac-261&quot;>Date: Calendar dates, all formats.</span></span> <span data-ttu-id=&quot;cadac-262&quot;>텍스트 및 숫자를 포함합니다(예: &quot;2020년 12월 9일").</span><span class="sxs-lookup"><span data-stu-id="cadac-262">Includes text and numbers (for example, "Dec 9, 2020").</span></span>
- <span data-ttu-id="cadac-263">날짜(숫자): 달력 날짜, 모든 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-263">Date (numeric): Calendar dates, all formats.</span></span> <span data-ttu-id="cadac-264">숫자를 포함합니다(예: 1-11-2020).</span><span class="sxs-lookup"><span data-stu-id="cadac-264">Includes numbers (for example, 1-11-2020).</span></span>
- <span data-ttu-id="cadac-265">시간: 12시간 및 24시간 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-265">Time: 12 and 24 hour formats.</span></span>
- <span data-ttu-id="cadac-266">숫자: 최대 2자리 소수점까지 양수 및 음수입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-266">Number: Positive and negative numbers up to two decimals.</span></span>
- <span data-ttu-id="cadac-267">백분율: 백분율을 나타내는 패턴 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-267">Percentage: A list of patterns representing a percentage.</span></span> <span data-ttu-id="cadac-268">예: 1%, 11%, 100% 또는 11.11%입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-268">For example, 1%, 11%, 100%, or 11.11%.</span></span>
- <span data-ttu-id="cadac-269">전화번호: 일반적인 미국 및 국제 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-269">Phone number: Common US and International formats.</span></span> <span data-ttu-id="cadac-270">예: 000 000 0000, 000-000-0000, (000)000-0000 혹은 (000) 000-0000 등입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-270">For example, 000 000 0000, 000-000-0000, (000)000-0000, or (000) 000-0000.</span></span>
- <span data-ttu-id="cadac-271">우편 번호: 미국 우편 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-271">Zip code: US Zip code formats.</span></span> <span data-ttu-id="cadac-272">예: 11111, 11111-1111</span><span class="sxs-lookup"><span data-stu-id="cadac-272">For example, 11111, 11111-1111.</span></span>
- <span data-ttu-id="cadac-273">문장의 첫 번째 단어: 최대 9자의 단어에 대한 일반적인 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-273">First word of sentence: Common patterns for words up to nine characters.</span></span>
- <span data-ttu-id="cadac-274">문장의 끝: 문장의 끝에 대한 일반적인 문장 부호입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-274">End of sentence: Common punctuation for end of a sentence.</span></span>
- <span data-ttu-id="cadac-275">신용 카드: 일반 신용 카드 번호 형식입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-275">Credit card: Common credit card number formats.</span></span> <span data-ttu-id="cadac-276">예: 1111-1111-1111-1111.</span><span class="sxs-lookup"><span data-stu-id="cadac-276">For example, 1111-1111-1111-1111.</span></span>
- <span data-ttu-id="cadac-p132">사회 보장 번호: 미국 사회 보장 번호 형식입니다. 예를 들어 111-11-1111입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-p132">Social security number: US Social Security Number format. For example, 111-11-1111.</span></span>
- <span data-ttu-id="cadac-279">확인란: 채워진 확인란의 변형을 나타내는 구 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-279">Checkbox: A phrase list representing variations on a filled in checkbox.</span></span> <span data-ttu-id="cadac-280">예: _x_, _ _X_ 입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-280">For example, _X_, _ _X_.</span></span>
- <span data-ttu-id="cadac-281">통화: 주요 국제 기호</span><span class="sxs-lookup"><span data-stu-id="cadac-281">Currency: Major international symbols.</span></span> <span data-ttu-id="cadac-282">예: $.</span><span class="sxs-lookup"><span data-stu-id="cadac-282">For example, $.</span></span>
- <span data-ttu-id="cadac-283">전자 메일 CC: 'CC:'라는 용어가 있는 구 목록으로 메시지가 전송된 다른 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있는 경우가 많습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-283">Email CC: A phrase list with the term 'CC:', often found near the names or email addresses of other people or groups the message was sent to.</span></span>
- <span data-ttu-id="cadac-284">전자 메일 날짜: '보낸 날짜:'라는 용어가 있는 구 목록입니다. 대개 전자 메일을 보낸 날짜 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-284">Email date: A phrase list with the term 'Sent on:', often found near the date the email was sent.</span></span>
- <span data-ttu-id="cadac-285">전자 메일 인사말: 전자 메일의 일반적인 첫 문장입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-285">Email greeting: Common opening lines for emails.</span></span>
- <span data-ttu-id="cadac-286">전자 메일 받는 사람: '받는 사람:'이라는 용어가 있는 구 목록입니다. 대개 메시지가 전송된 사용자 또는 그룹의 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-286">Email recipient: A phrase list with the term 'To:', often found near the names or email addresses of people or groups the message was sent to.</span></span>
- <span data-ttu-id="cadac-287">전자 메일 보낸 사람: '보낸 사람:'이라는 용어가 있는 구 목록입니다. 대개 보낸 사람 이름 또는 전자 메일 주소 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-287">Email sender: A phrase list with the term 'From:', often found near the sender's name or email address.</span></span>
- <span data-ttu-id="cadac-288">전자 메일 제목: '제목:'이라는 용어가 있는 구 목록입니다. 대개 전자 메일의 제목 근처에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-288">Email subject: A phrase list with the term 'Subject:', often found near the email's subject.</span></span>

<span data-ttu-id="cadac-289">설명 라이브러리에는 다음을 비롯하여 또한 일반적으로 사용되는 *정규식* 설명이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-289">The explanation library also includes commonly used *regular expression* explanations, including:</span></span>

- <span data-ttu-id="cadac-290">6~17자리 숫자: 6~17자리 모든 숫자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-290">6 to 17 digit numbers: Matches any number from 6 to 17 digits long.</span></span> <span data-ttu-id="cadac-291">미국 은행 계좌 번호는 이 패턴에 맞습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-291">US bank account numbers fit this pattern.</span></span>
- <span data-ttu-id="cadac-292">전자 메일 주소: meganb@contoso.com과 같은 일반적인 유형의 전자 메일 주소와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-292">Email address: Matches a common type of email address like meganb@contoso.com.</span></span>
- <span data-ttu-id="cadac-293">미국 납세자 ID 번호: 9부터 시작하는 3자리 숫자와 7 또는 8부터 시작하는 6자리 숫자와 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-293">US taxpayer ID number: Matches a three-digit number starting with 9 followed by a 6 digit number starting with 7 or 8.</span></span>
- <span data-ttu-id="cadac-294">웹 주소(URL): http:// 또는 https://로 시작하는 웹 주소의 형식과 일치합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-294">Web address (URL): Matches the format of a web address, starting with http:// or https://.</span></span>

<span data-ttu-id="cadac-295">또한 설명 라이브러리에는 예제 파일에 레이블을 지정한 데이터를 사용하는 세 가지 자동 템플릿 형식이 포함되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-295">In addition, the explanation library includes three automatic template types that work with the data you've labeled in your example files:</span></span>

- <span data-ttu-id="cadac-296">레이블 뒤: 예제 파일의 레이블 뒤에서 발생하는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-296">After label: The words or characters that occur after the labels in the example files.</span></span>
- <span data-ttu-id="cadac-297">레이블 전: 예제 파일의 레이블 앞에 있는 단어 또는 문자입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-297">Before label: The words or characters that occur before the labels in the example files.</span></span>
- <span data-ttu-id="cadac-298">레이블: 예제 파일에서 처음 10개 레이블까지입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-298">Labels: Up to the first 10 labels from the example files.</span></span>

<span data-ttu-id="cadac-299">자동 템플릿의 작동 방식에 대한 예제를 제공하기 위해 다음 예제 파일에서 이전 레이블 설명 템플릿을 사용하여 모델에 보다 정확한 일치를 얻기 위한 추가 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-299">To give you an example of how automatic templates work, in the following example file, we'll use the Before label explanation template to help give the model more information to get a more accurate match.</span></span>

![예제 파일](../media/content-understanding/before-label.png)

<span data-ttu-id="cadac-301">이전 레이블 설명 템플릿을 선택하면 예제 파일의 레이블 앞에 나타나는 첫 번째 단어 집합을 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-301">When you select the Before label explanation template, it will look for the first set of words that appear before the label in your example files.</span></span> <span data-ttu-id="cadac-302">예를 들어 첫번째 예제 파일에서 식별되는 단어는 “As of”입니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-302">In the example, the words that are identified in the first example file is "As of".</span></span>

![레이블 서식 파일 전](../media/content-understanding/before-label-explanation.png)

<span data-ttu-id="cadac-304">서식 파일에서 **추가** 를 선택하여 설명을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-304">You can select **Add** to create an explanation from the template.</span></span>  <span data-ttu-id="cadac-305">예제 파일을 더 추가하면 추가 단어가 식별되어 구 목록에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-305">As you add more example files, additional words will be identified and added to the phrase list.</span></span>

![레이블 추가](../media/content-understanding/before-label-add.png)

#### <a name="to-use-a-template-from-the-explanation-library"></a><span data-ttu-id="cadac-307">설명 라이브러리에서 서식 파일을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="cadac-307">To use a template from the explanation library</span></span>

1. <span data-ttu-id="cadac-308">모델의 **교육** 페이지의 **설명** 구역에서 **신규** 를 선택한 다음 **서식 파일 사용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-308">From the **Explanations** section of your model's **Train** page, select **New**, then select **From a template**.</span></span>

   ![레이블 전에 추가](../media/content-understanding/from-template.png)

2.  <span data-ttu-id="cadac-310">**설명 서식 파일** 페이지에서 사용하려는 설명을 선택하고 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-310">On the **Explanation templates** page, select the explanation you want to use, then select **Add**.</span></span>

    ![서식 파일 선택](../media/content-understanding/phone-template.png)

3. <span data-ttu-id="cadac-312">선택한 서식 파일에 대한 정보는 **설명 만들기** 페이지에 나와 있습니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-312">The information for the template you selected displays on the **Create an explanation** page.</span></span> <span data-ttu-id="cadac-313">필요한 경우 설명 이름을 편집하고 구 목록에서 항목을 추가 또는 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-313">If needed, edit the explanation name and add or remove items from the phrase list.</span></span>

    ![서식 파일 편집](../media/content-understanding/phone-template-live.png)

4. <span data-ttu-id="cadac-315">작업을 끝낸 후 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="cadac-315">When finished, select **Save**.</span></span>