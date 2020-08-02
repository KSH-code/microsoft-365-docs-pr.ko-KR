---
title: DLP (데이터 손실 방지) 함수에서 찾을 대상
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
description: DLP (데이터 손실 방지) 함수에서 찾는 사항에 대해 알아봅니다.
ms.openlocfilehash: ef87be7dde83b1e5ba12456e7801e0554bceb6ea
ms.sourcegitcommit: cfb0c50f1366736cdf031a75f0608246b5640d93
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/31/2020
ms.locfileid: "46536313"
---
# <a name="what-the-dlp-functions-look-for"></a><span data-ttu-id="427e6-103">DLP 기능이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="427e6-103">What the DLP functions look for</span></span>

<span data-ttu-id="427e6-104">DLP (데이터 손실 방지)에는 DLP 정책에서 사용할 준비가 된 신용 카드 번호 및 EU 직불 카드 번호와 같은 중요 한 정보 유형이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-104">Data loss prevention (DLP) includes sensitive information types, such as credit card Number and EU Debit card number, which are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="427e6-105">이러한 중요한 정보 유형은 특정 패턴을 찾은 후 서식이 올바른지 확인하고, 체크섬을 적용하고, 관련된 키워드 또는 기타 정보를 찾아 완전하게 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-105">These sensitive information types look for a specific pattern and corroborate it by ensuring proper formatting, enforcing checksums, and looking for relevant keywords or other information.</span></span> <span data-ttu-id="427e6-106">이 기능 중 일부는 내부 함수에 의해 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-106">Some of this functionality is performed by internal functions.</span></span> <span data-ttu-id="427e6-107">예를 들어 신용 카드 번호 중요한 정보 유형은 만료일과 같은 형식의 날짜를 찾는 함수를 사용하여 숫자가 신용 카드 번호임을 입증하는 데 도움을 줍니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-107">For example, the Credit Card Number sensitive information type uses a function to look for dates formatted like an expiration date, to help corroborate that a number is a credit card number.</span></span>
  
<span data-ttu-id="427e6-108">이 문서에서는 미리 정의 된 중요 한 정보 유형의 작동 방식을 이해 하는 데 도움이 되도록 이러한 함수가 찾는 항목에 대해 설명 합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-108">This article explains what these functions look for, to help you understand how the predefined sensitive information types work.</span></span> <span data-ttu-id="427e6-109">자세한 내용은 [중요 한 정보 유형 엔터티 정의](sensitive-information-type-entity-definitions.md) 를 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="427e6-109">For more information, see [Sensitive information type entity definitions](sensitive-information-type-entity-definitions.md)</span></span>
  
## <a name="func_us_date"></a><span data-ttu-id="427e6-110">Func_us_date</span><span class="sxs-lookup"><span data-stu-id="427e6-110">Func_us_date</span></span>

<span data-ttu-id="427e6-111">이 함수는 미국에서 일반적으로 사용 되는 형식으로 날짜를 찾습니다. 여기에는 "월/일/년", "월-일-년" 및 "월 일 년" 형식이 포함 됩니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-111">This function looks for a date in the format commonly used in the U.S. This includes the formats "month/day/year", "month-day-year", and "month day year ".</span></span> <span data-ttu-id="427e6-112">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-112">The names or abbreviations of months are not case sensitive.</span></span> 
  
<span data-ttu-id="427e6-113">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-113">Examples:</span></span>
  
- <span data-ttu-id="427e6-114">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="427e6-114">December 2, 2016</span></span>
    
- <span data-ttu-id="427e6-115">12 월 2 일 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-115">Dec 2, 2016</span></span>
    
- <span data-ttu-id="427e6-116">dec 02 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-116">dec 02 2016</span></span>
    
- <span data-ttu-id="427e6-117">12/2/2016</span><span class="sxs-lookup"><span data-stu-id="427e6-117">12/2/2016</span></span>
    
- <span data-ttu-id="427e6-118">12/02/16</span><span class="sxs-lookup"><span data-stu-id="427e6-118">12/02/16</span></span>
    
- <span data-ttu-id="427e6-119">2-2016 년 12 월</span><span class="sxs-lookup"><span data-stu-id="427e6-119">Dec-2-2016</span></span>
    
