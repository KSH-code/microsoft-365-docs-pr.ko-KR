---
title: DLP 기능이 찾는 항목
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/18/2016
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 중요 한 정보 유형은 특정 패턴을 확인 하 고 적절 한 서식을 유지 하 고 체크섬을 적용 하며 관련 키워드 또는 기타 정보를 찾는 방법으로 corroborate 합니다. 이 기능 중 일부는 내부 함수에 의해 수행됩니다. 이 항목에는 이러한 함수가 찾는 대상이 설명되어 있어 미리 정의된 중요한 정보 유형이 작동하는 방식을 이해할 수 있습니다.
ms.openlocfilehash: c192a17c488e5a7252a3599204d2bdeda4d0637c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088645"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="510df-105">DLP 기능이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="510df-105">What the DLP functions look for</span></span>

<span data-ttu-id="510df-p102">DLP(데이터 손실 방지)에는 DLP 정책에 사용할 수 있는 신용 카드 번호 및 EU 직불 카드 번호와 같은 중요한 정보 유형이 포함됩니다. 이러한 중요한 정보 유형은 특정 패턴을 찾은 후 서식이 올바른지 확인하고, 체크섬을 적용하고, 관련된 키워드 또는 기타 정보를 찾아 완전하게 확인합니다. 이 기능 중 일부는 내부 함수에 의해 수행됩니다. 예를 들어 신용 카드 번호 중요한 정보 유형은 만료일과 같은 형식의 날짜를 찾는 함수를 사용하여 숫자가 신용 카드 번호임을 입증하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="510df-p102">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="510df-110">이 항목에는 이러한 함수가 찾는 대상이 설명되어 있어 미리 정의된 중요한 정보 유형이 작동하는 방식을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-110">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="510df-111">자세한 내용은 [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md)을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="510df-111">For more information, see [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="510df-112">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="510df-112">Func_us_date</span></span>

<span data-ttu-id="510df-113">이 함수는 미국에서 일반적으로 사용 되는 형식으로 날짜를 찾습니다. 여기에는 "월/일/년", "월-일-년" 및 "월 일 년" 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="510df-113">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="510df-114">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-114">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="510df-115">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-115">Examples:</span></span>
  
- <span data-ttu-id="510df-116">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="510df-116">December 2, 2016</span></span>
    
- <span data-ttu-id="510df-117">12 월 2 일 2016</span><span class="sxs-lookup"><span data-stu-id="510df-117">Dec 2, 2016</span></span>
    
- <span data-ttu-id="510df-118">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="510df-118">dec 02 2016</span></span>
    
- <span data-ttu-id="510df-119">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="510df-119">12/2/2016</span></span>
    
- <span data-ttu-id="510df-120">12/02/16</span><span class="sxs-lookup"><span data-stu-id="510df-120">12/02/16</span></span>
    
- <span data-ttu-id="510df-121">2-2016 년 12 월</span><span class="sxs-lookup"><span data-stu-id="510df-121">Dec-2-2016</span></span>
    
- <span data-ttu-id="510df-122">12-2-16</span><span class="sxs-lookup"><span data-stu-id="510df-122">12-2-16</span></span>
    
<span data-ttu-id="510df-123">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="510df-123">Accepted month names:</span></span>
  
- <span data-ttu-id="510df-124">영어</span><span class="sxs-lookup"><span data-stu-id="510df-124">English</span></span>
    
  - <span data-ttu-id="510df-125">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="510df-125">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="510df-126">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="510df-126">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="510df-127">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="510df-127">Func_eu_date</span></span>

<span data-ttu-id="510df-p105">이 함수는 유럽 연합(및 미국 이외의 대부분의 지역)에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 여기에는 "일/월/년", "일-월-년" 및 "일 월 년" 형식이 포함됩니다. 월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-p105">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="510df-132">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-132">Examples:</span></span>
  
- <span data-ttu-id="510df-133">2 월 12 일 2016</span><span class="sxs-lookup"><span data-stu-id="510df-133">2 Dec 2016</span></span>
    
- <span data-ttu-id="510df-134">02 년 12 월 2016</span><span class="sxs-lookup"><span data-stu-id="510df-134">02 dec 2016</span></span>
    
