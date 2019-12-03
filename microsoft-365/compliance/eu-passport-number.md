---
title: EU 여권 번호
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: 44ee6e7b46d79772bcd3aec0fd26265f58f6c4c6
ms.sourcegitcommit: 3fd6d175c1954ce463198e835d1d8f2f91d80d79
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/02/2019
ms.locfileid: "39662803"
---
# <a name="eu-passport-number"></a><span data-ttu-id="85894-104">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-104">EU Passport Number</span></span>

<span data-ttu-id="85894-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85894-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="85894-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="85894-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="85894-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="85894-108">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-108">Format</span></span>

<span data-ttu-id="85894-109">1 개의 문자 다음에 선택적 공백, 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-110">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-110">Pattern</span></span>

<span data-ttu-id="85894-111">한 글자, 일곱 자리 및 한 가지 공백 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="85894-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="85894-112">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="85894-113">1 개의 공백 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85894-113">One space (optional)</span></span>
    
- <span data-ttu-id="85894-114">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-115">제외</span><span class="sxs-lookup"><span data-stu-id="85894-115">Checksum</span></span>

<span data-ttu-id="85894-116">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-117">정의</span><span class="sxs-lookup"><span data-stu-id="85894-117">Definition</span></span>

<span data-ttu-id="85894-118">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-119">정규식이 해당 `Regex_austria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-120">From `Keywords_austria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-121">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-121">Keywords</span></span>

<span data-ttu-id="85894-122">| |</span><span class="sxs-lookup"><span data-stu-id="85894-122"></span></span>
|<span data-ttu-id="85894-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-124">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-124">passport number</span></span>  <br/> <span data-ttu-id="85894-125">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-125">austrian passport number</span></span>  <br/> <span data-ttu-id="85894-126">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-126">passport no</span></span>  <br/> <span data-ttu-id="85894-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="85894-127">reisepass</span></span>  <br/> <span data-ttu-id="85894-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="85894-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="85894-129">벨기에</span><span class="sxs-lookup"><span data-stu-id="85894-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="85894-130">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-130">Format</span></span>

<span data-ttu-id="85894-131">공백 또는 구분 기호가 없는 2 개 문자 다음에 6 자리 숫자 사용</span><span class="sxs-lookup"><span data-stu-id="85894-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-132">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-132">Pattern</span></span>

<span data-ttu-id="85894-133">2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-134">제외</span><span class="sxs-lookup"><span data-stu-id="85894-134">Checksum</span></span>

<span data-ttu-id="85894-135">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-136">정의</span><span class="sxs-lookup"><span data-stu-id="85894-136">Definition</span></span>

<span data-ttu-id="85894-137">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-138">정규식이 해당 `Regex_belgium_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-139">From `Keywords_belgium_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-140">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-140">Keywords</span></span>

<span data-ttu-id="85894-141">| |</span><span class="sxs-lookup"><span data-stu-id="85894-141"></span></span>
|<span data-ttu-id="85894-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-143">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-143">passport number</span></span>  <br/> <span data-ttu-id="85894-144">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-144">belgian passport number</span></span>  <br/> <span data-ttu-id="85894-145">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-145">passport no</span></span>  <br/> <span data-ttu-id="85894-146">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="85894-146">paspoort</span></span>  <br/> <span data-ttu-id="85894-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="85894-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="85894-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="85894-148">reisepass kein</span></span>  <br/> <span data-ttu-id="85894-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="85894-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="85894-150">불가리아</span><span class="sxs-lookup"><span data-stu-id="85894-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="85894-151">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-151">Format</span></span>

<span data-ttu-id="85894-152">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-153">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-153">Pattern</span></span>

 <span data-ttu-id="85894-154">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85894-155">제외</span><span class="sxs-lookup"><span data-stu-id="85894-155">Checksum</span></span>

<span data-ttu-id="85894-156">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-157">정의</span><span class="sxs-lookup"><span data-stu-id="85894-157">Definition</span></span>