- <span data-ttu-id="427e6-120">12-2-16</span><span class="sxs-lookup"><span data-stu-id="427e6-120">12-2-16</span></span>
    
<span data-ttu-id="427e6-121">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="427e6-121">Accepted month names:</span></span>
  
- <span data-ttu-id="427e6-122">English</span><span class="sxs-lookup"><span data-stu-id="427e6-122">English</span></span>
    
  - <span data-ttu-id="427e6-123">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="427e6-123">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="427e6-124">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="427e6-124">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
## <a name="func_eu_date"></a><span data-ttu-id="427e6-125">Func_eu_date</span><span class="sxs-lookup"><span data-stu-id="427e6-125">Func_eu_date</span></span>

<span data-ttu-id="427e6-126">이 함수는 E.U.에서 일반적으로 사용 되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-126">This function looks for a date in the format commonly used in the E.U.</span></span> <span data-ttu-id="427e6-127">"일/월/년", "일/월/년" 및 "일 년"과 같이 미국 이외의 위치에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-127">(and most places outside the U.S.), such as "day/month/year", "day-month-year", and "day month year".</span></span> <span data-ttu-id="427e6-128">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-128">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="427e6-129">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-129">Examples:</span></span>
  
- <span data-ttu-id="427e6-130">2 월 12 일 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-130">2 Dec 2016</span></span>
    
- <span data-ttu-id="427e6-131">02 년 12 월 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-131">02 dec 2016</span></span>
    
- <span data-ttu-id="427e6-132">2 월 16 일</span><span class="sxs-lookup"><span data-stu-id="427e6-132">2 Dec 16</span></span>
    
- <span data-ttu-id="427e6-133">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="427e6-133">2/12/2016</span></span>
    
- <span data-ttu-id="427e6-134">02/12/16</span><span class="sxs-lookup"><span data-stu-id="427e6-134">02/12/16</span></span>
    
- <span data-ttu-id="427e6-135">2016 년 12 월 2 일</span><span class="sxs-lookup"><span data-stu-id="427e6-135">2-Dec-2016</span></span>
    
- <span data-ttu-id="427e6-136">2-12-16</span><span class="sxs-lookup"><span data-stu-id="427e6-136">2-12-16</span></span>
    
<span data-ttu-id="427e6-137">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="427e6-137">Accepted month names:</span></span>
  
- <span data-ttu-id="427e6-138">English</span><span class="sxs-lookup"><span data-stu-id="427e6-138">English</span></span>
    
  - <span data-ttu-id="427e6-139">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="427e6-139">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="427e6-140">1 월 2 월 3 월 4 일. c a 11 월호-2005 년 12 월.</span><span class="sxs-lookup"><span data-stu-id="427e6-140">Jan. Feb. Mar. Apr. May June July Aug. Sept. Oct. Nov. Dec.</span></span>
    
- <span data-ttu-id="427e6-141">Dutch</span><span class="sxs-lookup"><span data-stu-id="427e6-141">Dutch</span></span>
    
  - <span data-ttu-id="427e6-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="427e6-142">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="427e6-143">jan 1 월 maart 년 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="427e6-143">jan feb maart apr mei jun jul aug sep sept oct okt nov dec</span></span>
    
- <span data-ttu-id="427e6-144">French</span><span class="sxs-lookup"><span data-stu-id="427e6-144">French</span></span>
    
  - <span data-ttu-id="427e6-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span><span class="sxs-lookup"><span data-stu-id="427e6-145">janvier, février, mars, avril, mai, juin juillet, août, septembre, octobre, novembre, décembre</span></span>
    
  - <span data-ttu-id="427e6-146">janv.</span><span class="sxs-lookup"><span data-stu-id="427e6-146">janv.</span></span> <span data-ttu-id="427e6-147">févr.</span><span class="sxs-lookup"><span data-stu-id="427e6-147">févr.</span></span> <span data-ttu-id="427e6-148">mars avril mai juin juil</span><span class="sxs-lookup"><span data-stu-id="427e6-148">mars avril mai juin juil.</span></span> <span data-ttu-id="427e6-149">août 9 월</span><span class="sxs-lookup"><span data-stu-id="427e6-149">août sept.</span></span> <span data-ttu-id="427e6-150">일.</span><span class="sxs-lookup"><span data-stu-id="427e6-150">oct.</span></span> <span data-ttu-id="427e6-151">수정일.</span><span class="sxs-lookup"><span data-stu-id="427e6-151">nov.</span></span> <span data-ttu-id="427e6-152">déc.</span><span class="sxs-lookup"><span data-stu-id="427e6-152">déc.</span></span>
    
