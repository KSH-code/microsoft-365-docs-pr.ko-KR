---
title: EU 여권 번호
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: fa3be04dec0f71a2568e046abd6b0af3e20181c5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088072"
---
# <a name="eu-passport-number"></a><span data-ttu-id="8b6d1-104">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-104">EU Passport Number</span></span>

<span data-ttu-id="8b6d1-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="8b6d1-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="8b6d1-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-108">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-108">Format</span></span>

<span data-ttu-id="8b6d1-109">1 개의 문자 다음에 선택적 공백, 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-110">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-110">Pattern</span></span>

<span data-ttu-id="8b6d1-111">한 글자, 일곱 자리 및 한 가지 공백 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="8b6d1-112">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8b6d1-113">1 개의 공백 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-113">One space (optional)</span></span>
    
- <span data-ttu-id="8b6d1-114">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-115">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-115">Checksum</span></span>

<span data-ttu-id="8b6d1-116">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-117">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-117">Definition</span></span>

<span data-ttu-id="8b6d1-118">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-119">정규식이 해당 `Regex_austria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-120">From `Keywords_austria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-121">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-121">Keywords</span></span>

<span data-ttu-id="8b6d1-122">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-122"></span></span>
|<span data-ttu-id="8b6d1-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-124">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-124">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-125">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-125">austrian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-126">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-126">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="8b6d1-127">reisepass</span></span>  <br/> <span data-ttu-id="8b6d1-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="8b6d1-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="8b6d1-129">벨기에</span><span class="sxs-lookup"><span data-stu-id="8b6d1-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-130">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-130">Format</span></span>

<span data-ttu-id="8b6d1-131">공백 또는 구분 기호가 없는 2 개 문자 다음에 6 자리 숫자 사용</span><span class="sxs-lookup"><span data-stu-id="8b6d1-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-132">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-132">Pattern</span></span>

<span data-ttu-id="8b6d1-133">2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-134">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-134">Checksum</span></span>

<span data-ttu-id="8b6d1-135">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-136">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-136">Definition</span></span>

<span data-ttu-id="8b6d1-137">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-138">정규식이 해당 `Regex_belgium_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-139">From `Keywords_belgium_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-140">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-140">Keywords</span></span>

<span data-ttu-id="8b6d1-141">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-141"></span></span>
|<span data-ttu-id="8b6d1-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-143">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-143">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-144">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-144">belgian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-145">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-145">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-146">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="8b6d1-146">paspoort</span></span>  <br/> <span data-ttu-id="8b6d1-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b6d1-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="8b6d1-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="8b6d1-148">reisepass kein</span></span>  <br/> <span data-ttu-id="8b6d1-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="8b6d1-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="8b6d1-150">불가리아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-151">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-151">Format</span></span>

<span data-ttu-id="8b6d1-152">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-153">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-153">Pattern</span></span>

 <span data-ttu-id="8b6d1-154">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-155">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-155">Checksum</span></span>

<span data-ttu-id="8b6d1-156">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-157">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-157">Definition</span></span>

<span data-ttu-id="8b6d1-158">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-159">정규식이 해당 `Regex_bulgaria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-160">From `Keywords_bulgaria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-161">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-161">Keywords</span></span>

<span data-ttu-id="8b6d1-162">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-162"></span></span>
|<span data-ttu-id="8b6d1-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-164">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-164">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-165">불가리아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-166">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-166">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="8b6d1-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="8b6d1-168">크로아티아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-169">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-169">Format</span></span>

<span data-ttu-id="8b6d1-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-171">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-171">Pattern</span></span>

 <span data-ttu-id="8b6d1-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-173">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-173">Checksum</span></span>

<span data-ttu-id="8b6d1-174">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-175">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-175">Definition</span></span>

<span data-ttu-id="8b6d1-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-177">정규식이 해당 `Regex_croatia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-178">From `Keywords_croatia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-179">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-179">Keywords</span></span>