<span data-ttu-id="85894-158">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-159">정규식이 해당 `Regex_bulgaria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-160">From `Keywords_bulgaria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-161">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-161">Keywords</span></span>

<span data-ttu-id="85894-162">| |</span><span class="sxs-lookup"><span data-stu-id="85894-162"></span></span>
|<span data-ttu-id="85894-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-164">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-164">passport number</span></span>  <br/> <span data-ttu-id="85894-165">불가리아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="85894-166">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-166">passport no</span></span>  <br/> <span data-ttu-id="85894-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="85894-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="85894-168">크로아티아</span><span class="sxs-lookup"><span data-stu-id="85894-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="85894-169">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-169">Format</span></span>

<span data-ttu-id="85894-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-171">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-171">Pattern</span></span>

 <span data-ttu-id="85894-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85894-173">제외</span><span class="sxs-lookup"><span data-stu-id="85894-173">Checksum</span></span>

<span data-ttu-id="85894-174">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-175">정의</span><span class="sxs-lookup"><span data-stu-id="85894-175">Definition</span></span>

<span data-ttu-id="85894-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-177">정규식이 해당 `Regex_croatia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-178">From `Keywords_croatia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-179">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-179">Keywords</span></span>

<span data-ttu-id="85894-180">| |</span><span class="sxs-lookup"><span data-stu-id="85894-180"></span></span>
|<span data-ttu-id="85894-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-182">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-182">passport number</span></span>  <br/> <span data-ttu-id="85894-183">크로아티아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-183">croatian passport number</span></span>  <br/> <span data-ttu-id="85894-184">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-184">passport no</span></span>  <br/> <span data-ttu-id="85894-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="85894-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="85894-186">키프로스</span><span class="sxs-lookup"><span data-stu-id="85894-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="85894-187">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-187">Format</span></span>

<span data-ttu-id="85894-188">공백 또는 구분 기호가 없는 1 개 문자 다음에 6-8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-189">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-189">Pattern</span></span>

<span data-ttu-id="85894-190">한 문자 다음에 6 ~ 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-191">제외</span><span class="sxs-lookup"><span data-stu-id="85894-191">Checksum</span></span>

<span data-ttu-id="85894-192">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-193">정의</span><span class="sxs-lookup"><span data-stu-id="85894-193">Definition</span></span>

<span data-ttu-id="85894-194">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-195">정규식이 해당 `Regex_cyprus_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-196">From `Keywords_cyprus_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-197">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-197">Keywords</span></span>

<span data-ttu-id="85894-198">| |</span><span class="sxs-lookup"><span data-stu-id="85894-198"></span></span>
|<span data-ttu-id="85894-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-200">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-200">passport number</span></span>  <br/> <span data-ttu-id="85894-201">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="85894-202">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-202">passport no</span></span>  <br/> <span data-ttu-id="85894-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="85894-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="85894-204">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="85894-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="85894-205">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-205">Format</span></span>

<span data-ttu-id="85894-206">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-207">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-207">Pattern</span></span>

<span data-ttu-id="85894-208">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-209">제외</span><span class="sxs-lookup"><span data-stu-id="85894-209">Checksum</span></span>

<span data-ttu-id="85894-210">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-211">정의</span><span class="sxs-lookup"><span data-stu-id="85894-211">Definition</span></span>

<span data-ttu-id="85894-212">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-213">정규식이 해당 `Regex_czech_republic_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-214">From `Keywords_czech_republic_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-215">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-215">Keywords</span></span>

<span data-ttu-id="85894-216">| |</span><span class="sxs-lookup"><span data-stu-id="85894-216"></span></span>
|<span data-ttu-id="85894-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-218">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-218">passport number</span></span>  <br/> <span data-ttu-id="85894-219">체코어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-219">czech passport number</span></span>  <br/> <span data-ttu-id="85894-220">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-220">passport no</span></span>  <br/> <span data-ttu-id="85894-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="85894-221">cestovní pas</span></span>  <br/> <span data-ttu-id="85894-222">pas</span><span class="sxs-lookup"><span data-stu-id="85894-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="85894-223">덴마크</span><span class="sxs-lookup"><span data-stu-id="85894-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="85894-224">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-224">Format</span></span>

<span data-ttu-id="85894-225">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-226">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-226">Pattern</span></span>

 <span data-ttu-id="85894-227">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85894-228">제외</span><span class="sxs-lookup"><span data-stu-id="85894-228">Checksum</span></span>

<span data-ttu-id="85894-229">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-230">정의</span><span class="sxs-lookup"><span data-stu-id="85894-230">Definition</span></span>

