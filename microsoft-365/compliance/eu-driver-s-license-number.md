---
title: EU 운전 면허 번호
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: 2e75a8724dc91ef2d895c977fdd5fcc21e7a1da4
ms.sourcegitcommit: c7f11d851073ef14a69669f6c8b7e0c11e4bb7a1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/29/2020
ms.locfileid: "43938832"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="e8633-104">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-104">EU Driver's License Number</span></span>

<span data-ttu-id="e8633-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="e8633-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="e8633-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="e8633-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="e8633-108">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-108">Format</span></span>

<span data-ttu-id="e8633-109">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-110">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-110">Pattern</span></span>

<span data-ttu-id="e8633-111">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-112">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-112">Checksum</span></span>

<span data-ttu-id="e8633-113">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-114">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-114">Definition</span></span>

<span data-ttu-id="e8633-115">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-116">정규식이 해당 `Regex_austria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-117">From `Keywords_austria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="e8633-118">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-118">Keywords</span></span>

<span data-ttu-id="e8633-119">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-119">| |</span></span>
|<span data-ttu-id="e8633-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-121">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-121">dl#</span></span>  <br/> <span data-ttu-id="e8633-122">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-122">driver license</span></span>  <br/> <span data-ttu-id="e8633-123">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-123">driver license number</span></span>  <br/> <span data-ttu-id="e8633-124">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-124">driver licence</span></span>  <br/> <span data-ttu-id="e8633-125">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-125">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-126">drivers license</span></span>  <br/> <span data-ttu-id="e8633-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="e8633-127">driver's licence</span></span>  <br/> <span data-ttu-id="e8633-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-128">driver's license</span></span>  <br/> <span data-ttu-id="e8633-129">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-129">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-130">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="e8633-131">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-131">driving license number</span></span>  <br/> <span data-ttu-id="e8633-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-132">dlno#</span></span>  <br/> <span data-ttu-id="e8633-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="e8633-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="e8633-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="e8633-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="e8633-135">벨기에</span><span class="sxs-lookup"><span data-stu-id="e8633-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="e8633-136">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-136">Format</span></span>

<span data-ttu-id="e8633-137">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-138">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-138">Pattern</span></span>

<span data-ttu-id="e8633-139">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-140">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-140">Checksum</span></span>

<span data-ttu-id="e8633-141">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-142">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-142">Definition</span></span>

<span data-ttu-id="e8633-143">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-144">정규식이 해당 `Regex_belgium_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-145">From `Keywords_belgium_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e8633-146">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-146">Keywords</span></span>

<span data-ttu-id="e8633-147">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-147">| |</span></span>
|<span data-ttu-id="e8633-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-149">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-149">dl#</span></span>  <br/> <span data-ttu-id="e8633-150">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-150">driver license</span></span>  <br/> <span data-ttu-id="e8633-151">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-151">driver license number</span></span>  <br/> <span data-ttu-id="e8633-152">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-152">driver licence</span></span>  <br/> <span data-ttu-id="e8633-153">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-153">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-154">drivers license</span></span>  <br/> <span data-ttu-id="e8633-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-155">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-156">driver's license</span></span>  <br/> <span data-ttu-id="e8633-157">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-157">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-158">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-158">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-159">dlno#</span></span>  <br/> <span data-ttu-id="e8633-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="e8633-160">rijbewijs</span></span>  <br/> <span data-ttu-id="e8633-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="e8633-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="e8633-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="e8633-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="e8633-165">führerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="e8633-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="e8633-166">fuehrerschein-Veiligheid</span><span class="sxs-lookup"><span data-stu-id="e8633-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="e8633-167">fuehrerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="e8633-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="e8633-168">불가리아</span><span class="sxs-lookup"><span data-stu-id="e8633-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="e8633-169">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-169">Format</span></span>

<span data-ttu-id="e8633-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-171">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-171">Pattern</span></span>

<span data-ttu-id="e8633-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-173">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-173">Checksum</span></span>

<span data-ttu-id="e8633-174">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-175">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-175">Definition</span></span>

<span data-ttu-id="e8633-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-177">정규식이 해당 `Regex_bulgaria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-178">From `Keywords_bulgaria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="e8633-179">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-179">Keywords</span></span>

<span data-ttu-id="e8633-180">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-180">| |</span></span>
|<span data-ttu-id="e8633-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-182">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-182">dl#</span></span>  <br/> <span data-ttu-id="e8633-183">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-183">driver license</span></span>  <br/> <span data-ttu-id="e8633-184">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-184">driver license number</span></span>  <br/> <span data-ttu-id="e8633-185">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-185">driver licence</span></span>  <br/> <span data-ttu-id="e8633-186">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-186">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-187">drivers license</span></span>  <br/> <span data-ttu-id="e8633-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-188">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-189">driver's license</span></span>  <br/> <span data-ttu-id="e8633-190">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-190">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-191">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-191">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-192">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-192">driving license number</span></span>  <br/> <span data-ttu-id="e8633-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-193">dlno#</span></span>  <br/> <span data-ttu-id="e8633-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="e8633-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="e8633-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="e8633-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="e8633-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="e8633-196">сумпс</span></span>  <br/> <span data-ttu-id="e8633-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="e8633-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="e8633-198">크로아티아</span><span class="sxs-lookup"><span data-stu-id="e8633-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="e8633-199">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-199">Format</span></span>