<span data-ttu-id="8b6d1-180">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-180"></span></span>
|<span data-ttu-id="8b6d1-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-182">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-182">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-183">크로아티아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-183">croatian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-184">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-184">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="8b6d1-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="8b6d1-186">키프로스</span><span class="sxs-lookup"><span data-stu-id="8b6d1-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-187">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-187">Format</span></span>

<span data-ttu-id="8b6d1-188">공백 또는 구분 기호가 없는 1 개 문자 다음에 6-8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-189">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-189">Pattern</span></span>

<span data-ttu-id="8b6d1-190">한 문자 다음에 6 ~ 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-191">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-191">Checksum</span></span>

<span data-ttu-id="8b6d1-192">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-193">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-193">Definition</span></span>

<span data-ttu-id="8b6d1-194">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-195">정규식이 해당 `Regex_cyprus_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-196">From `Keywords_cyprus_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-197">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-197">Keywords</span></span>

<span data-ttu-id="8b6d1-198">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-198"></span></span>
|<span data-ttu-id="8b6d1-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-200">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-200">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-201">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="8b6d1-202">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-202">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="8b6d1-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="8b6d1-204">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="8b6d1-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-205">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-205">Format</span></span>

<span data-ttu-id="8b6d1-206">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-207">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-207">Pattern</span></span>

<span data-ttu-id="8b6d1-208">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-209">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-209">Checksum</span></span>

<span data-ttu-id="8b6d1-210">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-211">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-211">Definition</span></span>

<span data-ttu-id="8b6d1-212">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-213">정규식이 해당 `Regex_czech_republic_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-214">From `Keywords_czech_republic_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-215">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-215">Keywords</span></span>

<span data-ttu-id="8b6d1-216">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-216"></span></span>
|<span data-ttu-id="8b6d1-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-218">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-218">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-219">체코어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-219">czech passport number</span></span>  <br/> <span data-ttu-id="8b6d1-220">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-220">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="8b6d1-221">cestovní pas</span></span>  <br/> <span data-ttu-id="8b6d1-222">pas</span><span class="sxs-lookup"><span data-stu-id="8b6d1-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="8b6d1-223">덴마크</span><span class="sxs-lookup"><span data-stu-id="8b6d1-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-224">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-224">Format</span></span>

<span data-ttu-id="8b6d1-225">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-226">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-226">Pattern</span></span>

 <span data-ttu-id="8b6d1-227">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-228">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-228">Checksum</span></span>

<span data-ttu-id="8b6d1-229">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-230">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-230">Definition</span></span>

<span data-ttu-id="8b6d1-231">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-232">정규식이 해당 `Regex_denmark_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-233">From `Keywords_denmark_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-234">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-234">Keywords</span></span>

<span data-ttu-id="8b6d1-235">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-235"></span></span>
|<span data-ttu-id="8b6d1-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-237">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-237">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-238">덴마크어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-238">danish passport number</span></span>  <br/> <span data-ttu-id="8b6d1-239">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-239">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-240">pas</span><span class="sxs-lookup"><span data-stu-id="8b6d1-240">pas</span></span>  <br/> <span data-ttu-id="8b6d1-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="8b6d1-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="8b6d1-242">에스토니아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-243">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-243">Format</span></span>

<span data-ttu-id="8b6d1-244">공백 또는 구분 기호가 없는 1 개 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-245">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-245">Pattern</span></span>

<span data-ttu-id="8b6d1-246">1 개의 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-247">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-247">Checksum</span></span>

<span data-ttu-id="8b6d1-248">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-249">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-249">Definition</span></span>

<span data-ttu-id="8b6d1-250">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-251">정규식이 해당 `Regex_estonia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-252">From `Keywords_estonia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-253">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-253">Keywords</span></span>

<span data-ttu-id="8b6d1-254">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-254"></span></span>
|<span data-ttu-id="8b6d1-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-256">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-256">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-257">에스토니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-257">estonian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-258">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-258">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="8b6d1-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="8b6d1-260">핀란드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-260">Finland</span></span>

<span data-ttu-id="8b6d1-261">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"핀란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="8b6d1-262">프랑스</span><span class="sxs-lookup"><span data-stu-id="8b6d1-262">France</span></span>