- <span data-ttu-id="427e6-153">German</span><span class="sxs-lookup"><span data-stu-id="427e6-153">German</span></span>
    
  - <span data-ttu-id="427e6-154">jänuar, februar, märz, 4 월, mai, juni juli, 8 월, 09, oktober, 11 월, dezember</span><span class="sxs-lookup"><span data-stu-id="427e6-154">jänuar, februar, märz, April, mai, juni juli, August, September, oktober, November, dezember</span></span>
    
  - <span data-ttu-id="427e6-155">1 월/Jän.</span><span class="sxs-lookup"><span data-stu-id="427e6-155">Jan./Jän.</span></span> <span data-ttu-id="427e6-156">März Apr. Mai Juni Juli 8 ~ 9. Okt</span><span class="sxs-lookup"><span data-stu-id="427e6-156">Feb. März Apr. Mai Juni Juli Aug. Sept. Okt.</span></span> <span data-ttu-id="427e6-157">11 월.</span><span class="sxs-lookup"><span data-stu-id="427e6-157">Nov. Dez.</span></span>
    
- <span data-ttu-id="427e6-158">Italian</span><span class="sxs-lookup"><span data-stu-id="427e6-158">Italian</span></span>
    
  - <span data-ttu-id="427e6-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, novembre</span><span class="sxs-lookup"><span data-stu-id="427e6-159">gennaio, febbraio, marzo, aprile, maggio, giugno, luglio, agosto, settembre, ottobre, novembre, dicembre</span></span>
    
  - <span data-ttu-id="427e6-160">genn</span><span class="sxs-lookup"><span data-stu-id="427e6-160">genn.</span></span> <span data-ttu-id="427e6-161">febbr</span><span class="sxs-lookup"><span data-stu-id="427e6-161">febbr.</span></span> <span data-ttu-id="427e6-162">mar.</span><span class="sxs-lookup"><span data-stu-id="427e6-162">mar.</span></span> <span data-ttu-id="427e6-163">년.</span><span class="sxs-lookup"><span data-stu-id="427e6-163">apr.</span></span> <span data-ttu-id="427e6-164">magg.</span><span class="sxs-lookup"><span data-stu-id="427e6-164">magg.</span></span> <span data-ttu-id="427e6-165">giugno luglio ag</span><span class="sxs-lookup"><span data-stu-id="427e6-165">giugno luglio ag.</span></span> <span data-ttu-id="427e6-166">sett</span><span class="sxs-lookup"><span data-stu-id="427e6-166">sett.</span></span> <span data-ttu-id="427e6-167">ott.</span><span class="sxs-lookup"><span data-stu-id="427e6-167">ott.</span></span> <span data-ttu-id="427e6-168">수정일.</span><span class="sxs-lookup"><span data-stu-id="427e6-168">nov.</span></span> <span data-ttu-id="427e6-169">home.dic.</span><span class="sxs-lookup"><span data-stu-id="427e6-169">dic.</span></span>
    
- <span data-ttu-id="427e6-170">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="427e6-170">Portuguese</span></span>
    
  - <span data-ttu-id="427e6-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="427e6-171">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="427e6-172">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="427e6-172">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