<span data-ttu-id="e8633-200">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-201">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-201">Pattern</span></span>

<span data-ttu-id="e8633-202">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-203">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-203">Checksum</span></span>

<span data-ttu-id="e8633-204">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-205">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-205">Definition</span></span>

<span data-ttu-id="e8633-206">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-207">정규식이 해당 `Regex_croatia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-208">From `Keywords_croatia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e8633-209">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-209">Keywords</span></span>

<span data-ttu-id="e8633-210">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-210">| |</span></span>
|<span data-ttu-id="e8633-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-212">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-212">dl#</span></span>  <br/> <span data-ttu-id="e8633-213">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-213">driver license</span></span>  <br/> <span data-ttu-id="e8633-214">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-214">driver license number</span></span>  <br/> <span data-ttu-id="e8633-215">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-215">driver licence</span></span>  <br/> <span data-ttu-id="e8633-216">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-216">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-217">drivers license</span></span>  <br/> <span data-ttu-id="e8633-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-218">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-219">driver's license</span></span>  <br/> <span data-ttu-id="e8633-220">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-220">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-221">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-221">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-222">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-222">driving license number</span></span>  <br/> <span data-ttu-id="e8633-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-223">dlno#</span></span>  <br/> <span data-ttu-id="e8633-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="e8633-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="e8633-225">키프로스</span><span class="sxs-lookup"><span data-stu-id="e8633-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="e8633-226">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-226">Format</span></span>

<span data-ttu-id="e8633-227">공백과 구분 기호를 사용 하지 않고 12 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-228">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-228">Pattern</span></span>

<span data-ttu-id="e8633-229">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-230">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-230">Checksum</span></span>

<span data-ttu-id="e8633-231">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-232">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-232">Definition</span></span>

<span data-ttu-id="e8633-233">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-234">정규식이 해당 `Regex_cyprus_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-235">From `Keywords_cyprus_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-236">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-236">Keywords</span></span>

<span data-ttu-id="e8633-237">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-237">| |</span></span>
|<span data-ttu-id="e8633-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-239">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-239">dl#</span></span>  <br/> <span data-ttu-id="e8633-240">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-240">driver license</span></span>  <br/> <span data-ttu-id="e8633-241">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-241">driver license number</span></span>  <br/> <span data-ttu-id="e8633-242">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-242">driver licence</span></span>  <br/> <span data-ttu-id="e8633-243">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-243">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-244">drivers license</span></span>  <br/> <span data-ttu-id="e8633-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-245">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-246">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-246">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-247">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-247">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-248">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-248">driving license number</span></span>  <br/> <span data-ttu-id="e8633-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-249">dlno#</span></span>  <br/> <span data-ttu-id="e8633-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="e8633-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="e8633-251">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="e8633-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="e8633-252">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-252">Format</span></span>

<span data-ttu-id="e8633-253">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-254">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-254">Pattern</span></span>

<span data-ttu-id="e8633-255">8 개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="e8633-256">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="e8633-257">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e8633-257">A space (optional)</span></span>
    
- <span data-ttu-id="e8633-258">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-259">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-259">Checksum</span></span>

<span data-ttu-id="e8633-260">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-261">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-261">Definition</span></span>

<span data-ttu-id="e8633-262">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-263">정규식이 해당 `Regex_czech_republic_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-264">From `Keywords_czech_republic_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e8633-265">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-265">Keywords</span></span>

<span data-ttu-id="e8633-266">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-266">| |</span></span>
|<span data-ttu-id="e8633-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-268">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-268">dl#</span></span>  <br/> <span data-ttu-id="e8633-269">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-269">driver license</span></span>  <br/> <span data-ttu-id="e8633-270">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-270">driver license number</span></span>  <br/> <span data-ttu-id="e8633-271">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-271">driver licence</span></span>  <br/> <span data-ttu-id="e8633-272">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-272">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-273">drivers license</span></span>  <br/> <span data-ttu-id="e8633-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-274">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-275">driver's license</span></span>  <br/> <span data-ttu-id="e8633-276">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-276">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-277">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-277">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-278">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-278">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-279">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-279">driving license number</span></span>  <br/> <span data-ttu-id="e8633-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-280">dlno#</span></span>  <br/> <span data-ttu-id="e8633-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="e8633-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="e8633-282">덴마크</span><span class="sxs-lookup"><span data-stu-id="e8633-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="e8633-283">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-283">Format</span></span>

<span data-ttu-id="e8633-284">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-285">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-285">Pattern</span></span>

<span data-ttu-id="e8633-286">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-287">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-287">Checksum</span></span>

<span data-ttu-id="e8633-288">예</span><span class="sxs-lookup"><span data-stu-id="e8633-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-289">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-289">Definition</span></span>

<span data-ttu-id="e8633-290">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-291">정규식이 해당 `Regex_denmark_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-292">From `Keywords_denmark_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="e8633-293">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-293">Keywords</span></span>

