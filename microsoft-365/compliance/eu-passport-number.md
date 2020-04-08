---
title: EU 여권 번호
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/16/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: 0032d3e50d7dab0b696d9000242e70956469052e
ms.sourcegitcommit: 053d42480d8aa3792ecb0027ddd53d383a029474
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/07/2020
ms.locfileid: "41592119"
---
# <a name="eu-passport-number"></a><span data-ttu-id="c7e3d-104">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-104">EU Passport Number</span></span>

<span data-ttu-id="c7e3d-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU (유럽 여권 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Passport Number sensitive information type.</span></span> <span data-ttu-id="c7e3d-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="c7e3d-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-108">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-108">Format</span></span>

<span data-ttu-id="c7e3d-109">1 개의 문자 다음에 선택적 공백, 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-109">One letter followed by an optional space and seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-110">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-110">Pattern</span></span>

<span data-ttu-id="c7e3d-111">한 글자, 일곱 자리 및 한 가지 공백 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-111">A combination of one letter, seven digits, and one space:</span></span>
  
- <span data-ttu-id="c7e3d-112">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-112">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="c7e3d-113">1 개의 공백 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-113">One space (optional)</span></span>
    
- <span data-ttu-id="c7e3d-114">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-114">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-115">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-115">Checksum</span></span>

<span data-ttu-id="c7e3d-116">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-116">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-117">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-117">Definition</span></span>

<span data-ttu-id="c7e3d-118">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-118">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-119">정규식이 해당 `Regex_austria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-119">The regular expression  `Regex_austria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-120">From `Keywords_austria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-120">A keyword from  `Keywords_austria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_passport_number" />
          <Match idRef="Keywords_austria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-121">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-121">Keywords</span></span>

<span data-ttu-id="c7e3d-122">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-122">| |</span></span>
|<span data-ttu-id="c7e3d-123">**Keywords_austria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-123">**Keywords_austria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-124">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-124">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-125">오스트리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-125">austrian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-126">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-126">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-127">reisepass</span><span class="sxs-lookup"><span data-stu-id="c7e3d-127">reisepass</span></span>  <br/> <span data-ttu-id="c7e3d-128">österreichisch reisepass</span><span class="sxs-lookup"><span data-stu-id="c7e3d-128">österreichisch reisepass</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="c7e3d-129">벨기에</span><span class="sxs-lookup"><span data-stu-id="c7e3d-129">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-130">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-130">Format</span></span>

<span data-ttu-id="c7e3d-131">공백 또는 구분 기호가 없는 2 개 문자 다음에 6 자리 숫자 사용</span><span class="sxs-lookup"><span data-stu-id="c7e3d-131">Two letters followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-132">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-132">Pattern</span></span>

<span data-ttu-id="c7e3d-133">2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-133">Two letters and followed by six digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-134">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-134">Checksum</span></span>

<span data-ttu-id="c7e3d-135">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-135">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-136">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-136">Definition</span></span>

<span data-ttu-id="c7e3d-137">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-137">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-138">정규식이 해당 `Regex_belgium_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-138">The regular expression  `Regex_belgium_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-139">From `Keywords_belgium_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-139">A keyword from  `Keywords_belgium_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium__eu_passport_number" />
          <Match idRef="Keywords_belgium_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-140">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-140">Keywords</span></span>

<span data-ttu-id="c7e3d-141">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-141">| |</span></span>
|<span data-ttu-id="c7e3d-142">**Keywords_belgium_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-142">**Keywords_belgium_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-143">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-143">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-144">벨기에 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-144">belgian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-145">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-145">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-146">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="c7e3d-146">paspoort</span></span>  <br/> <span data-ttu-id="c7e3d-147">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c7e3d-147">paspoortnummer</span></span>  <br/> <span data-ttu-id="c7e3d-148">reisepass kein</span><span class="sxs-lookup"><span data-stu-id="c7e3d-148">reisepass kein</span></span>  <br/> <span data-ttu-id="c7e3d-149">reisepass</span><span class="sxs-lookup"><span data-stu-id="c7e3d-149">reisepass</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="c7e3d-150">불가리아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-150">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-151">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-151">Format</span></span>

<span data-ttu-id="c7e3d-152">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-152">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-153">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-153">Pattern</span></span>

 <span data-ttu-id="c7e3d-154">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-154">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-155">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-155">Checksum</span></span>

<span data-ttu-id="c7e3d-156">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-156">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-157">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-157">Definition</span></span>