<span data-ttu-id="85894-231">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-232">정규식이 해당 `Regex_denmark_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-233">From `Keywords_denmark_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-234">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-234">Keywords</span></span>

<span data-ttu-id="85894-235">| |</span><span class="sxs-lookup"><span data-stu-id="85894-235"></span></span>
|<span data-ttu-id="85894-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-237">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-237">passport number</span></span>  <br/> <span data-ttu-id="85894-238">덴마크어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-238">danish passport number</span></span>  <br/> <span data-ttu-id="85894-239">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-239">passport no</span></span>  <br/> <span data-ttu-id="85894-240">pas</span><span class="sxs-lookup"><span data-stu-id="85894-240">pas</span></span>  <br/> <span data-ttu-id="85894-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="85894-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="85894-242">에스토니아</span><span class="sxs-lookup"><span data-stu-id="85894-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="85894-243">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-243">Format</span></span>

<span data-ttu-id="85894-244">공백 또는 구분 기호가 없는 1 개 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-245">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-245">Pattern</span></span>

<span data-ttu-id="85894-246">1 개의 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-247">제외</span><span class="sxs-lookup"><span data-stu-id="85894-247">Checksum</span></span>

<span data-ttu-id="85894-248">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-249">정의</span><span class="sxs-lookup"><span data-stu-id="85894-249">Definition</span></span>

<span data-ttu-id="85894-250">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-251">정규식이 해당 `Regex_estonia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-252">From `Keywords_estonia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-253">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-253">Keywords</span></span>

<span data-ttu-id="85894-254">| |</span><span class="sxs-lookup"><span data-stu-id="85894-254"></span></span>
|<span data-ttu-id="85894-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-256">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-256">passport number</span></span>  <br/> <span data-ttu-id="85894-257">에스토니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-257">estonian passport number</span></span>  <br/> <span data-ttu-id="85894-258">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-258">passport no</span></span>  <br/> <span data-ttu-id="85894-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="85894-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="85894-260">핀란드</span><span class="sxs-lookup"><span data-stu-id="85894-260">Finland</span></span>

<span data-ttu-id="85894-261">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"핀란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="85894-262">프랑스</span><span class="sxs-lookup"><span data-stu-id="85894-262">France</span></span>

<span data-ttu-id="85894-263">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"프랑스 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="85894-264">독일</span><span class="sxs-lookup"><span data-stu-id="85894-264">Germany</span></span>

<span data-ttu-id="85894-265">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="85894-266">그리스</span><span class="sxs-lookup"><span data-stu-id="85894-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="85894-267">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-267">Format</span></span>

<span data-ttu-id="85894-268">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="85894-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-269">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-269">Pattern</span></span>

<span data-ttu-id="85894-270">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-271">제외</span><span class="sxs-lookup"><span data-stu-id="85894-271">Checksum</span></span>

<span data-ttu-id="85894-272">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-273">정의</span><span class="sxs-lookup"><span data-stu-id="85894-273">Definition</span></span>

<span data-ttu-id="85894-274">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-275">정규식이 해당 `Regex_greece_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-276">From `Keywords_greece_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-277">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-277">Keywords</span></span>

<span data-ttu-id="85894-278">| |</span><span class="sxs-lookup"><span data-stu-id="85894-278"></span></span>
|<span data-ttu-id="85894-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-280">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-280">passport number</span></span>  <br/> <span data-ttu-id="85894-281">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-281">greek passport number</span></span>  <br/> <span data-ttu-id="85894-282">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-282">passport no</span></span>  <br/> <span data-ttu-id="85894-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="85894-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="85894-284">헝가리</span><span class="sxs-lookup"><span data-stu-id="85894-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="85894-285">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-285">Format</span></span>

<span data-ttu-id="85894-286">공백 또는 구분 기호가 없는 2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-287">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-287">Pattern</span></span>

<span data-ttu-id="85894-288">2 개의 문자 다음에 6 개 또는 7 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-289">제외</span><span class="sxs-lookup"><span data-stu-id="85894-289">Checksum</span></span>

<span data-ttu-id="85894-290">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-291">정의</span><span class="sxs-lookup"><span data-stu-id="85894-291">Definition</span></span>

<span data-ttu-id="85894-292">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-293">정규식이 해당 `Regex_hungary_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-294">From `Keywords_hungary_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-295">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-295">Keywords</span></span>

<span data-ttu-id="85894-296">| |</span><span class="sxs-lookup"><span data-stu-id="85894-296"></span></span>
|<span data-ttu-id="85894-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-298">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-298">passport number</span></span>  <br/> <span data-ttu-id="85894-299">헝가리어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="85894-300">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-300">passport no</span></span>  <br/> <span data-ttu-id="85894-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="85894-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="85894-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="85894-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="85894-303">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-303">Format</span></span>