<span data-ttu-id="e8633-294">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-294">| |</span></span>
|<span data-ttu-id="e8633-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-296">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-296">dl#</span></span>  <br/> <span data-ttu-id="e8633-297">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-297">driver license</span></span>  <br/> <span data-ttu-id="e8633-298">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-298">driver license number</span></span>  <br/> <span data-ttu-id="e8633-299">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-299">driver licence</span></span>  <br/> <span data-ttu-id="e8633-300">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-300">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-301">drivers license</span></span>  <br/> <span data-ttu-id="e8633-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-302">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-303">driver's license</span></span>  <br/> <span data-ttu-id="e8633-304">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-304">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-305">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-305">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-306">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-306">driving license number</span></span>  <br/> <span data-ttu-id="e8633-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-307">dlno#</span></span>  <br/> <span data-ttu-id="e8633-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="e8633-308">kørekort</span></span>  <br/> <span data-ttu-id="e8633-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="e8633-310">에스토니아</span><span class="sxs-lookup"><span data-stu-id="e8633-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="e8633-311">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-311">Format</span></span>

<span data-ttu-id="e8633-312">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-313">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-313">Pattern</span></span>

<span data-ttu-id="e8633-314">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="e8633-315">문자 "ET" (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e8633-316">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-317">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-317">Checksum</span></span>

<span data-ttu-id="e8633-318">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-319">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-319">Definition</span></span>

<span data-ttu-id="e8633-320">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-321">정규식이 해당 `Regex_estonia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-322">From `Keywords_estonia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-323">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-323">Keywords</span></span>

<span data-ttu-id="e8633-324">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-324">| |</span></span>
|<span data-ttu-id="e8633-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-326">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-326">dl#</span></span>  <br/> <span data-ttu-id="e8633-327">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-327">driver license</span></span>  <br/> <span data-ttu-id="e8633-328">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-328">driver license number</span></span>  <br/> <span data-ttu-id="e8633-329">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-329">driver license number</span></span>  <br/> <span data-ttu-id="e8633-330">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-330">driver licence</span></span>  <br/> <span data-ttu-id="e8633-331">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-331">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-332">drivers license</span></span>  <br/> <span data-ttu-id="e8633-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-333">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-334">driver's license</span></span>  <br/> <span data-ttu-id="e8633-335">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-335">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-336">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-336">driving license number</span></span>  <br/> <span data-ttu-id="e8633-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-337">dlno#</span></span>  <br/> <span data-ttu-id="e8633-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="e8633-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="e8633-339">핀란드</span><span class="sxs-lookup"><span data-stu-id="e8633-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="e8633-340">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-340">Format</span></span>

<span data-ttu-id="e8633-341">하이픈을 포함하는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-342">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-342">Pattern</span></span>

<span data-ttu-id="e8633-343">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="e8633-344">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-344">Six digits</span></span> 
    
- <span data-ttu-id="e8633-345">하이픈</span><span class="sxs-lookup"><span data-stu-id="e8633-345">A hyphen</span></span>
    
-  <span data-ttu-id="e8633-346">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8633-347">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-347">Checksum</span></span>

<span data-ttu-id="e8633-348">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-349">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-349">Definition</span></span>

<span data-ttu-id="e8633-350">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-351">정규식이 해당 `Regex_finland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-352">From `Keywords_finland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-353">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-353">Keywords</span></span>

<span data-ttu-id="e8633-354">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-354">| |</span></span>
|<span data-ttu-id="e8633-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-356">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-356">dl#</span></span>  <br/> <span data-ttu-id="e8633-357">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-357">driver license</span></span>  <br/> <span data-ttu-id="e8633-358">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-358">driver license number</span></span>  <br/> <span data-ttu-id="e8633-359">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-359">driver licence</span></span>  <br/> <span data-ttu-id="e8633-360">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-360">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-361">drivers license</span></span>  <br/> <span data-ttu-id="e8633-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-362">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-363">driver's license</span></span>  <br/> <span data-ttu-id="e8633-364">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-364">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-365">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-365">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-366">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-366">driving license number</span></span>  <br/> <span data-ttu-id="e8633-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-367">dlno#</span></span>  <br/> <span data-ttu-id="e8633-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="e8633-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="e8633-369">프랑스</span><span class="sxs-lookup"><span data-stu-id="e8633-369">France</span></span>

<span data-ttu-id="e8633-370">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"경기도 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8633-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="e8633-371">독일</span><span class="sxs-lookup"><span data-stu-id="e8633-371">Germany</span></span>

<span data-ttu-id="e8633-372">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일어 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8633-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="e8633-373">그리스</span><span class="sxs-lookup"><span data-stu-id="e8633-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="e8633-374">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-374">Format</span></span>

<span data-ttu-id="e8633-375">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-376">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-376">Pattern</span></span>

 <span data-ttu-id="e8633-377">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e8633-378">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-378">Checksum</span></span>

<span data-ttu-id="e8633-379">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-380">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-380">Definition</span></span>

<span data-ttu-id="e8633-381">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-382">정규식이 해당 `Regex_greece_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-383">From `Keywords_greece_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-384">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-384">Keywords</span></span>

<span data-ttu-id="e8633-385">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-385">| |</span></span>
|<span data-ttu-id="e8633-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="e8633-387">dlL#</span></span>  <br/> <span data-ttu-id="e8633-388">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-388">driver license</span></span>  <br/> <span data-ttu-id="e8633-389">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-389">driver license number</span></span>  <br/> <span data-ttu-id="e8633-390">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-390">driver licence</span></span>  <br/> <span data-ttu-id="e8633-391">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-391">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-392">drivers license</span></span>  <br/> <span data-ttu-id="e8633-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-393">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-394">driver's license</span></span>  <br/> <span data-ttu-id="e8633-395">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-395">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-396">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-396">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-397">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-397">driving license number</span></span>  <br/> <span data-ttu-id="e8633-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-398">dlno#</span></span>  <br/> <span data-ttu-id="e8633-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="e8633-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="e8633-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="e8633-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="e8633-401">헝가리</span><span class="sxs-lookup"><span data-stu-id="e8633-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="e8633-402">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-402">Format</span></span>

<span data-ttu-id="e8633-403">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-404">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-404">Pattern</span></span>

<span data-ttu-id="e8633-405">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="e8633-406">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e8633-407">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-408">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-408">Checksum</span></span>

<span data-ttu-id="e8633-409">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-410">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-410">Definition</span></span>

<span data-ttu-id="e8633-411">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-412">정규식이 해당 `Regex_hungary_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-413">From `Keywords_hungary_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-414">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-414">Keywords</span></span>

<span data-ttu-id="e8633-415">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-415">| |</span></span>
|<span data-ttu-id="e8633-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-417">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-417">dl#</span></span>  <br/> <span data-ttu-id="e8633-418">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-418">driver license</span></span>  <br/> <span data-ttu-id="e8633-419">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-419">driver license number</span></span>  <br/> <span data-ttu-id="e8633-420">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-420">driver licence</span></span>  <br/> <span data-ttu-id="e8633-421">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-421">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-422">drivers license</span></span>  <br/> <span data-ttu-id="e8633-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-423">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-424">driver's license</span></span>  <br/> <span data-ttu-id="e8633-425">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-425">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-426">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-426">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-427">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-427">driving license number</span></span>  <br/> <span data-ttu-id="e8633-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-428">dlno#</span></span>  <br/> <span data-ttu-id="e8633-429">vezetoi</span><span class="sxs-lookup"><span data-stu-id="e8633-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="e8633-430">아일랜드</span><span class="sxs-lookup"><span data-stu-id="e8633-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="e8633-431">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-431">Format</span></span>

<span data-ttu-id="e8633-432">6 자리 숫자와 4 개 문자</span><span class="sxs-lookup"><span data-stu-id="e8633-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-433">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-433">Pattern</span></span>

<span data-ttu-id="e8633-434">6 자리 숫자와 4 개 문자:</span><span class="sxs-lookup"><span data-stu-id="e8633-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="e8633-435">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-435">Six digits</span></span>
    
- <span data-ttu-id="e8633-436">4 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-437">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-437">Checksum</span></span>

<span data-ttu-id="e8633-438">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-439">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-439">Definition</span></span>

<span data-ttu-id="e8633-440">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-441">정규식이 해당 `Regex_ireland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-442">From `Keywords_ireland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-443">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-443">Keywords</span></span>

<span data-ttu-id="e8633-444">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-444">| |</span></span>
|<span data-ttu-id="e8633-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-446">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-446">dl#</span></span>  <br/> <span data-ttu-id="e8633-447">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-447">driver license</span></span>  <br/> <span data-ttu-id="e8633-448">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-448">driver license number</span></span>  <br/> <span data-ttu-id="e8633-449">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-449">driver licence</span></span>  <br/> <span data-ttu-id="e8633-450">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-450">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-451">drivers license</span></span>  <br/> <span data-ttu-id="e8633-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-452">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-453">driver's license</span></span>  <br/> <span data-ttu-id="e8633-454">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-454">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-455">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-455">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-456">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-456">driving license number</span></span>  <br/> <span data-ttu-id="e8633-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-457">dlno#</span></span>  <br/> <span data-ttu-id="e8633-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="e8633-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="e8633-459">이탈리아</span><span class="sxs-lookup"><span data-stu-id="e8633-459">Italy</span></span>

<span data-ttu-id="e8633-460">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"이탈리아 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8633-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="e8633-461">라트비아</span><span class="sxs-lookup"><span data-stu-id="e8633-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="e8633-462">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-462">Format</span></span>

<span data-ttu-id="e8633-463">3 개의 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-464">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-464">Pattern</span></span>

<span data-ttu-id="e8633-465">3 개의 문자 및 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="e8633-466">3 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e8633-467">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-468">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-468">Checksum</span></span>

<span data-ttu-id="e8633-469">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-470">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-470">Definition</span></span>

<span data-ttu-id="e8633-471">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-472">정규식이 해당 `Regex_latvia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-473">From `Keywords_latvia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-474">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-474">Keywords</span></span>

<span data-ttu-id="e8633-475">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-475">| |</span></span>
|<span data-ttu-id="e8633-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-477">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-477">dl#</span></span>  <br/> <span data-ttu-id="e8633-478">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-478">driver license</span></span>  <br/> <span data-ttu-id="e8633-479">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-479">driver license number</span></span>  <br/> <span data-ttu-id="e8633-480">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-480">driver licence</span></span>  <br/> <span data-ttu-id="e8633-481">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-481">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-482">drivers license</span></span>  <br/> <span data-ttu-id="e8633-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-483">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-484">driver's license</span></span>  <br/> <span data-ttu-id="e8633-485">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-485">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-486">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-486">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-487">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-487">driving license number</span></span>  <br/> <span data-ttu-id="e8633-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-488">dlno#</span></span>  <br/> <span data-ttu-id="e8633-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="e8633-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="e8633-490">리투아니아</span><span class="sxs-lookup"><span data-stu-id="e8633-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="e8633-491">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-491">Format</span></span>

<span data-ttu-id="e8633-492">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-493">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-493">Pattern</span></span>

 <span data-ttu-id="e8633-494">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e8633-495">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-495">Checksum</span></span>

<span data-ttu-id="e8633-496">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-497">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-497">Definition</span></span>

<span data-ttu-id="e8633-498">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-499">정규식이 해당 `Regex_lithuania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-500">From `Keywords_lithuania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-501">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-501">Keywords</span></span>

<span data-ttu-id="e8633-502">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-502">| |</span></span>
|<span data-ttu-id="e8633-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-504">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-504">dl#</span></span>  <br/> <span data-ttu-id="e8633-505">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-505">driver license</span></span>  <br/> <span data-ttu-id="e8633-506">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-506">driver license number</span></span>  <br/> <span data-ttu-id="e8633-507">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-507">driver licence</span></span>  <br/> <span data-ttu-id="e8633-508">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-508">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-509">drivers license</span></span>  <br/> <span data-ttu-id="e8633-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-510">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-511">driver's license</span></span>  <br/> <span data-ttu-id="e8633-512">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-512">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-513">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-513">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-514">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-514">driving license number</span></span>  <br/> <span data-ttu-id="e8633-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-515">dlno#</span></span>  <br/> <span data-ttu-id="e8633-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="e8633-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="e8633-517">셈</span><span class="sxs-lookup"><span data-stu-id="e8633-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="e8633-518">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-518">Format</span></span>

<span data-ttu-id="e8633-519">공백과 구분 기호가 없는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-520">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-520">Pattern</span></span>

 <span data-ttu-id="e8633-521">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="e8633-522">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-522">Checksum</span></span>

<span data-ttu-id="e8633-523">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-524">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-524">Definition</span></span>

<span data-ttu-id="e8633-525">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-526">정규식이 해당 `Regex_luxemburg_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-527">From `Keywords_luxemburg_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-528">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-528">Keywords</span></span>

<span data-ttu-id="e8633-529">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-529">| |</span></span>
|<span data-ttu-id="e8633-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-531">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-531">dl#</span></span>  <br/> <span data-ttu-id="e8633-532">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-532">driver license</span></span>  <br/> <span data-ttu-id="e8633-533">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-533">driver license number</span></span>  <br/> <span data-ttu-id="e8633-534">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-534">driver licence</span></span>  <br/> <span data-ttu-id="e8633-535">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-535">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-536">drivers license</span></span>  <br/> <span data-ttu-id="e8633-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-537">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-538">driver's license</span></span>  <br/> <span data-ttu-id="e8633-539">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-539">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-540">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-540">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-541">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-541">driving license number</span></span>  <br/> <span data-ttu-id="e8633-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-542">dlno#</span></span>  <br/> <span data-ttu-id="e8633-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="e8633-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="e8633-544">몰타</span><span class="sxs-lookup"><span data-stu-id="e8633-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="e8633-545">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-545">Format</span></span>

<span data-ttu-id="e8633-546">지정 된 패턴에서 두 개의 문자와 6 자리 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="e8633-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-547">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-547">Pattern</span></span>

<span data-ttu-id="e8633-548">두 문자와 6 자리 숫자의 조합:</span><span class="sxs-lookup"><span data-stu-id="e8633-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="e8633-549">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="e8633-550">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e8633-550">A space (optional)</span></span>
    
- <span data-ttu-id="e8633-551">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-551">Three digits</span></span>
    
- <span data-ttu-id="e8633-552">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="e8633-552">A space (optional)</span></span>
    
- <span data-ttu-id="e8633-553">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-554">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-554">Checksum</span></span>

<span data-ttu-id="e8633-555">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-556">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-556">Definition</span></span>

<span data-ttu-id="e8633-557">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-558">정규식이 해당 `Regex_malta_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-559">From `Keywords_malta_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-560">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-560">Keywords</span></span>

<span data-ttu-id="e8633-561">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-561">| |</span></span>
|<span data-ttu-id="e8633-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-563">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-563">dl#</span></span>  <br/> <span data-ttu-id="e8633-564">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-564">driver license</span></span>  <br/> <span data-ttu-id="e8633-565">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-565">driver license number</span></span>  <br/> <span data-ttu-id="e8633-566">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-566">driver licence</span></span>  <br/> <span data-ttu-id="e8633-567">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-567">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-568">drivers license</span></span>  <br/> <span data-ttu-id="e8633-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-569">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-570">driver's license</span></span>  <br/> <span data-ttu-id="e8633-571">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-571">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-572">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-572">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-573">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-573">driving license number</span></span>  <br/> <span data-ttu-id="e8633-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-574">dlno#</span></span>  <br/> <span data-ttu-id="e8633-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="e8633-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="e8633-576">네덜란드</span><span class="sxs-lookup"><span data-stu-id="e8633-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="e8633-577">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-577">Format</span></span>

<span data-ttu-id="e8633-578">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-579">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-579">Pattern</span></span>

<span data-ttu-id="e8633-580">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-581">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-581">Checksum</span></span>

<span data-ttu-id="e8633-582">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-583">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-583">Definition</span></span>

<span data-ttu-id="e8633-584">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-585">정규식이 해당 `Regex_netherlands_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-586">From `Keywords_netherlands_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-587">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-587">Keywords</span></span>

<span data-ttu-id="e8633-588">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-588">| |</span></span>
|<span data-ttu-id="e8633-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-590">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-590">dl#</span></span>  <br/> <span data-ttu-id="e8633-591">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-591">driver license</span></span>  <br/> <span data-ttu-id="e8633-592">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-592">driver license number</span></span>  <br/> <span data-ttu-id="e8633-593">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-593">driver licence</span></span>  <br/> <span data-ttu-id="e8633-594">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-594">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-595">drivers license</span></span>  <br/> <span data-ttu-id="e8633-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-596">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-597">driver's license</span></span>  <br/> <span data-ttu-id="e8633-598">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-598">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-599">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-599">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-600">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-600">driving license number</span></span>  <br/> <span data-ttu-id="e8633-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-601">dlno#</span></span>  <br/> <span data-ttu-id="e8633-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="e8633-602">permis de conduire</span></span>  <br/> <span data-ttu-id="e8633-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="e8633-603">rijbewijs</span></span>  <br/> <span data-ttu-id="e8633-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="e8633-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="e8633-605">폴란드</span><span class="sxs-lookup"><span data-stu-id="e8633-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="e8633-606">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-606">Format</span></span>

<span data-ttu-id="e8633-607">두 개의 슬래시를 포함 하는 14 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-608">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-608">Pattern</span></span>

<span data-ttu-id="e8633-609">14 자리 숫자와 2 개의 슬래시:</span><span class="sxs-lookup"><span data-stu-id="e8633-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="e8633-610">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-610">Five digits</span></span> 
    
- <span data-ttu-id="e8633-611">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="e8633-611">A forward slash</span></span>
    
- <span data-ttu-id="e8633-612">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-612">Two digits</span></span>
    
- <span data-ttu-id="e8633-613">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="e8633-613">A forward slash</span></span>
    
- <span data-ttu-id="e8633-614">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-615">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-615">Checksum</span></span>

<span data-ttu-id="e8633-616">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-617">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-617">Definition</span></span>

<span data-ttu-id="e8633-618">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-619">정규식이 해당 `Regex_poland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-620">From `Keywords_poland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-621">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-621">Keywords</span></span>

<span data-ttu-id="e8633-622">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-622">| |</span></span>
|<span data-ttu-id="e8633-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-624">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-624">dl#</span></span>  <br/> <span data-ttu-id="e8633-625">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-625">driver license</span></span>  <br/> <span data-ttu-id="e8633-626">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-626">driver license number</span></span>  <br/> <span data-ttu-id="e8633-627">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-627">driver licence</span></span>  <br/> <span data-ttu-id="e8633-628">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-628">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-629">drivers license</span></span>  <br/> <span data-ttu-id="e8633-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-630">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-631">driver's license</span></span>  <br/> <span data-ttu-id="e8633-632">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-632">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-633">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-633">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-634">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-634">driving license number</span></span>  <br/> <span data-ttu-id="e8633-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-635">dlno#</span></span>  <br/> <span data-ttu-id="e8633-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="e8633-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="e8633-637">포르투갈</span><span class="sxs-lookup"><span data-stu-id="e8633-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="e8633-638">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-638">Format</span></span>

<span data-ttu-id="e8633-639">두 개의 문자와 지정 된 패턴에 있는 일곱 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-640">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-640">Pattern</span></span>

<span data-ttu-id="e8633-641">두 문자 다음에 특수 문자를 사용한 7 개의 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="e8633-642">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="e8633-643">하이픈</span><span class="sxs-lookup"><span data-stu-id="e8633-643">A hyphen</span></span>
    
- <span data-ttu-id="e8633-644">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-644">Six digits</span></span>
    
- <span data-ttu-id="e8633-645">공백</span><span class="sxs-lookup"><span data-stu-id="e8633-645">A space</span></span>
    
- <span data-ttu-id="e8633-646">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-647">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-647">Checksum</span></span>

<span data-ttu-id="e8633-648">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-649">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-649">Definition</span></span>

<span data-ttu-id="e8633-650">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-651">정규식이 해당 `Regex_portugal_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-652">From `Keywords_portugal_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-653">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-653">Keywords</span></span>

<span data-ttu-id="e8633-654">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-654">| |</span></span>
|<span data-ttu-id="e8633-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-656">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-656">dl#</span></span>  <br/> <span data-ttu-id="e8633-657">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-657">driver license</span></span>  <br/> <span data-ttu-id="e8633-658">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-658">driver license number</span></span>  <br/> <span data-ttu-id="e8633-659">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-659">driver licence</span></span>  <br/> <span data-ttu-id="e8633-660">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-660">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-661">drivers license</span></span>  <br/> <span data-ttu-id="e8633-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-662">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-663">driver's license</span></span>  <br/> <span data-ttu-id="e8633-664">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-664">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-665">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-665">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-666">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-666">driving license number</span></span>  <br/> <span data-ttu-id="e8633-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-667">dlno#</span></span>  <br/> <span data-ttu-id="e8633-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="e8633-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="e8633-669">루마니아</span><span class="sxs-lookup"><span data-stu-id="e8633-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="e8633-670">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-670">Format</span></span>

<span data-ttu-id="e8633-671">한 문자 다음에 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-672">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-672">Pattern</span></span>

<span data-ttu-id="e8633-673">1 개의 문자 다음에 8 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="e8633-674">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="e8633-675">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-676">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-676">Checksum</span></span>

<span data-ttu-id="e8633-677">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-678">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-678">Definition</span></span>

<span data-ttu-id="e8633-679">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-680">정규식이 해당 `Regex_romania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-681">From `Keywords_romania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-682">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-682">Keywords</span></span>

<span data-ttu-id="e8633-683">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-683">| |</span></span>
|<span data-ttu-id="e8633-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-685">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-685">dl#</span></span>  <br/> <span data-ttu-id="e8633-686">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-686">driver license</span></span>  <br/> <span data-ttu-id="e8633-687">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-687">driver license number</span></span>  <br/> <span data-ttu-id="e8633-688">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-688">driver licence</span></span>  <br/> <span data-ttu-id="e8633-689">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-689">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-690">drivers license</span></span>  <br/> <span data-ttu-id="e8633-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-691">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-692">driver's license</span></span>  <br/> <span data-ttu-id="e8633-693">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-693">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-694">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-694">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-695">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-695">driving license number</span></span>  <br/> <span data-ttu-id="e8633-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-696">dlno#</span></span>  <br/> <span data-ttu-id="e8633-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="e8633-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="e8633-698">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="e8633-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="e8633-699">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-699">Format</span></span>

<span data-ttu-id="e8633-700">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-701">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-701">Pattern</span></span>

<span data-ttu-id="e8633-702">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="e8633-703">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="e8633-704">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="e8633-705">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-705">Checksum</span></span>

<span data-ttu-id="e8633-706">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-707">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-707">Definition</span></span>

<span data-ttu-id="e8633-708">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-709">정규식이 해당 `Regex_slovakia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-710">From `Keywords_slovakia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-711">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-711">Keywords</span></span>

<span data-ttu-id="e8633-712">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-712">| |</span></span>
|<span data-ttu-id="e8633-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-714">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-714">dl#</span></span>  <br/> <span data-ttu-id="e8633-715">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-715">driver license</span></span>  <br/> <span data-ttu-id="e8633-716">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-716">driver license number</span></span>  <br/> <span data-ttu-id="e8633-717">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-717">driver licence</span></span>  <br/> <span data-ttu-id="e8633-718">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-718">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-719">drivers license</span></span>  <br/> <span data-ttu-id="e8633-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-720">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-721">driver's license</span></span>  <br/> <span data-ttu-id="e8633-722">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-722">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-723">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-723">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-724">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-724">driving license number</span></span>  <br/> <span data-ttu-id="e8633-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-725">dlno#</span></span>  <br/> <span data-ttu-id="e8633-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="e8633-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="e8633-727">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="e8633-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="e8633-728">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-728">Format</span></span>

<span data-ttu-id="e8633-729">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-730">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-730">Pattern</span></span>

<span data-ttu-id="e8633-731">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="e8633-732">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-732">Checksum</span></span>

<span data-ttu-id="e8633-733">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-734">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-734">Definition</span></span>

<span data-ttu-id="e8633-735">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-736">정규식이 해당 `Regex_slovenia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-737">From `Keywords_slovenia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-738">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-738">Keywords</span></span>

<span data-ttu-id="e8633-739">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-739">| |</span></span>
|<span data-ttu-id="e8633-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-741">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-741">dl#</span></span>  <br/> <span data-ttu-id="e8633-742">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-742">driver license</span></span>  <br/> <span data-ttu-id="e8633-743">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-743">driver license number</span></span>  <br/> <span data-ttu-id="e8633-744">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-744">driver licence</span></span>  <br/> <span data-ttu-id="e8633-745">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-745">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-746">drivers license</span></span>  <br/> <span data-ttu-id="e8633-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-747">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-748">driver's license</span></span>  <br/> <span data-ttu-id="e8633-749">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-749">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-750">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-750">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-751">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-751">driving license number</span></span>  <br/> <span data-ttu-id="e8633-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-752">dlno#</span></span>  <br/> <span data-ttu-id="e8633-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="e8633-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="e8633-754">스페인</span><span class="sxs-lookup"><span data-stu-id="e8633-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="e8633-755">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-755">Format</span></span>

<span data-ttu-id="e8633-756">8 자리 숫자와 문자 1 개</span><span class="sxs-lookup"><span data-stu-id="e8633-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-757">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-757">Pattern</span></span>

<span data-ttu-id="e8633-758">8 자리 숫자와 문자 1 개:</span><span class="sxs-lookup"><span data-stu-id="e8633-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="e8633-759">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-759">Eight digits</span></span> 
    
- <span data-ttu-id="e8633-760">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="e8633-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-761">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-761">Checksum</span></span>

<span data-ttu-id="e8633-762">예</span><span class="sxs-lookup"><span data-stu-id="e8633-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-763">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-763">Definition</span></span>

<span data-ttu-id="e8633-764">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-765">이 함수 `Func_spain_eu_driver's_license_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-766">From `Keywords_spain_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="e8633-767">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-767">Keywords</span></span>

<span data-ttu-id="e8633-768">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-768">| |</span></span>
|<span data-ttu-id="e8633-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-770">dlno#</span></span>  <br/> <span data-ttu-id="e8633-771">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-771">dl#</span></span>  <br/> <span data-ttu-id="e8633-772">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-772">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-773">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-773">driver licence</span></span>  <br/> <span data-ttu-id="e8633-774">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-774">driver license</span></span>  <br/> <span data-ttu-id="e8633-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-775">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-776">drivers license</span></span>  <br/> <span data-ttu-id="e8633-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="e8633-777">driver's licence</span></span>  <br/> <span data-ttu-id="e8633-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-778">driver's license</span></span>  <br/> <span data-ttu-id="e8633-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="e8633-779">driving licence</span></span>  <br/> <span data-ttu-id="e8633-780">driving license</span><span class="sxs-lookup"><span data-stu-id="e8633-780">driving license</span></span>  <br/> <span data-ttu-id="e8633-781">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-781">driver licence number</span></span>  <br/> <span data-ttu-id="e8633-782">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-782">driver license number</span></span>  <br/> <span data-ttu-id="e8633-783">영향 요소 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-783">drivers licence number</span></span>  <br/> <span data-ttu-id="e8633-784">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-784">drivers license number</span></span>  <br/> <span data-ttu-id="e8633-785">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-785">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-786">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-786">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-787">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-787">driving licence number</span></span>  <br/> <span data-ttu-id="e8633-788">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-788">driving license number</span></span>  <br/> <span data-ttu-id="e8633-789">추진 허용</span><span class="sxs-lookup"><span data-stu-id="e8633-789">driving permit</span></span>  <br/> <span data-ttu-id="e8633-790">제어 허용 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-790">driving permit number</span></span>  <br/> <span data-ttu-id="e8633-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="e8633-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="e8633-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="e8633-792">permiso conducción</span></span>  <br/> <span data-ttu-id="e8633-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="e8633-794">número de 네트워크 de conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="e8633-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="e8633-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-796">licencia conducir</span></span>  <br/> <span data-ttu-id="e8633-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="e8633-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="e8633-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="e8633-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-800">permiso conducir</span></span>  <br/> <span data-ttu-id="e8633-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="e8633-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="e8633-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="e8633-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="e8633-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="e8633-804">스웨덴</span><span class="sxs-lookup"><span data-stu-id="e8633-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="e8633-805">형식일</span><span class="sxs-lookup"><span data-stu-id="e8633-805">Format</span></span>

<span data-ttu-id="e8633-806">하이픈을 포함 하는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="e8633-807">패턴</span><span class="sxs-lookup"><span data-stu-id="e8633-807">Pattern</span></span>

<span data-ttu-id="e8633-808">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="e8633-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="e8633-809">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-809">Six digits</span></span> 
    
- <span data-ttu-id="e8633-810">하이픈</span><span class="sxs-lookup"><span data-stu-id="e8633-810">A hyphen</span></span>
    
- <span data-ttu-id="e8633-811">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="e8633-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="e8633-812">제외</span><span class="sxs-lookup"><span data-stu-id="e8633-812">Checksum</span></span>

<span data-ttu-id="e8633-813">아니요</span><span class="sxs-lookup"><span data-stu-id="e8633-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="e8633-814">정의</span><span class="sxs-lookup"><span data-stu-id="e8633-814">Definition</span></span>

<span data-ttu-id="e8633-815">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="e8633-816">정규식이 해당 `Regex_sweden_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="e8633-817">From `Keywords_sweden_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="e8633-818">키워드</span><span class="sxs-lookup"><span data-stu-id="e8633-818">Keywords</span></span>

<span data-ttu-id="e8633-819">| |</span><span class="sxs-lookup"><span data-stu-id="e8633-819">| |</span></span>
|<span data-ttu-id="e8633-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="e8633-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="e8633-821">dl #</span><span class="sxs-lookup"><span data-stu-id="e8633-821">dl#</span></span>  <br/> <span data-ttu-id="e8633-822">driver license</span><span class="sxs-lookup"><span data-stu-id="e8633-822">driver license</span></span>  <br/> <span data-ttu-id="e8633-823">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-823">driver license number</span></span>  <br/> <span data-ttu-id="e8633-824">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="e8633-824">driver licence</span></span>  <br/> <span data-ttu-id="e8633-825">drivers lic</span><span class="sxs-lookup"><span data-stu-id="e8633-825">drivers lic.</span></span>  <br/> <span data-ttu-id="e8633-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="e8633-826">drivers license</span></span>  <br/> <span data-ttu-id="e8633-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="e8633-827">drivers licence</span></span>  <br/> <span data-ttu-id="e8633-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="e8633-828">driver's license</span></span>  <br/> <span data-ttu-id="e8633-829">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-829">driver's license number</span></span>  <br/> <span data-ttu-id="e8633-830">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-830">driver's licence number</span></span>  <br/> <span data-ttu-id="e8633-831">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="e8633-831">driving license number</span></span>  <br/> <span data-ttu-id="e8633-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="e8633-832">dlno#</span></span>  <br/> <span data-ttu-id="e8633-833">körkort</span><span class="sxs-lookup"><span data-stu-id="e8633-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="e8633-834">영국의</span><span class="sxs-lookup"><span data-stu-id="e8633-834">UK</span></span>

<span data-ttu-id="e8633-835">자세한 내용은 영국 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="e8633-835">For details, see the section "U.K.</span></span> <span data-ttu-id="e8633-836">[중요 한 정보 유형에 서 확인 되는](what-the-sensitive-information-types-look-for.md)운전 면허 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="e8633-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="e8633-837">참고 항목</span><span class="sxs-lookup"><span data-stu-id="e8633-837">See also</span></span>

[<span data-ttu-id="e8633-838">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="e8633-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