<span data-ttu-id="c7e3d-158">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-158">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-159">정규식이 해당 `Regex_bulgaria_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-159">The regular expression  `Regex_bulgaria_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-160">From `Keywords_bulgaria_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-160">A keyword from  `Keywords_bulgaria_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_passport_number" />
          <Match idRef="Keywords_bulgaria_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-161">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-161">Keywords</span></span>

<span data-ttu-id="c7e3d-162">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-162">| |</span></span>
|<span data-ttu-id="c7e3d-163">**Keywords_bulgaria_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-163">**Keywords_bulgaria_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-164">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-164">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-165">불가리아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-165">bulgarian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-166">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-166">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-167">номер на паспорта</span><span class="sxs-lookup"><span data-stu-id="c7e3d-167">номер на паспорта</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="c7e3d-168">크로아티아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-168">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-169">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-169">Format</span></span>

<span data-ttu-id="c7e3d-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-171">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-171">Pattern</span></span>

 <span data-ttu-id="c7e3d-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-172">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-173">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-173">Checksum</span></span>

<span data-ttu-id="c7e3d-174">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-175">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-175">Definition</span></span>

<span data-ttu-id="c7e3d-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-177">정규식이 해당 `Regex_croatia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-177">The regular expression  `Regex_croatia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-178">From `Keywords_croatia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-178">A keyword from  `Keywords_croatia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_passport_number" />
          <Match idRef="Keywords_croatia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-179">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-179">Keywords</span></span>

<span data-ttu-id="c7e3d-180">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-180">| |</span></span>
|<span data-ttu-id="c7e3d-181">**Keywords_croatia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-181">**Keywords_croatia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-182">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-182">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-183">크로아티아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-183">croatian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-184">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-184">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-185">broj putovnice</span><span class="sxs-lookup"><span data-stu-id="c7e3d-185">broj putovnice</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="c7e3d-186">키프로스</span><span class="sxs-lookup"><span data-stu-id="c7e3d-186">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-187">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-187">Format</span></span>

<span data-ttu-id="c7e3d-188">공백 또는 구분 기호가 없는 1 개 문자 다음에 6-8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-188">One letter followed by 6-8 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-189">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-189">Pattern</span></span>

<span data-ttu-id="c7e3d-190">한 문자 다음에 6 ~ 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-190">One letter followed by six to eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-191">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-191">Checksum</span></span>

<span data-ttu-id="c7e3d-192">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-192">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-193">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-193">Definition</span></span>

<span data-ttu-id="c7e3d-194">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-194">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-195">정규식이 해당 `Regex_cyprus_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-195">The regular expression  `Regex_cyprus_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-196">From `Keywords_cyprus_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-196">A keyword from  `Keywords_cyprus_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_passport_number" />
          <Match idRef="Keywords_cyprus_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-197">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-197">Keywords</span></span>

<span data-ttu-id="c7e3d-198">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-198">| |</span></span>
|<span data-ttu-id="c7e3d-199">**Keywords_cyprus_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-199">**Keywords_cyprus_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-200">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-200">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-201">키프로스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-201">cyprus passport number</span></span>  <br/> <span data-ttu-id="c7e3d-202">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-202">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-203">αριθμό διαβατηρίου</span><span class="sxs-lookup"><span data-stu-id="c7e3d-203">αριθμό διαβατηρίου</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="c7e3d-204">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="c7e3d-204">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-205">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-205">Format</span></span>

<span data-ttu-id="c7e3d-206">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-206">Eight digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-207">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-207">Pattern</span></span>

<span data-ttu-id="c7e3d-208">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-208">Eight digits without spaces or delimiters</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-209">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-209">Checksum</span></span>

<span data-ttu-id="c7e3d-210">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-210">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-211">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-211">Definition</span></span>

<span data-ttu-id="c7e3d-212">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-212">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-213">정규식이 해당 `Regex_czech_republic_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-213">The regular expression  `Regex_czech_republic_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-214">From `Keywords_czech_republic_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-214">A keyword from  `Keywords_czech_republic_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_passport_number" />
          <Match idRef="Keywords_czech_republic_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-215">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-215">Keywords</span></span>

<span data-ttu-id="c7e3d-216">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-216">| |</span></span>
|<span data-ttu-id="c7e3d-217">**Keywords_czech_republic_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-217">**Keywords_czech_republic_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-218">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-218">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-219">체코어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-219">czech passport number</span></span>  <br/> <span data-ttu-id="c7e3d-220">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-220">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-221">cestovní pas</span><span class="sxs-lookup"><span data-stu-id="c7e3d-221">cestovní pas</span></span>  <br/> <span data-ttu-id="c7e3d-222">pas</span><span class="sxs-lookup"><span data-stu-id="c7e3d-222">pas</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="c7e3d-223">덴마크</span><span class="sxs-lookup"><span data-stu-id="c7e3d-223">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-224">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-224">Format</span></span>