<span data-ttu-id="8b6d1-263">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"프랑스 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="8b6d1-264">독일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-264">Germany</span></span>

<span data-ttu-id="8b6d1-265">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-265">For details, see the section "Germany Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="8b6d1-266">그리스</span><span class="sxs-lookup"><span data-stu-id="8b6d1-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-267">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-267">Format</span></span>

<span data-ttu-id="8b6d1-268">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-269">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-269">Pattern</span></span>

<span data-ttu-id="8b6d1-270">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-271">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-271">Checksum</span></span>

<span data-ttu-id="8b6d1-272">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-273">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-273">Definition</span></span>

<span data-ttu-id="8b6d1-274">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-275">정규식이 해당 `Regex_greece_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-276">From `Keywords_greece_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-277">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-277">Keywords</span></span>

<span data-ttu-id="8b6d1-278">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-278"></span></span>
|<span data-ttu-id="8b6d1-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-280">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-280">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-281">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-281">greek passport number</span></span>  <br/> <span data-ttu-id="8b6d1-282">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-282">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="8b6d1-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="8b6d1-284">헝가리</span><span class="sxs-lookup"><span data-stu-id="8b6d1-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-285">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-285">Format</span></span>

<span data-ttu-id="8b6d1-286">공백 또는 구분 기호가 없는 2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-287">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-287">Pattern</span></span>

<span data-ttu-id="8b6d1-288">2 개의 문자 다음에 6 개 또는 7 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-289">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-289">Checksum</span></span>

<span data-ttu-id="8b6d1-290">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-291">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-291">Definition</span></span>

<span data-ttu-id="8b6d1-292">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-293">정규식이 해당 `Regex_hungary_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-294">From `Keywords_hungary_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-295">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-295">Keywords</span></span>

<span data-ttu-id="8b6d1-296">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-296"></span></span>
|<span data-ttu-id="8b6d1-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-298">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-298">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-299">헝가리어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-300">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-300">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="8b6d1-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="8b6d1-302">Ireland</span><span class="sxs-lookup"><span data-stu-id="8b6d1-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-303">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-303">Format</span></span>

<span data-ttu-id="8b6d1-304">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-305">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-305">Pattern</span></span>

<span data-ttu-id="8b6d1-306">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="8b6d1-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b6d1-307">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b6d1-308">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-309">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-309">Checksum</span></span>

<span data-ttu-id="8b6d1-310">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-311">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-311">Definition</span></span>

<span data-ttu-id="8b6d1-312">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-313">정규식이 해당 `Regex_ireland_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-314">From `Keywords_ireland_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-315">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-315">Keywords</span></span>

<span data-ttu-id="8b6d1-316">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-316"></span></span>
|<span data-ttu-id="8b6d1-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-318">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-318">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-319">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-319">irish passport number</span></span>  <br/> <span data-ttu-id="8b6d1-320">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-320">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-321">pas</span><span class="sxs-lookup"><span data-stu-id="8b6d1-321">pas</span></span>  <br/> <span data-ttu-id="8b6d1-322">여권</span><span class="sxs-lookup"><span data-stu-id="8b6d1-322">passport</span></span>  <br/> <span data-ttu-id="8b6d1-323">포트</span><span class="sxs-lookup"><span data-stu-id="8b6d1-323">passeport</span></span>  <br/> <span data-ttu-id="8b6d1-324">포트 numero</span><span class="sxs-lookup"><span data-stu-id="8b6d1-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="8b6d1-325">이탈리아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-326">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-326">Format</span></span>

<span data-ttu-id="8b6d1-327">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-328">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-328">Pattern</span></span>

<span data-ttu-id="8b6d1-329">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="8b6d1-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b6d1-330">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b6d1-331">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-332">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-332">Checksum</span></span>

<span data-ttu-id="8b6d1-333">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-334">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-334">Definition</span></span>

<span data-ttu-id="8b6d1-335">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-336">정규식이 해당 `Regex_italy_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-337">From `Keywords_italy_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-338">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-338">Keywords</span></span>