<span data-ttu-id="85894-304">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-305">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-305">Pattern</span></span>

<span data-ttu-id="85894-306">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85894-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="85894-307">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="85894-308">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-309">제외</span><span class="sxs-lookup"><span data-stu-id="85894-309">Checksum</span></span>

<span data-ttu-id="85894-310">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-311">정의</span><span class="sxs-lookup"><span data-stu-id="85894-311">Definition</span></span>

<span data-ttu-id="85894-312">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-313">정규식이 해당 `Regex_ireland_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-314">From `Keywords_ireland_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-315">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-315">Keywords</span></span>

<span data-ttu-id="85894-316">| |</span><span class="sxs-lookup"><span data-stu-id="85894-316"></span></span>
|<span data-ttu-id="85894-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-318">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-318">passport number</span></span>  <br/> <span data-ttu-id="85894-319">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-319">irish passport number</span></span>  <br/> <span data-ttu-id="85894-320">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-320">passport no</span></span>  <br/> <span data-ttu-id="85894-321">pas</span><span class="sxs-lookup"><span data-stu-id="85894-321">pas</span></span>  <br/> <span data-ttu-id="85894-322">여권</span><span class="sxs-lookup"><span data-stu-id="85894-322">passport</span></span>  <br/> <span data-ttu-id="85894-323">포트</span><span class="sxs-lookup"><span data-stu-id="85894-323">passeport</span></span>  <br/> <span data-ttu-id="85894-324">포트 numero</span><span class="sxs-lookup"><span data-stu-id="85894-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="85894-325">이탈리아</span><span class="sxs-lookup"><span data-stu-id="85894-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="85894-326">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-326">Format</span></span>

<span data-ttu-id="85894-327">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-328">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-328">Pattern</span></span>

<span data-ttu-id="85894-329">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85894-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="85894-330">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="85894-331">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-332">제외</span><span class="sxs-lookup"><span data-stu-id="85894-332">Checksum</span></span>

<span data-ttu-id="85894-333">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-334">정의</span><span class="sxs-lookup"><span data-stu-id="85894-334">Definition</span></span>

<span data-ttu-id="85894-335">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-336">정규식이 해당 `Regex_italy_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-337">From `Keywords_italy_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-338">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-338">Keywords</span></span>

<span data-ttu-id="85894-339">| |</span><span class="sxs-lookup"><span data-stu-id="85894-339"></span></span>
|<span data-ttu-id="85894-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-341">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-341">italian passport number</span></span>  <br/> <span data-ttu-id="85894-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="85894-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="85894-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="85894-343">passaporto</span></span>  <br/> <span data-ttu-id="85894-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="85894-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="85894-345">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-345">passport number</span></span>  <br/> <span data-ttu-id="85894-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="85894-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="85894-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="85894-347">passaporto numero</span></span>  <br/> <span data-ttu-id="85894-348">numéro) 포트 italien</span><span class="sxs-lookup"><span data-stu-id="85894-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="85894-349">numéro (고) 포트</span><span class="sxs-lookup"><span data-stu-id="85894-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="85894-350">라트비아</span><span class="sxs-lookup"><span data-stu-id="85894-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="85894-351">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-351">Format</span></span>

<span data-ttu-id="85894-352">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-353">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-353">Pattern</span></span>

<span data-ttu-id="85894-354">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85894-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="85894-355">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="85894-356">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-357">제외</span><span class="sxs-lookup"><span data-stu-id="85894-357">Checksum</span></span>

<span data-ttu-id="85894-358">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-359">정의</span><span class="sxs-lookup"><span data-stu-id="85894-359">Definition</span></span>