<span data-ttu-id="c7e3d-225">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-225">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-226">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-226">Pattern</span></span>

 <span data-ttu-id="c7e3d-227">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-227">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-228">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-228">Checksum</span></span>

<span data-ttu-id="c7e3d-229">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-229">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-230">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-230">Definition</span></span>

<span data-ttu-id="c7e3d-231">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-231">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-232">정규식이 해당 `Regex_denmark_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-232">The regular expression  `Regex_denmark_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-233">From `Keywords_denmark_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-233">A keyword from  `Keywords_denmark_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_passport_number" />
          <Match idRef="Keywords_denmark_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-234">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-234">Keywords</span></span>

<span data-ttu-id="c7e3d-235">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-235">| |</span></span>
|<span data-ttu-id="c7e3d-236">**Keywords_denmark_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-236">**Keywords_denmark_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-237">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-237">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-238">덴마크어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-238">danish passport number</span></span>  <br/> <span data-ttu-id="c7e3d-239">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-239">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-240">pas</span><span class="sxs-lookup"><span data-stu-id="c7e3d-240">pas</span></span>  <br/> <span data-ttu-id="c7e3d-241">pasnummer</span><span class="sxs-lookup"><span data-stu-id="c7e3d-241">pasnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="c7e3d-242">에스토니아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-242">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-243">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-243">Format</span></span>

<span data-ttu-id="c7e3d-244">공백 또는 구분 기호가 없는 1 개 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-244">One letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-245">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-245">Pattern</span></span>

<span data-ttu-id="c7e3d-246">1 개의 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-246">One letter followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-247">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-247">Checksum</span></span>

<span data-ttu-id="c7e3d-248">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-248">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-249">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-249">Definition</span></span>

<span data-ttu-id="c7e3d-250">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-250">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-251">정규식이 해당 `Regex_estonia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-251">The regular expression  `Regex_estonia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-252">From `Keywords_estonia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-252">A keyword from  `Keywords_estonia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_passport_number" />
          <Match idRef="Keywords_estonia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-253">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-253">Keywords</span></span>

<span data-ttu-id="c7e3d-254">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-254">| |</span></span>
|<span data-ttu-id="c7e3d-255">**Keywords_estonia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-255">**Keywords_estonia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-256">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-256">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-257">에스토니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-257">estonian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-258">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-258">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-259">eesti kodaniku pass</span><span class="sxs-lookup"><span data-stu-id="c7e3d-259">eesti kodaniku pass</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="c7e3d-260">핀란드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-260">Finland</span></span>

<span data-ttu-id="c7e3d-261">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"핀란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-261">For details, see the section "Finland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="france"></a><span data-ttu-id="c7e3d-262">프랑스</span><span class="sxs-lookup"><span data-stu-id="c7e3d-262">France</span></span>

<span data-ttu-id="c7e3d-263">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"프랑스 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-263">For details, see the section "France Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="c7e3d-264">독일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-264">Germany</span></span>

<span data-ttu-id="c7e3d-265">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-265">For details, see the section "German Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="c7e3d-266">그리스</span><span class="sxs-lookup"><span data-stu-id="c7e3d-266">Greece</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-267">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-267">Format</span></span>

<span data-ttu-id="c7e3d-268">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-268">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-269">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-269">Pattern</span></span>

<span data-ttu-id="c7e3d-270">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-270">Two letters followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-271">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-271">Checksum</span></span>

<span data-ttu-id="c7e3d-272">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-272">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-273">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-273">Definition</span></span>

<span data-ttu-id="c7e3d-274">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-275">정규식이 해당 `Regex_greece_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-275">The regular expression  `Regex_greece_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-276">From `Keywords_greece_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-276">A keyword from  `Keywords_greece_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_passport_number" />
          <Match idRef="Keywords_greece_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-277">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-277">Keywords</span></span>

<span data-ttu-id="c7e3d-278">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-278">| |</span></span>
|<span data-ttu-id="c7e3d-279">**Keywords_greece_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-279">**Keywords_greece_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-280">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-280">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-281">그리스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-281">greek passport number</span></span>  <br/> <span data-ttu-id="c7e3d-282">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-282">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-283">διαβατηριο</span><span class="sxs-lookup"><span data-stu-id="c7e3d-283">διαβατηριο</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="c7e3d-284">헝가리</span><span class="sxs-lookup"><span data-stu-id="c7e3d-284">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-285">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-285">Format</span></span>

<span data-ttu-id="c7e3d-286">공백 또는 구분 기호가 없는 2 개 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-286">Two letters followed by six or seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-287">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-287">Pattern</span></span>