<span data-ttu-id="8b6d1-339">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-339"></span></span>
|<span data-ttu-id="8b6d1-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-341">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-341">italian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="8b6d1-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="8b6d1-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="8b6d1-343">passaporto</span></span>  <br/> <span data-ttu-id="8b6d1-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="8b6d1-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="8b6d1-345">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-345">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8b6d1-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="8b6d1-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="8b6d1-347">passaporto numero</span></span>  <br/> <span data-ttu-id="8b6d1-348">numéro) 포트 italien</span><span class="sxs-lookup"><span data-stu-id="8b6d1-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="8b6d1-349">numéro (고) 포트</span><span class="sxs-lookup"><span data-stu-id="8b6d1-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="8b6d1-350">라트비아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-351">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-351">Format</span></span>

<span data-ttu-id="8b6d1-352">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-353">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-353">Pattern</span></span>

<span data-ttu-id="8b6d1-354">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="8b6d1-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="8b6d1-355">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="8b6d1-356">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-357">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-357">Checksum</span></span>

<span data-ttu-id="8b6d1-358">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-359">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-359">Definition</span></span>

<span data-ttu-id="8b6d1-360">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-361">정규식이 해당 `Regex_latvia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-362">From `Keywords_latvia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-363">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-363">Keywords</span></span>

<span data-ttu-id="8b6d1-364">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-364"></span></span>
|<span data-ttu-id="8b6d1-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-366">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-366">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-367">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-367">latvian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-368">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-368">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="8b6d1-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="8b6d1-370">리투아니아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-371">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-371">Format</span></span>

<span data-ttu-id="8b6d1-372">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-373">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-373">Pattern</span></span>

<span data-ttu-id="8b6d1-374">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-375">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-375">Checksum</span></span>

<span data-ttu-id="8b6d1-376">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-377">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-377">Definition</span></span>

<span data-ttu-id="8b6d1-378">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-379">정규식이 해당 `Regex_lithuania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-380">From `Keywords_lithuania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-381">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-381">Keywords</span></span>

<span data-ttu-id="8b6d1-382">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-382"></span></span>
|<span data-ttu-id="8b6d1-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-384">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-384">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-385">lithunian 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-386">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-386">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-387">numeris</span><span class="sxs-lookup"><span data-stu-id="8b6d1-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="8b6d1-388">셈</span><span class="sxs-lookup"><span data-stu-id="8b6d1-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-389">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-389">Format</span></span>

<span data-ttu-id="8b6d1-390">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-391">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-391">Pattern</span></span>

<span data-ttu-id="8b6d1-392">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-393">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-393">Checksum</span></span>

<span data-ttu-id="8b6d1-394">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-395">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-395">Definition</span></span>

<span data-ttu-id="8b6d1-396">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-397">정규식이 해당 `Regex_nation_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-398">From `Keywords_nation_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-399">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-399">Keywords</span></span>

<span data-ttu-id="8b6d1-400">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-400"></span></span>
|<span data-ttu-id="8b6d1-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-402">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-402">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-403">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-403">latvian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-404">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-404">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="8b6d1-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="8b6d1-406">몰타</span><span class="sxs-lookup"><span data-stu-id="8b6d1-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-407">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-407">Format</span></span>

<span data-ttu-id="8b6d1-408">공백이 나 구분 기호 없이 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-409">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-409">Pattern</span></span>

 <span data-ttu-id="8b6d1-410">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-411">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-411">Checksum</span></span>

<span data-ttu-id="8b6d1-412">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-413">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-413">Definition</span></span>

<span data-ttu-id="8b6d1-414">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-415">정규식이 해당 `Regex_malta_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-416">From `Keywords_malta_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-417">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-417">Keywords</span></span>

<span data-ttu-id="8b6d1-418">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-418"></span></span>
|<span data-ttu-id="8b6d1-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-420">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-420">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-421">몰타어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-421">maltese passport number</span></span>  <br/> <span data-ttu-id="8b6d1-422">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-422">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-423">numru-passaport</span><span class="sxs-lookup"><span data-stu-id="8b6d1-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="8b6d1-424">네덜란드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-425">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-425">Format</span></span>