<span data-ttu-id="85894-360">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-361">정규식이 해당 `Regex_latvia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-362">From `Keywords_latvia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-363">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-363">Keywords</span></span>

<span data-ttu-id="85894-364">| |</span><span class="sxs-lookup"><span data-stu-id="85894-364"></span></span>
|<span data-ttu-id="85894-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-366">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-366">passport number</span></span>  <br/> <span data-ttu-id="85894-367">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-367">latvian passport number</span></span>  <br/> <span data-ttu-id="85894-368">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-368">passport no</span></span>  <br/> <span data-ttu-id="85894-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="85894-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="85894-370">리투아니아</span><span class="sxs-lookup"><span data-stu-id="85894-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="85894-371">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-371">Format</span></span>

<span data-ttu-id="85894-372">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="85894-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-373">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-373">Pattern</span></span>

<span data-ttu-id="85894-374">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-375">제외</span><span class="sxs-lookup"><span data-stu-id="85894-375">Checksum</span></span>

<span data-ttu-id="85894-376">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-377">정의</span><span class="sxs-lookup"><span data-stu-id="85894-377">Definition</span></span>

<span data-ttu-id="85894-378">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-379">정규식이 해당 `Regex_lithuania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-380">From `Keywords_lithuania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-381">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-381">Keywords</span></span>

<span data-ttu-id="85894-382">| |</span><span class="sxs-lookup"><span data-stu-id="85894-382"></span></span>
|<span data-ttu-id="85894-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-384">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-384">passport number</span></span>  <br/> <span data-ttu-id="85894-385">lithunian 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="85894-386">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-386">passport no</span></span>  <br/> <span data-ttu-id="85894-387">numeris</span><span class="sxs-lookup"><span data-stu-id="85894-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="85894-388">셈</span><span class="sxs-lookup"><span data-stu-id="85894-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="85894-389">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-389">Format</span></span>

<span data-ttu-id="85894-390">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="85894-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-391">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-391">Pattern</span></span>

<span data-ttu-id="85894-392">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-393">제외</span><span class="sxs-lookup"><span data-stu-id="85894-393">Checksum</span></span>

<span data-ttu-id="85894-394">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-395">정의</span><span class="sxs-lookup"><span data-stu-id="85894-395">Definition</span></span>

<span data-ttu-id="85894-396">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-397">정규식이 해당 `Regex_nation_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-398">From `Keywords_nation_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-399">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-399">Keywords</span></span>

<span data-ttu-id="85894-400">| |</span><span class="sxs-lookup"><span data-stu-id="85894-400"></span></span>
|<span data-ttu-id="85894-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-402">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-402">passport number</span></span>  <br/> <span data-ttu-id="85894-403">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-403">latvian passport number</span></span>  <br/> <span data-ttu-id="85894-404">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-404">passport no</span></span>  <br/> <span data-ttu-id="85894-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="85894-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="85894-406">몰타</span><span class="sxs-lookup"><span data-stu-id="85894-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="85894-407">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-407">Format</span></span>

<span data-ttu-id="85894-408">공백이 나 구분 기호 없이 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-409">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-409">Pattern</span></span>

 <span data-ttu-id="85894-410">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85894-411">제외</span><span class="sxs-lookup"><span data-stu-id="85894-411">Checksum</span></span>

<span data-ttu-id="85894-412">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-413">정의</span><span class="sxs-lookup"><span data-stu-id="85894-413">Definition</span></span>

<span data-ttu-id="85894-414">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-415">정규식이 해당 `Regex_malta_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-416">From `Keywords_malta_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-417">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-417">Keywords</span></span>

<span data-ttu-id="85894-418">| |</span><span class="sxs-lookup"><span data-stu-id="85894-418"></span></span>
|<span data-ttu-id="85894-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-420">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-420">passport number</span></span>  <br/> <span data-ttu-id="85894-421">몰타어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-421">maltese passport number</span></span>  <br/> <span data-ttu-id="85894-422">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-422">passport no</span></span>  <br/> <span data-ttu-id="85894-423">numru-passaport</span><span class="sxs-lookup"><span data-stu-id="85894-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="85894-424">네덜란드</span><span class="sxs-lookup"><span data-stu-id="85894-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="85894-425">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-425">Format</span></span>

<span data-ttu-id="85894-426">공백이 나 구분 기호가 없는 9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-427">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-427">Pattern</span></span>

<span data-ttu-id="85894-428">9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-429">제외</span><span class="sxs-lookup"><span data-stu-id="85894-429">Checksum</span></span>

<span data-ttu-id="85894-430">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-431">정의</span><span class="sxs-lookup"><span data-stu-id="85894-431">Definition</span></span>