- <span data-ttu-id="510df-135">2 월 16 일</span><span class="sxs-lookup"><span data-stu-id="510df-135">2 Dec 16</span></span>
    
- <span data-ttu-id="510df-136">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="510df-136">2/12/2016</span></span>
    
- <span data-ttu-id="510df-137">02/12/16</span><span class="sxs-lookup"><span data-stu-id="510df-137">02/12/16</span></span>
    
- <span data-ttu-id="510df-138">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="510df-138">2-Dec-2016</span></span>
    
- <span data-ttu-id="510df-139">2-12-16</span><span class="sxs-lookup"><span data-stu-id="510df-139">2-12-16</span></span>
    
<span data-ttu-id="510df-140">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="510df-140">Accepted month names:</span></span>
  
- <span data-ttu-id="510df-141">영어</span><span class="sxs-lookup"><span data-stu-id="510df-141">English</span></span>
    
  - <span data-ttu-id="510df-142">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="510df-142">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="510df-143">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="510df-143">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="510df-144">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="510df-144">Dutch</span></span>
    
  - <span data-ttu-id="510df-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="510df-145">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="510df-146">jan 1 월 maart 년 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="510df-146">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="510df-147">프랑스어</span><span class="sxs-lookup"><span data-stu-id="510df-147">French</span></span>
    
  - <span data-ttu-id="510df-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="510df-148">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="510df-149">janv.</span><span class="sxs-lookup"><span data-stu-id="510df-149">janv.</span></span> <span data-ttu-id="510df-150">févr.</span><span class="sxs-lookup"><span data-stu-id="510df-150">févr.</span></span> <span data-ttu-id="510df-151">mars avril mai juin juil</span><span class="sxs-lookup"><span data-stu-id="510df-151">mars avril mai juin juil.</span></span> <span data-ttu-id="510df-152">août 9 월</span><span class="sxs-lookup"><span data-stu-id="510df-152">août sept.</span></span> <span data-ttu-id="510df-153">일.</span><span class="sxs-lookup"><span data-stu-id="510df-153">oct.</span></span> <span data-ttu-id="510df-154">수정일.</span><span class="sxs-lookup"><span data-stu-id="510df-154">nov.</span></span> <span data-ttu-id="510df-155">déc.</span><span class="sxs-lookup"><span data-stu-id="510df-155">déc.</span></span>
    
- <span data-ttu-id="510df-156">독일어</span><span class="sxs-lookup"><span data-stu-id="510df-156">German</span></span>
    
  - <span data-ttu-id="510df-157">jänuar, februar, märz, 4 월, mai, juni juli, 8 월, 09, oktober, 11 월, dezember</span><span class="sxs-lookup"><span data-stu-id="510df-157">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="510df-158">1 월/Jän.</span><span class="sxs-lookup"><span data-stu-id="510df-158">Jan./Jän.</span></span> <span data-ttu-id="510df-159">März Apr. Mai Juni Juli 8 ~ 9. Okt</span><span class="sxs-lookup"><span data-stu-id="510df-159">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="510df-160">11 월.</span><span class="sxs-lookup"><span data-stu-id="510df-160">Nov. Dez.</span></span>
    
- <span data-ttu-id="510df-161">이탈리아어</span><span class="sxs-lookup"><span data-stu-id="510df-161">Italian</span></span>
    
  - <span data-ttu-id="510df-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, novembre</span><span class="sxs-lookup"><span data-stu-id="510df-162">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="510df-163">genn</span><span class="sxs-lookup"><span data-stu-id="510df-163">genn.</span></span> <span data-ttu-id="510df-164">febbr</span><span class="sxs-lookup"><span data-stu-id="510df-164">febbr.</span></span> <span data-ttu-id="510df-165">mar.</span><span class="sxs-lookup"><span data-stu-id="510df-165">mar.</span></span> <span data-ttu-id="510df-166">년.</span><span class="sxs-lookup"><span data-stu-id="510df-166">apr.</span></span> <span data-ttu-id="510df-167">magg.</span><span class="sxs-lookup"><span data-stu-id="510df-167">magg.</span></span> <span data-ttu-id="510df-168">giugno luglio ag</span><span class="sxs-lookup"><span data-stu-id="510df-168">giugno luglio ag.</span></span> <span data-ttu-id="510df-169">sett</span><span class="sxs-lookup"><span data-stu-id="510df-169">sett.</span></span> <span data-ttu-id="510df-170">ott.</span><span class="sxs-lookup"><span data-stu-id="510df-170">ott.</span></span> <span data-ttu-id="510df-171">수정일.</span><span class="sxs-lookup"><span data-stu-id="510df-171">nov.</span></span> <span data-ttu-id="510df-172">home.dic.</span><span class="sxs-lookup"><span data-stu-id="510df-172">dic.</span></span>
    