<span data-ttu-id="c7e3d-288">2 개의 문자 다음에 6 개 또는 7 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-288">Two letters followed by six or seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-289">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-289">Checksum</span></span>

<span data-ttu-id="c7e3d-290">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-290">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-291">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-291">Definition</span></span>

<span data-ttu-id="c7e3d-292">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-292">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-293">정규식이 해당 `Regex_hungary_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-293">The regular expression  `Regex_hungary_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-294">From `Keywords_hungary_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-294">A keyword from  `Keywords_hungary_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_passport_number" />
          <Match idRef="Keywords_hungary_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-295">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-295">Keywords</span></span>

<span data-ttu-id="c7e3d-296">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-296">| |</span></span>
|<span data-ttu-id="c7e3d-297">**Keywords_hungary_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-297">**Keywords_hungary_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-298">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-298">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-299">헝가리어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-299">hungarian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-300">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-300">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-301">útlevél száma</span><span class="sxs-lookup"><span data-stu-id="c7e3d-301">útlevél száma</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="c7e3d-302">아일랜드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-302">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-303">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-303">Format</span></span>

<span data-ttu-id="c7e3d-304">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-304">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-305">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-305">Pattern</span></span>

<span data-ttu-id="c7e3d-306">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="c7e3d-306">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c7e3d-307">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-307">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c7e3d-308">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-308">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-309">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-309">Checksum</span></span>

<span data-ttu-id="c7e3d-310">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-310">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-311">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-311">Definition</span></span>

<span data-ttu-id="c7e3d-312">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-312">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-313">정규식이 해당 `Regex_ireland_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-313">The regular expression  `Regex_ireland_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-314">From `Keywords_ireland_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-314">A keyword from  `Keywords_ireland_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_passport_number" />
          <Match idRef="Keywords_ireland_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-315">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-315">Keywords</span></span>

<span data-ttu-id="c7e3d-316">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-316">| |</span></span>
|<span data-ttu-id="c7e3d-317">**Keywords_ireland_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-317">**Keywords_ireland_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-318">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-318">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-319">아일랜드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-319">irish passport number</span></span>  <br/> <span data-ttu-id="c7e3d-320">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-320">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-321">pas</span><span class="sxs-lookup"><span data-stu-id="c7e3d-321">pas</span></span>  <br/> <span data-ttu-id="c7e3d-322">여권</span><span class="sxs-lookup"><span data-stu-id="c7e3d-322">passport</span></span>  <br/> <span data-ttu-id="c7e3d-323">포트</span><span class="sxs-lookup"><span data-stu-id="c7e3d-323">passeport</span></span>  <br/> <span data-ttu-id="c7e3d-324">포트 numero</span><span class="sxs-lookup"><span data-stu-id="c7e3d-324">passeport numero</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="c7e3d-325">이탈리아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-325">Italy</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-326">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-326">Format</span></span>

<span data-ttu-id="c7e3d-327">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-327">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-328">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-328">Pattern</span></span>

<span data-ttu-id="c7e3d-329">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="c7e3d-329">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c7e3d-330">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-330">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c7e3d-331">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-331">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-332">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-332">Checksum</span></span>

<span data-ttu-id="c7e3d-333">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-333">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-334">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-334">Definition</span></span>