<span data-ttu-id="8b6d1-426">공백이 나 구분 기호가 없는 9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-427">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-427">Pattern</span></span>

<span data-ttu-id="8b6d1-428">9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-429">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-429">Checksum</span></span>

<span data-ttu-id="8b6d1-430">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-431">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-431">Definition</span></span>

<span data-ttu-id="8b6d1-432">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-433">정규식이 해당 `Regex_netherlands_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-434">From `Keywords_netherlands_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-435">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-435">Keywords</span></span>

<span data-ttu-id="8b6d1-436">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-436"></span></span>
|<span data-ttu-id="8b6d1-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-438">네덜란드어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-438">dutch passport number</span></span>  <br/> <span data-ttu-id="8b6d1-439">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-439">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-440">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="8b6d1-441">nederlanden, nummer ort</span><span class="sxs-lookup"><span data-stu-id="8b6d1-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="8b6d1-442">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="8b6d1-442">paspoort</span></span>  <br/> <span data-ttu-id="8b6d1-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b6d1-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="8b6d1-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="8b6d1-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="8b6d1-445">폴란드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-445">Poland</span></span>

<span data-ttu-id="8b6d1-446">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"폴란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="8b6d1-447">포르투갈</span><span class="sxs-lookup"><span data-stu-id="8b6d1-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-448">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-448">Format</span></span>

<span data-ttu-id="8b6d1-449">공백 또는 구분 기호가 없는 한 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-450">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-450">Pattern</span></span>

<span data-ttu-id="8b6d1-451">1 개의 문자 다음에 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="8b6d1-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="8b6d1-452">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="8b6d1-453">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-454">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-454">Checksum</span></span>

<span data-ttu-id="8b6d1-455">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-456">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-456">Definition</span></span>

<span data-ttu-id="8b6d1-457">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-458">정규식이 해당 `Regex_portugal_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-459">From `Keywords_portugal_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-460">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-460">Keywords</span></span>

<span data-ttu-id="8b6d1-461">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-461"></span></span>
|<span data-ttu-id="8b6d1-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-463">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-463">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-464">포르투갈어 passport 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="8b6d1-465">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-465">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="8b6d1-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="8b6d1-467">루마니아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-468">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-468">Format</span></span>

<span data-ttu-id="8b6d1-469">공백과 구분 기호를 사용 하지 않고 8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-470">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-470">Pattern</span></span>

<span data-ttu-id="8b6d1-471">8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-472">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-472">Checksum</span></span>

<span data-ttu-id="8b6d1-473">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-474">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-474">Definition</span></span>

<span data-ttu-id="8b6d1-475">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-476">정규식이 해당 `Regex_romania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-477">From `Keywords_romania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-478">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-478">Keywords</span></span>

<span data-ttu-id="8b6d1-479">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-479"></span></span>
|<span data-ttu-id="8b6d1-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-481">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-481">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-482">루마니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-482">romanian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-483">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-483">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="8b6d1-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="8b6d1-485">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-486">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-486">Format</span></span>

<span data-ttu-id="8b6d1-487">공백 또는 구분 기호가 없는 한 자리 숫자 또는 문자 다음에 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-488">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-488">Pattern</span></span>

<span data-ttu-id="8b6d1-489">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="8b6d1-490">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-490">Checksum</span></span>

<span data-ttu-id="8b6d1-491">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-492">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-492">Definition</span></span>

<span data-ttu-id="8b6d1-493">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-494">정규식이 해당 `Regex_slovakia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-495">From `Keywords_slovakia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-496">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-496">Keywords</span></span>

<span data-ttu-id="8b6d1-497">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-497"></span></span>
|<span data-ttu-id="8b6d1-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-499">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-499">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-500">슬로바키아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-501">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-501">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-502">číslo (u)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="8b6d1-503">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="8b6d1-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-504">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-504">Format</span></span>

<span data-ttu-id="8b6d1-505">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-506">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-506">Pattern</span></span>

<span data-ttu-id="8b6d1-507">2 개 문자와 7 자리 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="8b6d1-508">"P" 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-508">The letter "P"</span></span>
    