- <span data-ttu-id="510df-173">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="510df-173">Portuguese</span></span>
    
  - <span data-ttu-id="510df-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="510df-174">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="510df-175">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="510df-175">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="510df-176">스페인어</span><span class="sxs-lookup"><span data-stu-id="510df-176">Spanish</span></span>
    
  - <span data-ttu-id="510df-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="510df-177">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="510df-178">enero 년 2 월</span><span class="sxs-lookup"><span data-stu-id="510df-178">enero feb.</span></span> <span data-ttu-id="510df-179">marzo abr</span><span class="sxs-lookup"><span data-stu-id="510df-179">marzo abr.</span></span> <span data-ttu-id="510df-180">mayo의 6 월</span><span class="sxs-lookup"><span data-stu-id="510df-180">mayo jun.</span></span> <span data-ttu-id="510df-181">최종.</span><span class="sxs-lookup"><span data-stu-id="510df-181">jul.</span></span> <span data-ttu-id="510df-182">agosto/set.</span><span class="sxs-lookup"><span data-stu-id="510df-182">agosto sept./set.</span></span> <span data-ttu-id="510df-183">일.</span><span class="sxs-lookup"><span data-stu-id="510df-183">oct.</span></span> <span data-ttu-id="510df-184">수정일.</span><span class="sxs-lookup"><span data-stu-id="510df-184">nov.</span></span> <span data-ttu-id="510df-185">home.dic.</span><span class="sxs-lookup"><span data-stu-id="510df-185">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="510df-186">Func_eu_date1(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="510df-186">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="510df-187">이 함수는 이제 위의 `Func_eu_date` 함수에 포함 되는 포르투갈어 월 이름을 지원 하기 때문에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-187">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="510df-188">이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-188">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="510df-189">이 함수의 형식은 사용 되는 언어에만 `Func_eu_date`다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="510df-189">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="510df-190">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-190">Examples:</span></span>
  
- <span data-ttu-id="510df-191">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="510df-191">2 Dez 2016</span></span>
    
- <span data-ttu-id="510df-192">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="510df-192">02 dez 2016</span></span>
    
- <span data-ttu-id="510df-193">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="510df-193">2 Dez 16</span></span>
    
- <span data-ttu-id="510df-194">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="510df-194">2/12/2016</span></span>
    
- <span data-ttu-id="510df-195">02/12/16</span><span class="sxs-lookup"><span data-stu-id="510df-195">02/12/16</span></span>
    
- <span data-ttu-id="510df-196">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="510df-196">2-Dez-2016</span></span>
    
- <span data-ttu-id="510df-197">2-12-16</span><span class="sxs-lookup"><span data-stu-id="510df-197">2-12-16</span></span>
    
<span data-ttu-id="510df-198">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="510df-198">Accepted month names:</span></span>
  
- <span data-ttu-id="510df-199">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="510df-199">Portuguese</span></span>
    
  - <span data-ttu-id="510df-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="510df-200">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="510df-201">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="510df-201">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="510df-202">Func_eu_date2(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="510df-202">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="510df-203">이 함수는 이제 위의 `Func_eu_date` 함수에 포함 되는 네덜란드어 월 이름만 지원 하기 때문에 더 이상 사용 되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-203">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="510df-204">이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-204">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="510df-205">이 함수의 형식은 사용 되는 언어에만 `Func_eu_date`다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="510df-205">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="510df-206">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-206">Examples:</span></span>
  
- <span data-ttu-id="510df-207">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="510df-207">2 Mei 2016</span></span>
    