<span data-ttu-id="85894-432">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-433">정규식이 해당 `Regex_netherlands_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-434">From `Keywords_netherlands_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-435">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-435">Keywords</span></span>

<span data-ttu-id="85894-436">| |</span><span class="sxs-lookup"><span data-stu-id="85894-436"></span></span>
|<span data-ttu-id="85894-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-438">네덜란드어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-438">dutch passport number</span></span>  <br/> <span data-ttu-id="85894-439">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-439">passport number</span></span>  <br/> <span data-ttu-id="85894-440">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="85894-441">nederlanden, nummer ort</span><span class="sxs-lookup"><span data-stu-id="85894-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="85894-442">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="85894-442">paspoort</span></span>  <br/> <span data-ttu-id="85894-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="85894-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="85894-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="85894-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="85894-445">폴란드</span><span class="sxs-lookup"><span data-stu-id="85894-445">Poland</span></span>

<span data-ttu-id="85894-446">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"폴란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="85894-447">포르투갈</span><span class="sxs-lookup"><span data-stu-id="85894-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="85894-448">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-448">Format</span></span>

<span data-ttu-id="85894-449">공백 또는 구분 기호가 없는 한 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-450">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-450">Pattern</span></span>

<span data-ttu-id="85894-451">1 개의 문자 다음에 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85894-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="85894-452">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85894-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="85894-453">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-454">제외</span><span class="sxs-lookup"><span data-stu-id="85894-454">Checksum</span></span>

<span data-ttu-id="85894-455">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-456">정의</span><span class="sxs-lookup"><span data-stu-id="85894-456">Definition</span></span>

<span data-ttu-id="85894-457">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-458">정규식이 해당 `Regex_portugal_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-459">From `Keywords_portugal_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-460">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-460">Keywords</span></span>

<span data-ttu-id="85894-461">| |</span><span class="sxs-lookup"><span data-stu-id="85894-461"></span></span>
|<span data-ttu-id="85894-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-463">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-463">passport number</span></span>  <br/> <span data-ttu-id="85894-464">포르투갈어 passport 번호</span><span class="sxs-lookup"><span data-stu-id="85894-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="85894-465">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-465">passport no</span></span>  <br/> <span data-ttu-id="85894-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="85894-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="85894-467">루마니아</span><span class="sxs-lookup"><span data-stu-id="85894-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="85894-468">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-468">Format</span></span>

<span data-ttu-id="85894-469">공백과 구분 기호를 사용 하지 않고 8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-470">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-470">Pattern</span></span>

<span data-ttu-id="85894-471">8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-472">제외</span><span class="sxs-lookup"><span data-stu-id="85894-472">Checksum</span></span>

<span data-ttu-id="85894-473">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-474">정의</span><span class="sxs-lookup"><span data-stu-id="85894-474">Definition</span></span>

<span data-ttu-id="85894-475">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-476">정규식이 해당 `Regex_romania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-477">From `Keywords_romania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-478">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-478">Keywords</span></span>

<span data-ttu-id="85894-479">| |</span><span class="sxs-lookup"><span data-stu-id="85894-479"></span></span>
|<span data-ttu-id="85894-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-481">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-481">passport number</span></span>  <br/> <span data-ttu-id="85894-482">루마니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-482">romanian passport number</span></span>  <br/> <span data-ttu-id="85894-483">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-483">passport no</span></span>  <br/> <span data-ttu-id="85894-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="85894-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="85894-485">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="85894-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="85894-486">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-486">Format</span></span>

<span data-ttu-id="85894-487">공백 또는 구분 기호가 없는 한 자리 숫자 또는 문자 다음에 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-488">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-488">Pattern</span></span>

<span data-ttu-id="85894-489">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85894-490">제외</span><span class="sxs-lookup"><span data-stu-id="85894-490">Checksum</span></span>

<span data-ttu-id="85894-491">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-492">정의</span><span class="sxs-lookup"><span data-stu-id="85894-492">Definition</span></span>

<span data-ttu-id="85894-493">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-494">정규식이 해당 `Regex_slovakia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-495">From `Keywords_slovakia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-496">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-496">Keywords</span></span>

<span data-ttu-id="85894-497">| |</span><span class="sxs-lookup"><span data-stu-id="85894-497"></span></span>
|<span data-ttu-id="85894-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-499">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-499">passport number</span></span>  <br/> <span data-ttu-id="85894-500">슬로바키아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="85894-501">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-501">passport no</span></span>  <br/> <span data-ttu-id="85894-502">číslo (u)</span><span class="sxs-lookup"><span data-stu-id="85894-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="85894-503">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="85894-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="85894-504">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-504">Format</span></span>