<span data-ttu-id="c7e3d-335">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-335">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-336">정규식이 해당 `Regex_italy_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-336">The regular expression  `Regex_italy_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-337">From `Keywords_italy_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-337">A keyword from  `Keywords_italy_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_italy_eu_passport_number" />
          <Match idRef="Keywords_italy_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-338">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-338">Keywords</span></span>

<span data-ttu-id="c7e3d-339">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-339">| |</span></span>
|<span data-ttu-id="c7e3d-340">**Keywords_italy_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-340">**Keywords_italy_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-341">이탈리아 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-341">italian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-342">repubblica italiana passaporto</span><span class="sxs-lookup"><span data-stu-id="c7e3d-342">repubblica italiana passaporto</span></span>  <br/> <span data-ttu-id="c7e3d-343">passaporto</span><span class="sxs-lookup"><span data-stu-id="c7e3d-343">passaporto</span></span>  <br/> <span data-ttu-id="c7e3d-344">passaporto italiana</span><span class="sxs-lookup"><span data-stu-id="c7e3d-344">passaporto italiana</span></span>  <br/> <span data-ttu-id="c7e3d-345">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-345">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-346">italiana passaporto numero</span><span class="sxs-lookup"><span data-stu-id="c7e3d-346">italiana passaporto numero</span></span>  <br/> <span data-ttu-id="c7e3d-347">passaporto numero</span><span class="sxs-lookup"><span data-stu-id="c7e3d-347">passaporto numero</span></span>  <br/> <span data-ttu-id="c7e3d-348">numéro) 포트 italien</span><span class="sxs-lookup"><span data-stu-id="c7e3d-348">numéro passeport italien</span></span>  <br/> <span data-ttu-id="c7e3d-349">numéro (고) 포트</span><span class="sxs-lookup"><span data-stu-id="c7e3d-349">numéro passeport</span></span>  <br/> |
   
## <a name="latvia"></a><span data-ttu-id="c7e3d-350">라트비아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-350">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-351">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-351">Format</span></span>

<span data-ttu-id="c7e3d-352">공백이 나 구분 기호가 없는 두 개의 문자 또는 숫자와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-352">Two letters or digits followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-353">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-353">Pattern</span></span>

<span data-ttu-id="c7e3d-354">두 개의 문자 또는 숫자와 7 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="c7e3d-354">Two letters or digits followed by seven digits:</span></span>
  
- <span data-ttu-id="c7e3d-355">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-355">Two digits or letters (not case sensitive)</span></span>
    
- <span data-ttu-id="c7e3d-356">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-356">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-357">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-357">Checksum</span></span>

<span data-ttu-id="c7e3d-358">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-358">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-359">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-359">Definition</span></span>

<span data-ttu-id="c7e3d-360">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-360">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-361">정규식이 해당 `Regex_latvia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-361">The regular expression  `Regex_latvia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-362">From `Keywords_latvia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-362">A keyword from  `Keywords_latvia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_passport_number" />
          <Match idRef="Keywords_latvia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-363">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-363">Keywords</span></span>

<span data-ttu-id="c7e3d-364">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-364">| |</span></span>
|<span data-ttu-id="c7e3d-365">**Keywords_latvia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-365">**Keywords_latvia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-366">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-366">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-367">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-367">latvian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-368">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-368">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-369">pase numurs</span><span class="sxs-lookup"><span data-stu-id="c7e3d-369">pase numurs</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="c7e3d-370">리투아니아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-370">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-371">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-371">Format</span></span>

<span data-ttu-id="c7e3d-372">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-372">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-373">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-373">Pattern</span></span>

<span data-ttu-id="c7e3d-374">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-374">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-375">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-375">Checksum</span></span>

<span data-ttu-id="c7e3d-376">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-376">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-377">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-377">Definition</span></span>

<span data-ttu-id="c7e3d-378">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-378">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-379">정규식이 해당 `Regex_lithuania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-379">The regular expression  `Regex_lithuania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-380">From `Keywords_lithuania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-380">A keyword from  `Keywords_lithuania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_passport_number" />
          <Match idRef="Keywords_lithuania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-381">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-381">Keywords</span></span>

<span data-ttu-id="c7e3d-382">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-382">| |</span></span>
|<span data-ttu-id="c7e3d-383">**Keywords_lithuania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-383">**Keywords_lithuania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-384">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-384">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-385">lithunian 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-385">lithunian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-386">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-386">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-387">numeris</span><span class="sxs-lookup"><span data-stu-id="c7e3d-387">paso numeris</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="c7e3d-388">셈</span><span class="sxs-lookup"><span data-stu-id="c7e3d-388">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-389">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-389">Format</span></span>

<span data-ttu-id="c7e3d-390">공백이 나 구분 기호가 없는 8 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-390">Eight digits or letters with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-391">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-391">Pattern</span></span>

<span data-ttu-id="c7e3d-392">8 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-392">Eight digits or letters (not case sensitive)</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-393">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-393">Checksum</span></span>

<span data-ttu-id="c7e3d-394">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-394">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-395">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-395">Definition</span></span>

<span data-ttu-id="c7e3d-396">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-396">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-397">정규식이 해당 `Regex_nation_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-397">The regular expression  `Regex_nation_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-398">From `Keywords_nation_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-398">A keyword from  `Keywords_nation_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_nation_eu_passport_number" />
          <Match idRef="Keywords_nation_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-399">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-399">Keywords</span></span>

<span data-ttu-id="c7e3d-400">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-400">| |</span></span>
|<span data-ttu-id="c7e3d-401">**Keywords_nation_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-401">**Keywords_nation_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-402">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-402">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-403">라트비아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-403">latvian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-404">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-404">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-405">passnummer</span><span class="sxs-lookup"><span data-stu-id="c7e3d-405">passnummer</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="c7e3d-406">몰타</span><span class="sxs-lookup"><span data-stu-id="c7e3d-406">Malta</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-407">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-407">Format</span></span>

<span data-ttu-id="c7e3d-408">공백이 나 구분 기호 없이 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-408">Seven digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-409">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-409">Pattern</span></span>

 <span data-ttu-id="c7e3d-410">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-410">Seven digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-411">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-411">Checksum</span></span>