- <span data-ttu-id="510df-208">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="510df-208">02 mei 2016</span></span>
    
- <span data-ttu-id="510df-209">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="510df-209">2 Mei 16</span></span>
    
- <span data-ttu-id="510df-210">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="510df-210">2/12/2016</span></span>
    
- <span data-ttu-id="510df-211">02/12/16</span><span class="sxs-lookup"><span data-stu-id="510df-211">02/12/16</span></span>
    
- <span data-ttu-id="510df-212">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="510df-212">2-Mei-2016</span></span>
    
- <span data-ttu-id="510df-213">2-12-16</span><span class="sxs-lookup"><span data-stu-id="510df-213">2-12-16</span></span>
    
<span data-ttu-id="510df-214">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="510df-214">Accepted month names:</span></span>
  
- <span data-ttu-id="510df-215">네덜란드어</span><span class="sxs-lookup"><span data-stu-id="510df-215">Dutch</span></span>
    
  - <span data-ttu-id="510df-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="510df-216">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="510df-217">jan 1 월 maart 년 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="510df-217">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="510df-218">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="510df-218">Func_expiration_date</span></span>

<span data-ttu-id="510df-219">이 함수는 신용 카드 및 직불 카드에서 일반적으로 사용되는 형식의 날짜를 찾으며 월 기준의 일은 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="510df-219">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="510df-220">이 함수는 "month/year", "month-year", "[month name] year" 및 "[month 약어] year" 형식으로 날짜를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="510df-220">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="510df-221">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-221">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="510df-222">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-222">Examples:</span></span>
  
- <span data-ttu-id="510df-223">MM/YY - 예를 들어 01/11 또는 1/11</span><span class="sxs-lookup"><span data-stu-id="510df-223">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="510df-224">MM/YYYY - 예를 들어 01/2011, 1/2011 등</span><span class="sxs-lookup"><span data-stu-id="510df-224">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="510df-225">MM-YY -- 예를 들어 01-22 또는 1-11</span><span class="sxs-lookup"><span data-stu-id="510df-225">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="510df-226">MM-YYYY -- 예를 들어 01-2000 또는 1-2000</span><span class="sxs-lookup"><span data-stu-id="510df-226">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="510df-227">다음 형식은 YY 또는 YYYY를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="510df-227">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="510df-228">Month-YYYY -- 예를 들어 Jan-2010, january-2010, Jan-10 또는 january-10</span><span class="sxs-lookup"><span data-stu-id="510df-228">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="510df-229">Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="510df-229">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="510df-230">MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="510df-230">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="510df-231">Month/YYYY--예를 들어 ' 1 월/2010 ' 또는 ' Jan/2010 ' 또는 ' 1 월/10 '</span><span class="sxs-lookup"><span data-stu-id="510df-231">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="510df-232">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="510df-232">Accepted month names:</span></span>
  
- <span data-ttu-id="510df-233">영어</span><span class="sxs-lookup"><span data-stu-id="510df-233">English</span></span>
    
  - <span data-ttu-id="510df-234">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="510df-234">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="510df-235">1 월 2 월 3 월 4 일, 08 년 6 시 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="510df-235">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="510df-236">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="510df-236">Func_us_address</span></span>

<span data-ttu-id="510df-p113">이 함수는 우편 주소에 사용되는 것과 같이 미국 주 이름 또는 주 약어와 유효한 우편 번호를 찾습니다. 우편 번호는 미국 주 이름 또는 약어와 관련된 올바른 우편 번호 중 하나여야 합니다. 미국 주 이름과 우편 번호를 문장 부호나 문자로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="510df-p113">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="510df-240">예제:</span><span class="sxs-lookup"><span data-stu-id="510df-240">Examples:</span></span>
  
- <span data-ttu-id="510df-241">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="510df-241">Washington 98052</span></span>
    
- <span data-ttu-id="510df-242">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="510df-242">Washington 98052-9998</span></span>
    
- <span data-ttu-id="510df-243">WA 98052</span><span class="sxs-lookup"><span data-stu-id="510df-243">WA 98052</span></span>
    
- <span data-ttu-id="510df-244">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="510df-244">WA 98052-9998</span></span>
    

