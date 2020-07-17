---
title: DLP 기능이 찾는 항목
f1.keywords:
- NOCSH
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
ms.custom:
- seo-marvel-apr2020
description: 미리 정의 된 중요 한 정보 유형의 작동 방식을 이해 하는 데 도움이 되도록 DLP (데이터 손실 방지) 함수가 찾는 내용을 알아봅니다.
ms.openlocfilehash: 838277b2e30696cd00cfc30df49c1d5a29149d92
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819278"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="e2dfc-103">DLP 기능이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="e2dfc-103">What the DLP functions look for</span></span>

<span data-ttu-id="e2dfc-p101">DLP(데이터 손실 방지)에는 DLP 정책에 사용할 수 있는 신용 카드 번호 및 EU 직불 카드 번호와 같은 중요한 정보 유형이 포함됩니다. 이러한 중요한 정보 유형은 특정 패턴을 찾은 후 서식이 올바른지 확인하고, 체크섬을 적용하고, 관련된 키워드 또는 기타 정보를 찾아 완전하게 확인합니다. 이 기능 중 일부는 내부 함수에 의해 수행됩니다. 예를 들어 신용 카드 번호 중요한 정보 유형은 만료일과 같은 형식의 날짜를 찾는 함수를 사용하여 숫자가 신용 카드 번호임을 입증하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-p101">Data loss prevention (DLP) includes sensitive information types, such as Credit Card Number and EU Debit Card Number, which are ready for you to use in your DLP policies. These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information. Some of this functionality is performed by internal functions. For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="e2dfc-108">이 항목에는 이러한 함수가 찾는 대상이 설명되어 있어 미리 정의된 중요한 정보 유형이 작동하는 방식을 이해할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-108">This topic explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="e2dfc-109">자세한 내용은 [중요 한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="e2dfc-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="e2dfc-110">Func_us_date</span></span>

<span data-ttu-id="e2dfc-111">이 함수는 미국에서 일반적으로 사용 되는 형식으로 날짜를 찾습니다. 여기에는 "월/일/년", "월-일-년" 및 "월 일 년" 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="e2dfc-112">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="e2dfc-113">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-113">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-114">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-114">December 2, 2016</span></span>
    
- <span data-ttu-id="e2dfc-115">12 월 2 일 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="e2dfc-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-116">dec 02 2016</span></span>
    
- <span data-ttu-id="e2dfc-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-117">12/2/2016</span></span>
    
- <span data-ttu-id="e2dfc-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-118">12/02/16</span></span>
    
- <span data-ttu-id="e2dfc-119">2-2016 년 12 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="e2dfc-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-120">12-2-16</span></span>
    
<span data-ttu-id="e2dfc-121">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-121">Accepted month names:</span></span>
  
- <span data-ttu-id="e2dfc-122">English</span><span class="sxs-lookup"><span data-stu-id="e2dfc-122">English</span></span>
    
  - <span data-ttu-id="e2dfc-123">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e2dfc-124">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="e2dfc-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="e2dfc-125">Func_eu_date</span></span>

<span data-ttu-id="e2dfc-p104">이 함수는 유럽 연합(및 미국 이외의 대부분의 지역)에서 일반적으로 사용되는 형식의 날짜를 찾습니다. 여기에는 "일/월/년", "일-월-년" 및 "일 월 년" 형식이 포함됩니다. 월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-p104">This function looks for a date in the format commonly used in the E.U. (and most places outside the U.S.). This includes the formats "day/month/year", "day-month-year", and "day month year". The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e2dfc-130">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-130">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-131">2 월 12 일 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-131">2 Dec 2016</span></span>
    
- <span data-ttu-id="e2dfc-132">02 년 12 월 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-132">02 dec 2016</span></span>
    
- <span data-ttu-id="e2dfc-133">2 월 16 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-133">2 Dec 16</span></span>
    
- <span data-ttu-id="e2dfc-134">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-134">2/12/2016</span></span>
    
- <span data-ttu-id="e2dfc-135">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-135">02/12/16</span></span>
    
- <span data-ttu-id="e2dfc-136">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-136">2-Dec-2016</span></span>
    
- <span data-ttu-id="e2dfc-137">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-137">2-12-16</span></span>
    
<span data-ttu-id="e2dfc-138">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-138">Accepted month names:</span></span>
  
- <span data-ttu-id="e2dfc-139">English</span><span class="sxs-lookup"><span data-stu-id="e2dfc-139">English</span></span>
    
  - <span data-ttu-id="e2dfc-140">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-140">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e2dfc-141">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-141">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="e2dfc-142">Dutch</span><span class="sxs-lookup"><span data-stu-id="e2dfc-142">Dutch</span></span>
    
  - <span data-ttu-id="e2dfc-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e2dfc-143">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e2dfc-144">jan 1 월 maart 년 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-144">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="e2dfc-145">French</span><span class="sxs-lookup"><span data-stu-id="e2dfc-145">French</span></span>
    
  - <span data-ttu-id="e2dfc-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="e2dfc-146">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="e2dfc-147">janv.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-147">janv.</span></span> <span data-ttu-id="e2dfc-148">févr.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-148">févr.</span></span> <span data-ttu-id="e2dfc-149">mars avril mai juin juil</span><span class="sxs-lookup"><span data-stu-id="e2dfc-149">mars avril mai juin juil.</span></span> <span data-ttu-id="e2dfc-150">août 9 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-150">août sept.</span></span> <span data-ttu-id="e2dfc-151">일.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-151">oct.</span></span> <span data-ttu-id="e2dfc-152">수정일.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-152">nov.</span></span> <span data-ttu-id="e2dfc-153">déc.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-153">déc.</span></span>
    
- <span data-ttu-id="e2dfc-154">German</span><span class="sxs-lookup"><span data-stu-id="e2dfc-154">German</span></span>
    
  - <span data-ttu-id="e2dfc-155">jänuar, februar, märz, 4 월, mai, juni juli, 8 월, 09, oktober, 11 월, dezember</span><span class="sxs-lookup"><span data-stu-id="e2dfc-155">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="e2dfc-156">1 월/Jän.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-156">Jan./Jän.</span></span> <span data-ttu-id="e2dfc-157">März Apr. Mai Juni Juli 8 ~ 9. Okt</span><span class="sxs-lookup"><span data-stu-id="e2dfc-157">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="e2dfc-158">11 월.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-158">Nov. Dez.</span></span>
    
- <span data-ttu-id="e2dfc-159">Italian</span><span class="sxs-lookup"><span data-stu-id="e2dfc-159">Italian</span></span>
    
  - <span data-ttu-id="e2dfc-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, novembre</span><span class="sxs-lookup"><span data-stu-id="e2dfc-160">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="e2dfc-161">genn</span><span class="sxs-lookup"><span data-stu-id="e2dfc-161">genn.</span></span> <span data-ttu-id="e2dfc-162">febbr</span><span class="sxs-lookup"><span data-stu-id="e2dfc-162">febbr.</span></span> <span data-ttu-id="e2dfc-163">mar.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-163">mar.</span></span> <span data-ttu-id="e2dfc-164">년.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-164">apr.</span></span> <span data-ttu-id="e2dfc-165">magg.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-165">magg.</span></span> <span data-ttu-id="e2dfc-166">giugno luglio ag</span><span class="sxs-lookup"><span data-stu-id="e2dfc-166">giugno luglio ag.</span></span> <span data-ttu-id="e2dfc-167">sett</span><span class="sxs-lookup"><span data-stu-id="e2dfc-167">sett.</span></span> <span data-ttu-id="e2dfc-168">ott.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-168">ott.</span></span> <span data-ttu-id="e2dfc-169">수정일.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-169">nov.</span></span> <span data-ttu-id="e2dfc-170">home.dic.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-170">dic.</span></span>
    
- <span data-ttu-id="e2dfc-171">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="e2dfc-171">Portuguese</span></span>
    
  - <span data-ttu-id="e2dfc-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e2dfc-172">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e2dfc-173">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="e2dfc-173">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="e2dfc-174">Spanish</span><span class="sxs-lookup"><span data-stu-id="e2dfc-174">Spanish</span></span>
    
  - <span data-ttu-id="e2dfc-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="e2dfc-175">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="e2dfc-176">enero 년 2 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-176">enero feb.</span></span> <span data-ttu-id="e2dfc-177">marzo abr</span><span class="sxs-lookup"><span data-stu-id="e2dfc-177">marzo abr.</span></span> <span data-ttu-id="e2dfc-178">mayo의 6 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-178">mayo jun.</span></span> <span data-ttu-id="e2dfc-179">최종.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-179">jul.</span></span> <span data-ttu-id="e2dfc-180">agosto/set.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-180">agosto sept./set.</span></span> <span data-ttu-id="e2dfc-181">일.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-181">oct.</span></span> <span data-ttu-id="e2dfc-182">수정일.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-182">nov.</span></span> <span data-ttu-id="e2dfc-183">home.dic.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-183">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="e2dfc-184">Func_eu_date1(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="e2dfc-184">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e2dfc-185">이 함수는 이제 위의 함수에 포함 되는 포르투갈어 월 이름을 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` .</span><span class="sxs-lookup"><span data-stu-id="e2dfc-185">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e2dfc-186">이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-186">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="e2dfc-187">이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-187">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e2dfc-188">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-188">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-189">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-189">2 Dez 2016</span></span>
    
- <span data-ttu-id="e2dfc-190">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-190">02 dez 2016</span></span>
    
- <span data-ttu-id="e2dfc-191">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-191">2 Dez 16</span></span>
    
- <span data-ttu-id="e2dfc-192">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-192">2/12/2016</span></span>
    
- <span data-ttu-id="e2dfc-193">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-193">02/12/16</span></span>
    
- <span data-ttu-id="e2dfc-194">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-194">2-Dez-2016</span></span>
    
- <span data-ttu-id="e2dfc-195">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-195">2-12-16</span></span>
    
<span data-ttu-id="e2dfc-196">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-196">Accepted month names:</span></span>
  
- <span data-ttu-id="e2dfc-197">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="e2dfc-197">Portuguese</span></span>
    
  - <span data-ttu-id="e2dfc-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="e2dfc-198">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="e2dfc-199">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="e2dfc-199">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="e2dfc-200">Func_eu_date2(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="e2dfc-200">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="e2dfc-201">이 함수는 이제 위의 함수에 포함 되는 네덜란드어 월 이름만 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` .</span><span class="sxs-lookup"><span data-stu-id="e2dfc-201">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="e2dfc-202">이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-202">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="e2dfc-203">이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-203">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="e2dfc-204">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-204">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-205">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-205">2 Mei 2016</span></span>
    
- <span data-ttu-id="e2dfc-206">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-206">02 mei 2016</span></span>
    
- <span data-ttu-id="e2dfc-207">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-207">2 Mei 16</span></span>
    
- <span data-ttu-id="e2dfc-208">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-208">2/12/2016</span></span>
    
- <span data-ttu-id="e2dfc-209">02/12/16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-209">02/12/16</span></span>
    
- <span data-ttu-id="e2dfc-210">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="e2dfc-210">2-Mei-2016</span></span>
    
- <span data-ttu-id="e2dfc-211">2-12-16</span><span class="sxs-lookup"><span data-stu-id="e2dfc-211">2-12-16</span></span>
    
<span data-ttu-id="e2dfc-212">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-212">Accepted month names:</span></span>
  
- <span data-ttu-id="e2dfc-213">Dutch</span><span class="sxs-lookup"><span data-stu-id="e2dfc-213">Dutch</span></span>
    
  - <span data-ttu-id="e2dfc-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="e2dfc-214">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="e2dfc-215">jan 1 월 maart 년 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-215">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="e2dfc-216">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="e2dfc-216">Func_expiration_date</span></span>

<span data-ttu-id="e2dfc-217">이 함수는 신용 카드 및 직불 카드에서 일반적으로 사용되는 형식의 날짜를 찾으며 월 기준의 일은 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-217">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="e2dfc-218">이 함수는 "month/year", "month-year", "[month name] year" 및 "[month 약어] year" 형식으로 날짜를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-218">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="e2dfc-219">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-219">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="e2dfc-220">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-220">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-221">MM/YY - 예를 들어 01/11 또는 1/11</span><span class="sxs-lookup"><span data-stu-id="e2dfc-221">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="e2dfc-222">MM/YYYY - 예를 들어 01/2011, 1/2011 등</span><span class="sxs-lookup"><span data-stu-id="e2dfc-222">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="e2dfc-223">MM-YY -- 예를 들어 01-22 또는 1-11</span><span class="sxs-lookup"><span data-stu-id="e2dfc-223">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="e2dfc-224">MM-YYYY -- 예를 들어 01-2000 또는 1-2000</span><span class="sxs-lookup"><span data-stu-id="e2dfc-224">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="e2dfc-225">다음 형식은 YY 또는 YYYY를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-225">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="e2dfc-226">Month-YYYY -- 예를 들어 Jan-2010, january-2010, Jan-10 또는 january-10</span><span class="sxs-lookup"><span data-stu-id="e2dfc-226">Month-YYYY -- for example, .Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="e2dfc-227">Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="e2dfc-227">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="e2dfc-228">MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="e2dfc-228">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="e2dfc-229">Month/YYYY--예를 들어 ' 1 월/2010 ' 또는 ' Jan/2010 ' 또는 ' 1 월/10 '</span><span class="sxs-lookup"><span data-stu-id="e2dfc-229">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="e2dfc-230">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-230">Accepted month names:</span></span>
  
- <span data-ttu-id="e2dfc-231">English</span><span class="sxs-lookup"><span data-stu-id="e2dfc-231">English</span></span>
    
  - <span data-ttu-id="e2dfc-232">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="e2dfc-232">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="e2dfc-233">1 월 2 월 3 월 4 일, 08 년 6 시 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="e2dfc-233">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="e2dfc-234">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="e2dfc-234">Func_us_address</span></span>

<span data-ttu-id="e2dfc-p112">이 함수는 우편 주소에 사용되는 것과 같이 미국 주 이름 또는 주 약어와 유효한 우편 번호를 찾습니다. 우편 번호는 미국 주 이름 또는 약어와 관련된 올바른 우편 번호 중 하나여야 합니다. 미국 주 이름과 우편 번호를 문장 부호나 문자로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="e2dfc-p112">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they are used in postal addresses. The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation. The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="e2dfc-238">예제:</span><span class="sxs-lookup"><span data-stu-id="e2dfc-238">Examples:</span></span>
  
- <span data-ttu-id="e2dfc-239">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="e2dfc-239">Washington 98052</span></span>
    
- <span data-ttu-id="e2dfc-240">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e2dfc-240">Washington 98052-9998</span></span>
    
- <span data-ttu-id="e2dfc-241">WA 98052</span><span class="sxs-lookup"><span data-stu-id="e2dfc-241">WA 98052</span></span>
    
- <span data-ttu-id="e2dfc-242">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="e2dfc-242">WA 98052-9998</span></span>
    