- <span data-ttu-id="427e6-173">Spanish</span><span class="sxs-lookup"><span data-stu-id="427e6-173">Spanish</span></span>
    
  - <span data-ttu-id="427e6-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span><span class="sxs-lookup"><span data-stu-id="427e6-174">enero, febrero, marzo, abril, mayo, junio, julio, agosto, septiembre, octubre, noviembre, diciembre</span></span>
    
  - <span data-ttu-id="427e6-175">enero 년 2 월</span><span class="sxs-lookup"><span data-stu-id="427e6-175">enero feb.</span></span> <span data-ttu-id="427e6-176">marzo abr</span><span class="sxs-lookup"><span data-stu-id="427e6-176">marzo abr.</span></span> <span data-ttu-id="427e6-177">mayo의 6 월</span><span class="sxs-lookup"><span data-stu-id="427e6-177">mayo jun.</span></span> <span data-ttu-id="427e6-178">최종.</span><span class="sxs-lookup"><span data-stu-id="427e6-178">jul.</span></span> <span data-ttu-id="427e6-179">agosto/set.</span><span class="sxs-lookup"><span data-stu-id="427e6-179">agosto sept./set.</span></span> <span data-ttu-id="427e6-180">일.</span><span class="sxs-lookup"><span data-stu-id="427e6-180">oct.</span></span> <span data-ttu-id="427e6-181">수정일.</span><span class="sxs-lookup"><span data-stu-id="427e6-181">nov.</span></span> <span data-ttu-id="427e6-182">home.dic.</span><span class="sxs-lookup"><span data-stu-id="427e6-182">dic.</span></span>
    
## <a name="func_eu_date1-deprecated"></a><span data-ttu-id="427e6-183">Func_eu_date1(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="427e6-183">Func_eu_date1 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="427e6-184">이 함수는 이제 위의 함수에 포함 되는 포르투갈어 월 이름을 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` .</span><span class="sxs-lookup"><span data-stu-id="427e6-184">This function is deprecated because it supports only Portuguese month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="427e6-185">이 함수는 포르투갈어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-185">This function looks for a date in the format commonly used in Portuguese.</span></span> <span data-ttu-id="427e6-186">이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-186">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="427e6-187">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-187">Examples:</span></span>
  
- <span data-ttu-id="427e6-188">2 dez 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-188">2 Dez 2016</span></span>
    
- <span data-ttu-id="427e6-189">02 dez 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-189">02 dez 2016</span></span>
    
- <span data-ttu-id="427e6-190">2 dez 16</span><span class="sxs-lookup"><span data-stu-id="427e6-190">2 Dez 16</span></span>
    
- <span data-ttu-id="427e6-191">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="427e6-191">2/12/2016</span></span>
    
- <span data-ttu-id="427e6-192">02/12/16</span><span class="sxs-lookup"><span data-stu-id="427e6-192">02/12/16</span></span>
    
- <span data-ttu-id="427e6-193">2-dez-2016</span><span class="sxs-lookup"><span data-stu-id="427e6-193">2-Dez-2016</span></span>
    
- <span data-ttu-id="427e6-194">2-12-16</span><span class="sxs-lookup"><span data-stu-id="427e6-194">2-12-16</span></span>
    
<span data-ttu-id="427e6-195">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="427e6-195">Accepted month names:</span></span>
  
- <span data-ttu-id="427e6-196">포르투갈어</span><span class="sxs-lookup"><span data-stu-id="427e6-196">Portuguese</span></span>
    
  - <span data-ttu-id="427e6-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span><span class="sxs-lookup"><span data-stu-id="427e6-197">janeiro, fevereiro, março, marco, abril, maio, junho, julho, agosto, setembro, outubro, novembro, dezembro</span></span>
    
  - <span data-ttu-id="427e6-198">1 월의 fev mar abr mai 6 월 30 일 전인 11 월 이전 설정</span><span class="sxs-lookup"><span data-stu-id="427e6-198">jan fev mar abr mai jun jul ago set out nov dez</span></span>
    
## <a name="func_eu_date2-deprecated"></a><span data-ttu-id="427e6-199">Func_eu_date2(더 이상 사용되지 않음)</span><span class="sxs-lookup"><span data-stu-id="427e6-199">Func_eu_date2 (deprecated)</span></span>

> [!NOTE]
> <span data-ttu-id="427e6-200">이 함수는 이제 위의 함수에 포함 되는 네덜란드어 월 이름만 지원 하기 때문에 더 이상 사용 되지 않습니다 `Func_eu_date` .</span><span class="sxs-lookup"><span data-stu-id="427e6-200">This function is deprecated because it supports only Dutch month names, which are now included in the  `Func_eu_date` function above.</span></span> 
  
<span data-ttu-id="427e6-201">이 함수는 네덜란드어에서 일반적으로 사용되는 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-201">This function looks for a date in the format commonly used in Dutch.</span></span> <span data-ttu-id="427e6-202">이 함수의 형식은 `Func_eu_date` 사용 되는 언어에만 다른 것과 동일 합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-202">The format for this function is the same as  `Func_eu_date`, differing only in the language used.</span></span>
  