<span data-ttu-id="c7e3d-412">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-412">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-413">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-413">Definition</span></span>

<span data-ttu-id="c7e3d-414">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-414">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-415">정규식이 해당 `Regex_malta_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-415">The regular expression  `Regex_malta_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-416">From `Keywords_malta_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-416">A keyword from  `Keywords_malta_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_passport_number" />
          <Match idRef="Keywords_malta_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-417">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-417">Keywords</span></span>

<span data-ttu-id="c7e3d-418">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-418">| |</span></span>
|<span data-ttu-id="c7e3d-419">**Keywords_malta_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-419">**Keywords_malta_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-420">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-420">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-421">몰타어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-421">maltese passport number</span></span>  <br/> <span data-ttu-id="c7e3d-422">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-422">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-423">numru-passaport</span><span class="sxs-lookup"><span data-stu-id="c7e3d-423">numru tal-passaport</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="c7e3d-424">네덜란드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-424">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-425">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-425">Format</span></span>

<span data-ttu-id="c7e3d-426">공백이 나 구분 기호가 없는 9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-426">Nine letters or digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-427">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-427">Pattern</span></span>

<span data-ttu-id="c7e3d-428">9 개의 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-428">Nine letters or digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-429">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-429">Checksum</span></span>

<span data-ttu-id="c7e3d-430">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-430">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-431">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-431">Definition</span></span>

<span data-ttu-id="c7e3d-432">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-432">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-433">정규식이 해당 `Regex_netherlands_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-433">The regular expression  `Regex_netherlands_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-434">From `Keywords_netherlands_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-434">A keyword from  `Keywords_netherlands_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_passport_number" />
          <Match idRef="Keywords_netherlands_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-435">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-435">Keywords</span></span>

<span data-ttu-id="c7e3d-436">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-436">| |</span></span>
|<span data-ttu-id="c7e3d-437">**Keywords_netherlands_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-437">**Keywords_netherlands_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-438">네덜란드어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-438">dutch passport number</span></span>  <br/> <span data-ttu-id="c7e3d-439">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-439">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-440">네덜란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-440">netherlands passport number</span></span>  <br/> <span data-ttu-id="c7e3d-441">nederlanden, nummer ort</span><span class="sxs-lookup"><span data-stu-id="c7e3d-441">nederlanden paspoort nummer</span></span>  <br/> <span data-ttu-id="c7e3d-442">고 대/ort</span><span class="sxs-lookup"><span data-stu-id="c7e3d-442">paspoort</span></span>  <br/> <span data-ttu-id="c7e3d-443">nederlanden paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c7e3d-443">nederlanden paspoortnummer</span></span>  <br/> <span data-ttu-id="c7e3d-444">paspoortnummer</span><span class="sxs-lookup"><span data-stu-id="c7e3d-444">paspoortnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="c7e3d-445">폴란드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-445">Poland</span></span>

<span data-ttu-id="c7e3d-446">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"폴란드 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-446">For details, see the section "Poland Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="portugal"></a><span data-ttu-id="c7e3d-447">포르투갈</span><span class="sxs-lookup"><span data-stu-id="c7e3d-447">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-448">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-448">Format</span></span>

<span data-ttu-id="c7e3d-449">공백 또는 구분 기호가 없는 한 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-449">One letter followed by six digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-450">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-450">Pattern</span></span>

<span data-ttu-id="c7e3d-451">1 개의 문자 다음에 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="c7e3d-451">One letter followed by six digits:</span></span>
  
- <span data-ttu-id="c7e3d-452">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-452">One letter (not case sensitive)</span></span>
    
- <span data-ttu-id="c7e3d-453">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-453">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-454">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-454">Checksum</span></span>

<span data-ttu-id="c7e3d-455">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-455">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-456">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-456">Definition</span></span>