- <span data-ttu-id="8b6d1-509">대문자 1 개</span><span class="sxs-lookup"><span data-stu-id="8b6d1-509">One uppercase letter</span></span>
    
- <span data-ttu-id="8b6d1-510">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-511">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-511">Checksum</span></span>

<span data-ttu-id="8b6d1-512">아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-513">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-513">Definition</span></span>

<span data-ttu-id="8b6d1-514">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-515">정규식이 해당 `Regex_slovenia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-516">From `Keywords_slovenia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-517">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-517">Keywords</span></span>

<span data-ttu-id="8b6d1-518">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-518"></span></span>
|<span data-ttu-id="8b6d1-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-520">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-520">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-521">슬로베니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="8b6d1-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="8b6d1-522">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-522">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="8b6d1-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="8b6d1-524">스페인</span><span class="sxs-lookup"><span data-stu-id="8b6d1-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="8b6d1-525">형식일</span><span class="sxs-lookup"><span data-stu-id="8b6d1-525">Format</span></span>

<span data-ttu-id="8b6d1-526">공백이 나 구분 기호가 없는 문자 및 숫자의 8 자리 또는 9 자 조합</span><span class="sxs-lookup"><span data-stu-id="8b6d1-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="8b6d1-527">패턴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-527">Pattern</span></span>

<span data-ttu-id="8b6d1-528">문자와 숫자의 8 자리 또는 9 자리 조합:</span><span class="sxs-lookup"><span data-stu-id="8b6d1-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="8b6d1-529">두 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="8b6d1-530">1 자리 숫자 또는 문자 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="8b6d1-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="8b6d1-531">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="8b6d1-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="8b6d1-532">제외</span><span class="sxs-lookup"><span data-stu-id="8b6d1-532">Checksum</span></span>

<span data-ttu-id="8b6d1-533">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="8b6d1-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="8b6d1-534">정의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-534">Definition</span></span>

<span data-ttu-id="8b6d1-535">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="8b6d1-536">정규식이 해당 `Regex_spain_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="8b6d1-537">From `Keywords_spain_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="8b6d1-538">키워드</span><span class="sxs-lookup"><span data-stu-id="8b6d1-538">Keywords</span></span>

<span data-ttu-id="8b6d1-539">| |</span><span class="sxs-lookup"><span data-stu-id="8b6d1-539"></span></span>
|<span data-ttu-id="8b6d1-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="8b6d1-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="8b6d1-541">여권</span><span class="sxs-lookup"><span data-stu-id="8b6d1-541">passport</span></span>  <br/> <span data-ttu-id="8b6d1-542">스페인 여권</span><span class="sxs-lookup"><span data-stu-id="8b6d1-542">spain passport</span></span>  <br/> <span data-ttu-id="8b6d1-543">passport 책</span><span class="sxs-lookup"><span data-stu-id="8b6d1-543">passport book</span></span>  <br/> <span data-ttu-id="8b6d1-544">passport number</span><span class="sxs-lookup"><span data-stu-id="8b6d1-544">passport number</span></span>  <br/> <span data-ttu-id="8b6d1-545">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="8b6d1-545">passport no</span></span>  <br/> <span data-ttu-id="8b6d1-546">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b6d1-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="8b6d1-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b6d1-547">número pasaporte</span></span>  <br/> <span data-ttu-id="8b6d1-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b6d1-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="8b6d1-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="8b6d1-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="8b6d1-550">스웨덴</span><span class="sxs-lookup"><span data-stu-id="8b6d1-550">Sweden</span></span>

<span data-ttu-id="8b6d1-551">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"스웨덴 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="8b6d1-552">영국의</span><span class="sxs-lookup"><span data-stu-id="8b6d1-552">UK</span></span>

<span data-ttu-id="8b6d1-553">자세한 내용은 "미국/영국" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="8b6d1-554">[중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)Passport 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="8b6d1-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="8b6d1-555">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8b6d1-555">See also</span></span>

[<span data-ttu-id="8b6d1-556">중요한 정보 형식이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="8b6d1-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