<span data-ttu-id="427e6-203">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-203">Examples:</span></span>
  
- <span data-ttu-id="427e6-204">2 mei 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-204">2 Mei 2016</span></span>
    
- <span data-ttu-id="427e6-205">02 mei 2016</span><span class="sxs-lookup"><span data-stu-id="427e6-205">02 mei 2016</span></span>
    
- <span data-ttu-id="427e6-206">2 mei 16</span><span class="sxs-lookup"><span data-stu-id="427e6-206">2 Mei 16</span></span>
    
- <span data-ttu-id="427e6-207">2/12/2016</span><span class="sxs-lookup"><span data-stu-id="427e6-207">2/12/2016</span></span>
    
- <span data-ttu-id="427e6-208">02/12/16</span><span class="sxs-lookup"><span data-stu-id="427e6-208">02/12/16</span></span>
    
- <span data-ttu-id="427e6-209">2-mei-2016</span><span class="sxs-lookup"><span data-stu-id="427e6-209">2-Mei-2016</span></span>
    
- <span data-ttu-id="427e6-210">2-12-16</span><span class="sxs-lookup"><span data-stu-id="427e6-210">2-12-16</span></span>
    
<span data-ttu-id="427e6-211">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="427e6-211">Accepted month names:</span></span>
  
- <span data-ttu-id="427e6-212">Dutch</span><span class="sxs-lookup"><span data-stu-id="427e6-212">Dutch</span></span>
    
  - <span data-ttu-id="427e6-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span><span class="sxs-lookup"><span data-stu-id="427e6-213">januari, februari, maart, April, mei, juni, juli, augustus, September, ocktober, October, November, December</span></span>
    
  - <span data-ttu-id="427e6-214">1 월 2 일 maart 2007 년 9 월 8 월 9 시, 08 년 11 월</span><span class="sxs-lookup"><span data-stu-id="427e6-214">jan feb maart apr mei jun jul aug sep sept out okt nov dec</span></span>
    
## <a name="func_expiration_date"></a><span data-ttu-id="427e6-215">Func_expiration_date</span><span class="sxs-lookup"><span data-stu-id="427e6-215">Func_expiration_date</span></span>

<span data-ttu-id="427e6-216">이 함수는 신용 카드 및 직불 카드에서 일반적으로 사용되는 형식의 날짜를 찾으며 월 기준의 일은 제외합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-216">This function looks for a date in the formats commonly used by credit and debit cards, which exclude days in favor of months.</span></span> <span data-ttu-id="427e6-217">이 함수는 "month/year", "month-year", "[month name] year" 및 "[month 약어] year" 형식으로 날짜를 일치 시킵니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-217">This function will match dates in format of "month/year", "month-year", "[month name] year", and "[month abbreviation] year".</span></span> <span data-ttu-id="427e6-218">월 이름 또는 약어는 대/소문자를 구분하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-218">The names or abbreviations of months are not case sensitive.</span></span>
  
<span data-ttu-id="427e6-219">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-219">Examples:</span></span>
  
- <span data-ttu-id="427e6-220">MM/YY - 예를 들어 01/11 또는 1/11</span><span class="sxs-lookup"><span data-stu-id="427e6-220">MM/YY -- for example, 01/11 or 1/11</span></span>
    
- <span data-ttu-id="427e6-221">MM/YYYY - 예를 들어 01/2011, 1/2011 등</span><span class="sxs-lookup"><span data-stu-id="427e6-221">MM/YYYY -- for example, 01/2011 or 1/2011</span></span>
    
- <span data-ttu-id="427e6-222">MM-YY -- 예를 들어 01-22 또는 1-11</span><span class="sxs-lookup"><span data-stu-id="427e6-222">MM-YY -- for example, 01-22 or 1-11</span></span>
    
- <span data-ttu-id="427e6-223">MM-YYYY -- 예를 들어 01-2000 또는 1-2000</span><span class="sxs-lookup"><span data-stu-id="427e6-223">MM-YYYY -- for example, 01-2000 or 1-2000</span></span>
    
<span data-ttu-id="427e6-224">다음 형식은 YY 또는 YYYY를 지원합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-224">The following formats support YY or YYYY:</span></span>
  