<span data-ttu-id="c7e3d-457">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-457">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-458">정규식이 해당 `Regex_portugal_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-458">The regular expression  `Regex_portugal_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-459">From `Keywords_portugal_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-459">A keyword from  `Keywords_portugal_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_passport_number" />
          <Match idRef="Keywords_portugal_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-460">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-460">Keywords</span></span>

<span data-ttu-id="c7e3d-461">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-461">| |</span></span>
|<span data-ttu-id="c7e3d-462">**Keywords_portugal_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-462">**Keywords_portugal_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-463">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-463">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-464">포르투갈어 passport 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-464">portuguese passport number</span></span>  <br/> <span data-ttu-id="c7e3d-465">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-465">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-466">número do passaporte</span><span class="sxs-lookup"><span data-stu-id="c7e3d-466">número do passaporte</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="c7e3d-467">루마니아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-467">Romania</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-468">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-468">Format</span></span>

<span data-ttu-id="c7e3d-469">공백과 구분 기호를 사용 하지 않고 8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-469">Eight or nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-470">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-470">Pattern</span></span>

<span data-ttu-id="c7e3d-471">8 또는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-471">Eight or nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-472">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-472">Checksum</span></span>

<span data-ttu-id="c7e3d-473">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-473">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-474">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-474">Definition</span></span>

<span data-ttu-id="c7e3d-475">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-475">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-476">정규식이 해당 `Regex_romania_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-476">The regular expression  `Regex_romania_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-477">From `Keywords_romania_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-477">A keyword from  `Keywords_romania_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_passport_number" />
          <Match idRef="Keywords_romania_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-478">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-478">Keywords</span></span>

<span data-ttu-id="c7e3d-479">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-479">| |</span></span>
|<span data-ttu-id="c7e3d-480">**Keywords_romania_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-480">**Keywords_romania_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-481">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-481">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-482">루마니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-482">romanian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-483">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-483">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-484">numărul pașaportului</span><span class="sxs-lookup"><span data-stu-id="c7e3d-484">numărul pașaportului</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="c7e3d-485">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-485">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-486">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-486">Format</span></span>

<span data-ttu-id="c7e3d-487">공백 또는 구분 기호가 없는 한 자리 숫자 또는 문자 다음에 일곱 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-487">One digit or letter followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-488">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-488">Pattern</span></span>

<span data-ttu-id="c7e3d-489">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)와 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-489">One digit or letter (not case sensitive) followed by seven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="c7e3d-490">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-490">Checksum</span></span>

<span data-ttu-id="c7e3d-491">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-491">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-492">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-492">Definition</span></span>

<span data-ttu-id="c7e3d-493">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-493">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-494">정규식이 해당 `Regex_slovakia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-494">The regular expression  `Regex_slovakia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-495">From `Keywords_slovakia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-495">A keyword from  `Keywords_slovakia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_passport_number" />
          <Match idRef="Keywords_slovakia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-496">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-496">Keywords</span></span>

<span data-ttu-id="c7e3d-497">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-497">| |</span></span>
|<span data-ttu-id="c7e3d-498">**Keywords_slovakia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-498">**Keywords_slovakia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-499">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-499">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-500">슬로바키아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-500">slovakian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-501">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-501">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-502">číslo (u)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-502">číslo pasu</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="c7e3d-503">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="c7e3d-503">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-504">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-504">Format</span></span>

<span data-ttu-id="c7e3d-505">공백 또는 구분 기호가 없는 7 자리, 두 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-505">Two letters followed by seven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-506">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-506">Pattern</span></span>

<span data-ttu-id="c7e3d-507">2 개 문자와 7 자리 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-507">Two letters followed by seven digits:</span></span>
  
- <span data-ttu-id="c7e3d-508">"P" 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-508">The letter "P"</span></span>
    
- <span data-ttu-id="c7e3d-509">대문자 1 개</span><span class="sxs-lookup"><span data-stu-id="c7e3d-509">One uppercase letter</span></span>
    
- <span data-ttu-id="c7e3d-510">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-510">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-511">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-511">Checksum</span></span>

<span data-ttu-id="c7e3d-512">아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-512">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-513">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-513">Definition</span></span>

<span data-ttu-id="c7e3d-514">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-514">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-515">정규식이 해당 `Regex_slovenia_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-515">The regular expression  `Regex_slovenia_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-516">From `Keywords_slovenia_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-516">A keyword from  `Keywords_slovenia_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_passport_number" />
          <Match idRef="Keywords_slovenia_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-517">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-517">Keywords</span></span>

<span data-ttu-id="c7e3d-518">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-518">| |</span></span>
|<span data-ttu-id="c7e3d-519">**Keywords_slovenia_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-519">**Keywords_slovenia_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-520">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-520">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-521">슬로베니아어 여권 번호</span><span class="sxs-lookup"><span data-stu-id="c7e3d-521">slovenian passport number</span></span>  <br/> <span data-ttu-id="c7e3d-522">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-522">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-523">številka potnega lista</span><span class="sxs-lookup"><span data-stu-id="c7e3d-523">številka potnega lista</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="c7e3d-524">스페인</span><span class="sxs-lookup"><span data-stu-id="c7e3d-524">Spain</span></span>

### <a name="format"></a><span data-ttu-id="c7e3d-525">형식일</span><span class="sxs-lookup"><span data-stu-id="c7e3d-525">Format</span></span>