<span data-ttu-id="85894-505">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="85894-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-506">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-506">Pattern</span></span>

<span data-ttu-id="85894-507">2 개 문자와 7 자리 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="85894-508">"P" 문자</span><span class="sxs-lookup"><span data-stu-id="85894-508">The letter "P"</span></span>
    
- <span data-ttu-id="85894-509">대문자 1 개</span><span class="sxs-lookup"><span data-stu-id="85894-509">One uppercase letter</span></span>
    
- <span data-ttu-id="85894-510">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-511">제외</span><span class="sxs-lookup"><span data-stu-id="85894-511">Checksum</span></span>

<span data-ttu-id="85894-512">아니요</span><span class="sxs-lookup"><span data-stu-id="85894-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-513">정의</span><span class="sxs-lookup"><span data-stu-id="85894-513">Definition</span></span>

<span data-ttu-id="85894-514">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-515">정규식이 해당 `Regex_slovenia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-516">From `Keywords_slovenia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-517">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-517">Keywords</span></span>

<span data-ttu-id="85894-518">| |</span><span class="sxs-lookup"><span data-stu-id="85894-518"></span></span>
|<span data-ttu-id="85894-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-520">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-520">passport number</span></span>  <br/> <span data-ttu-id="85894-521">슬로베니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="85894-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="85894-522">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-522">passport no</span></span>  <br/> <span data-ttu-id="85894-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="85894-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="85894-524">스페인</span><span class="sxs-lookup"><span data-stu-id="85894-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="85894-525">형식일</span><span class="sxs-lookup"><span data-stu-id="85894-525">Format</span></span>

<span data-ttu-id="85894-526">공백이 나 구분 기호가 없는 문자 및 숫자의 8 자리 또는 9 자 조합</span><span class="sxs-lookup"><span data-stu-id="85894-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85894-527">패턴</span><span class="sxs-lookup"><span data-stu-id="85894-527">Pattern</span></span>

<span data-ttu-id="85894-528">문자와 숫자의 8 자리 또는 9 자리 조합:</span><span class="sxs-lookup"><span data-stu-id="85894-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="85894-529">두 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="85894-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="85894-530">1 자리 숫자 또는 문자 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85894-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="85894-531">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85894-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85894-532">제외</span><span class="sxs-lookup"><span data-stu-id="85894-532">Checksum</span></span>

<span data-ttu-id="85894-533">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="85894-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="85894-534">정의</span><span class="sxs-lookup"><span data-stu-id="85894-534">Definition</span></span>

<span data-ttu-id="85894-535">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85894-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85894-536">정규식이 해당 `Regex_spain_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85894-537">From `Keywords_spain_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85894-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85894-538">키워드</span><span class="sxs-lookup"><span data-stu-id="85894-538">Keywords</span></span>

<span data-ttu-id="85894-539">| |</span><span class="sxs-lookup"><span data-stu-id="85894-539"></span></span>
|<span data-ttu-id="85894-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="85894-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="85894-541">여권</span><span class="sxs-lookup"><span data-stu-id="85894-541">passport</span></span>  <br/> <span data-ttu-id="85894-542">스페인 여권</span><span class="sxs-lookup"><span data-stu-id="85894-542">spain passport</span></span>  <br/> <span data-ttu-id="85894-543">passport 책</span><span class="sxs-lookup"><span data-stu-id="85894-543">passport book</span></span>  <br/> <span data-ttu-id="85894-544">passport number</span><span class="sxs-lookup"><span data-stu-id="85894-544">passport number</span></span>  <br/> <span data-ttu-id="85894-545">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="85894-545">passport no</span></span>  <br/> <span data-ttu-id="85894-546">pasaporte</span><span class="sxs-lookup"><span data-stu-id="85894-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="85894-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="85894-547">número pasaporte</span></span>  <br/> <span data-ttu-id="85894-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="85894-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="85894-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="85894-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="85894-550">스웨덴</span><span class="sxs-lookup"><span data-stu-id="85894-550">Sweden</span></span>

<span data-ttu-id="85894-551">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"스웨덴 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="85894-552">영국의</span><span class="sxs-lookup"><span data-stu-id="85894-552">UK</span></span>

<span data-ttu-id="85894-553">자세한 내용은 "미국/영국" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85894-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="85894-554">[중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)Passport 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="85894-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85894-555">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85894-555">See also</span></span>

[<span data-ttu-id="85894-556">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="85894-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