- <span data-ttu-id="427e6-225">Month--1 월-2010 또는 1 월-2010 또는 Jan-10 년 1 월-일 예</span><span class="sxs-lookup"><span data-stu-id="427e6-225">Month-YYYY -- for example Jan-2010 or january-2010 or Jan-10 or january-10</span></span>
    
- <span data-ttu-id="427e6-226">Month YYYY -- 예를 들어 'january 2010', 'Jan 2010', 'january 10' 또는 'Jan 10'</span><span class="sxs-lookup"><span data-stu-id="427e6-226">Month YYYY -- for example, 'january 2010' or 'Jan 2010' or 'january 10' or 'Jan 10'</span></span>
    
- <span data-ttu-id="427e6-227">MonthYYYY -- 예를 들어 'january2010', 'Jan2010', 'january10' 또는 'Jan10'</span><span class="sxs-lookup"><span data-stu-id="427e6-227">MonthYYYY -- for example, 'january2010' or 'Jan2010' or 'january10' or 'Jan10'</span></span>
    
- <span data-ttu-id="427e6-228">Month/YYYY--예를 들어 ' 1 월/2010 ' 또는 ' Jan/2010 ' 또는 ' 1 월/10 '</span><span class="sxs-lookup"><span data-stu-id="427e6-228">Month/YYYY -- for example, 'january/2010' or 'Jan/2010' or 'january/10' or 'Jan/10'</span></span>
    
<span data-ttu-id="427e6-229">허용되는 월 이름:</span><span class="sxs-lookup"><span data-stu-id="427e6-229">Accepted month names:</span></span>
  
- <span data-ttu-id="427e6-230">English</span><span class="sxs-lookup"><span data-stu-id="427e6-230">English</span></span>
    
  - <span data-ttu-id="427e6-231">1 월, 2 월, 3 월, 4 월, 5 월, 01 년 6 월, 년 9 월, 10 월, 년 11 월, 12 월</span><span class="sxs-lookup"><span data-stu-id="427e6-231">January, February, march, April, may, June, July, August, September, October, November, December</span></span>
    
  - <span data-ttu-id="427e6-232">1 월 2 월 3 월 4 일, 08 년 6 시 9 월 8 일</span><span class="sxs-lookup"><span data-stu-id="427e6-232">Jan Feb Mar Apr May June July Aug Sept Oct Nov Dec</span></span>
    
## <a name="func_us_address"></a><span data-ttu-id="427e6-233">Func_us_address</span><span class="sxs-lookup"><span data-stu-id="427e6-233">Func_us_address</span></span>

<span data-ttu-id="427e6-234">이 함수는 우편 주소에서 사용 되는 것 처럼 미국 시/도 이름 또는 우편 약자를 찾은 다음 유효한 우편 번호를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-234">This function looks for a U.S. state name or postal abbreviation followed by a valid zip code, just as they're used in postal addresses.</span></span> <span data-ttu-id="427e6-235">우편 번호는 미국 주 이름 또는 약어와 관련된 올바른 우편 번호 중 하나여야 합니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-235">The zip code must be one of the correct zip codes associated with the U.S. state name or abbreviation.</span></span> <span data-ttu-id="427e6-236">미국 주 이름과 우편 번호를 문장 부호나 문자로 구분할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="427e6-236">The U.S. state name and zip code cannot be separated by punctuation or letters.</span></span>
  
<span data-ttu-id="427e6-237">예제:</span><span class="sxs-lookup"><span data-stu-id="427e6-237">Examples:</span></span>
  
- <span data-ttu-id="427e6-238">Washington 98052</span><span class="sxs-lookup"><span data-stu-id="427e6-238">Washington 98052</span></span>
    
- <span data-ttu-id="427e6-239">Washington 98052-9998</span><span class="sxs-lookup"><span data-stu-id="427e6-239">Washington 98052-9998</span></span>
    
- <span data-ttu-id="427e6-240">WA 98052</span><span class="sxs-lookup"><span data-stu-id="427e6-240">WA 98052</span></span>
    
- <span data-ttu-id="427e6-241">WA 98052-9998</span><span class="sxs-lookup"><span data-stu-id="427e6-241">WA 98052-9998</span></span>
    