<span data-ttu-id="c7e3d-526">공백이 나 구분 기호가 없는 문자 및 숫자의 8 자리 또는 9 자 조합</span><span class="sxs-lookup"><span data-stu-id="c7e3d-526">An eight- or nine-character combination of letters and numbers with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="c7e3d-527">패턴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-527">Pattern</span></span>

<span data-ttu-id="c7e3d-528">문자와 숫자의 8 자리 또는 9 자리 조합:</span><span class="sxs-lookup"><span data-stu-id="c7e3d-528">An eight- or nine-character combination of letters and numbers:</span></span>
  
-  <span data-ttu-id="c7e3d-529">두 자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-529">Two digits or letters</span></span> 
    
- <span data-ttu-id="c7e3d-530">1 자리 숫자 또는 문자 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="c7e3d-530">One digit or letter (optional)</span></span>
    
- <span data-ttu-id="c7e3d-531">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="c7e3d-531">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="c7e3d-532">제외</span><span class="sxs-lookup"><span data-stu-id="c7e3d-532">Checksum</span></span>

<span data-ttu-id="c7e3d-533">해당 없음</span><span class="sxs-lookup"><span data-stu-id="c7e3d-533">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="c7e3d-534">정의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-534">Definition</span></span>

<span data-ttu-id="c7e3d-535">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-535">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="c7e3d-536">정규식이 해당 `Regex_spain_eu_passport_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-536">The regular expression  `Regex_spain_eu_passport_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="c7e3d-537">From `Keywords_spain_eu_passport_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-537">A keyword from  `Keywords_spain_eu_passport_number` is found.</span></span> 
    
```
 <!-- EU Passport Number -->
<Entity id="21883626-6245-4f3d-9b61-5cbb43e625ee" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_spain_eu_passport_number" />
          <Match idRef="Keywords_spain_eu_passport_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="c7e3d-538">키워드</span><span class="sxs-lookup"><span data-stu-id="c7e3d-538">Keywords</span></span>

<span data-ttu-id="c7e3d-539">| |</span><span class="sxs-lookup"><span data-stu-id="c7e3d-539">| |</span></span>
|<span data-ttu-id="c7e3d-540">**Keywords_spain_eu_passport_number**</span><span class="sxs-lookup"><span data-stu-id="c7e3d-540">**Keywords_spain_eu_passport_number**</span></span>|
|:-----|
|<span data-ttu-id="c7e3d-541">여권</span><span class="sxs-lookup"><span data-stu-id="c7e3d-541">passport</span></span>  <br/> <span data-ttu-id="c7e3d-542">스페인 여권</span><span class="sxs-lookup"><span data-stu-id="c7e3d-542">spain passport</span></span>  <br/> <span data-ttu-id="c7e3d-543">passport 책</span><span class="sxs-lookup"><span data-stu-id="c7e3d-543">passport book</span></span>  <br/> <span data-ttu-id="c7e3d-544">passport number</span><span class="sxs-lookup"><span data-stu-id="c7e3d-544">passport number</span></span>  <br/> <span data-ttu-id="c7e3d-545">passport 아니요</span><span class="sxs-lookup"><span data-stu-id="c7e3d-545">passport no</span></span>  <br/> <span data-ttu-id="c7e3d-546">pasaporte</span><span class="sxs-lookup"><span data-stu-id="c7e3d-546">libreta pasaporte</span></span>  <br/> <span data-ttu-id="c7e3d-547">número pasaporte</span><span class="sxs-lookup"><span data-stu-id="c7e3d-547">número pasaporte</span></span>  <br/> <span data-ttu-id="c7e3d-548">españa pasaporte</span><span class="sxs-lookup"><span data-stu-id="c7e3d-548">españa pasaporte</span></span>  <br/> <span data-ttu-id="c7e3d-549">pasaporte</span><span class="sxs-lookup"><span data-stu-id="c7e3d-549">pasaporte</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="c7e3d-550">스웨덴</span><span class="sxs-lookup"><span data-stu-id="c7e3d-550">Sweden</span></span>

<span data-ttu-id="c7e3d-551">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"스웨덴 여권 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-551">For details, see the section "Sweden Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="uk"></a><span data-ttu-id="c7e3d-552">영국의</span><span class="sxs-lookup"><span data-stu-id="c7e3d-552">UK</span></span>

<span data-ttu-id="c7e3d-553">자세한 내용은 "미국/영국" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-553">For details, see the section "U.S. / U.K.</span></span> <span data-ttu-id="c7e3d-554">[중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)Passport 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="c7e3d-554">Passport Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="c7e3d-555">참고 항목</span><span class="sxs-lookup"><span data-stu-id="c7e3d-555">See also</span></span>

[<span data-ttu-id="c7e3d-556">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="c7e3d-556">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

