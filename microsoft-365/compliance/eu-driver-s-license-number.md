---
title: EU 운전 면허 번호
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: f1a95ecbaf6b6d1ac189290dd6d076cfd91ab30f
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088084"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="85d97-104">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-104">EU Driver's License Number</span></span>

<span data-ttu-id="85d97-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="85d97-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="85d97-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="85d97-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="85d97-108">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-108">Format</span></span>

<span data-ttu-id="85d97-109">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-110">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-110">Pattern</span></span>

<span data-ttu-id="85d97-111">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-112">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-112">Checksum</span></span>

<span data-ttu-id="85d97-113">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-114">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-114">Definition</span></span>

<span data-ttu-id="85d97-115">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-116">정규식이 해당 `Regex_austria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-117">From `Keywords_austria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="85d97-118">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-118">Keywords</span></span>

<span data-ttu-id="85d97-119">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-119"></span></span>
|<span data-ttu-id="85d97-120">**Keywords_austria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-121">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-121">dl#</span></span>  <br/> <span data-ttu-id="85d97-122">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-122">driver license</span></span>  <br/> <span data-ttu-id="85d97-123">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-123">driver license number</span></span>  <br/> <span data-ttu-id="85d97-124">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-124">driver licence</span></span>  <br/> <span data-ttu-id="85d97-125">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-125">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-126">drivers license</span></span>  <br/> <span data-ttu-id="85d97-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="85d97-127">driver's licence</span></span>  <br/> <span data-ttu-id="85d97-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-128">driver's license</span></span>  <br/> <span data-ttu-id="85d97-129">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-129">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-130">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="85d97-131">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-131">driving license number</span></span>  <br/> <span data-ttu-id="85d97-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-132">dlno#</span></span>  <br/> <span data-ttu-id="85d97-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="85d97-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="85d97-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="85d97-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="85d97-135">벨기에</span><span class="sxs-lookup"><span data-stu-id="85d97-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="85d97-136">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-136">Format</span></span>

<span data-ttu-id="85d97-137">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-138">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-138">Pattern</span></span>

<span data-ttu-id="85d97-139">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-140">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-140">Checksum</span></span>

<span data-ttu-id="85d97-141">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-142">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-142">Definition</span></span>

<span data-ttu-id="85d97-143">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-144">정규식이 해당 `Regex_belgium_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-145">From `Keywords_belgium_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="85d97-146">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-146">Keywords</span></span>

<span data-ttu-id="85d97-147">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-147"></span></span>
|<span data-ttu-id="85d97-148">**Keywords__belgium_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-149">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-149">dl#</span></span>  <br/> <span data-ttu-id="85d97-150">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-150">driver license</span></span>  <br/> <span data-ttu-id="85d97-151">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-151">driver license number</span></span>  <br/> <span data-ttu-id="85d97-152">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-152">driver licence</span></span>  <br/> <span data-ttu-id="85d97-153">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-153">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-154">drivers license</span></span>  <br/> <span data-ttu-id="85d97-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-155">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-156">driver's license</span></span>  <br/> <span data-ttu-id="85d97-157">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-157">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-158">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-158">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-159">dlno#</span></span>  <br/> <span data-ttu-id="85d97-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="85d97-160">rijbewijs</span></span>  <br/> <span data-ttu-id="85d97-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="85d97-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="85d97-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="85d97-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="85d97-165">führerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="85d97-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="85d97-166">fuehrerschein-Veiligheid</span><span class="sxs-lookup"><span data-stu-id="85d97-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="85d97-167">fuehrerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="85d97-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="85d97-168">불가리아</span><span class="sxs-lookup"><span data-stu-id="85d97-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="85d97-169">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-169">Format</span></span>

<span data-ttu-id="85d97-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-171">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-171">Pattern</span></span>

<span data-ttu-id="85d97-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-173">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-173">Checksum</span></span>

<span data-ttu-id="85d97-174">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-175">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-175">Definition</span></span>

<span data-ttu-id="85d97-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-177">정규식이 해당 `Regex_bulgaria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-178">From `Keywords_bulgaria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="85d97-179">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-179">Keywords</span></span>

<span data-ttu-id="85d97-180">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-180"></span></span>
|<span data-ttu-id="85d97-181">**Keywords_bulgaria_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-182">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-182">dl#</span></span>  <br/> <span data-ttu-id="85d97-183">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-183">driver license</span></span>  <br/> <span data-ttu-id="85d97-184">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-184">driver license number</span></span>  <br/> <span data-ttu-id="85d97-185">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-185">driver licence</span></span>  <br/> <span data-ttu-id="85d97-186">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-186">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-187">drivers license</span></span>  <br/> <span data-ttu-id="85d97-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-188">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-189">driver's license</span></span>  <br/> <span data-ttu-id="85d97-190">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-190">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-191">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-191">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-192">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-192">driving license number</span></span>  <br/> <span data-ttu-id="85d97-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-193">dlno#</span></span>  <br/> <span data-ttu-id="85d97-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="85d97-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="85d97-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="85d97-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="85d97-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="85d97-196">сумпс</span></span>  <br/> <span data-ttu-id="85d97-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="85d97-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="85d97-198">크로아티아</span><span class="sxs-lookup"><span data-stu-id="85d97-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="85d97-199">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-199">Format</span></span>

<span data-ttu-id="85d97-200">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-201">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-201">Pattern</span></span>

<span data-ttu-id="85d97-202">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-203">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-203">Checksum</span></span>

<span data-ttu-id="85d97-204">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-205">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-205">Definition</span></span>

<span data-ttu-id="85d97-206">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-207">정규식이 해당 `Regex_croatia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-208">From `Keywords_croatia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="85d97-209">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-209">Keywords</span></span>

<span data-ttu-id="85d97-210">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-210"></span></span>
|<span data-ttu-id="85d97-211">**Keywords_croatia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-212">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-212">dl#</span></span>  <br/> <span data-ttu-id="85d97-213">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-213">driver license</span></span>  <br/> <span data-ttu-id="85d97-214">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-214">driver license number</span></span>  <br/> <span data-ttu-id="85d97-215">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-215">driver licence</span></span>  <br/> <span data-ttu-id="85d97-216">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-216">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-217">drivers license</span></span>  <br/> <span data-ttu-id="85d97-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-218">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-219">driver's license</span></span>  <br/> <span data-ttu-id="85d97-220">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-220">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-221">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-221">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-222">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-222">driving license number</span></span>  <br/> <span data-ttu-id="85d97-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-223">dlno#</span></span>  <br/> <span data-ttu-id="85d97-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="85d97-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="85d97-225">키프로스</span><span class="sxs-lookup"><span data-stu-id="85d97-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="85d97-226">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-226">Format</span></span>

<span data-ttu-id="85d97-227">공백과 구분 기호를 사용 하지 않고 12 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-228">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-228">Pattern</span></span>

<span data-ttu-id="85d97-229">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-230">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-230">Checksum</span></span>

<span data-ttu-id="85d97-231">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-232">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-232">Definition</span></span>

<span data-ttu-id="85d97-233">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-234">정규식이 해당 `Regex_cyprus_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-235">From `Keywords_cyprus_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-236">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-236">Keywords</span></span>

<span data-ttu-id="85d97-237">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-237"></span></span>
|<span data-ttu-id="85d97-238">**Keywords_cyprus_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-239">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-239">dl#</span></span>  <br/> <span data-ttu-id="85d97-240">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-240">driver license</span></span>  <br/> <span data-ttu-id="85d97-241">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-241">driver license number</span></span>  <br/> <span data-ttu-id="85d97-242">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-242">driver licence</span></span>  <br/> <span data-ttu-id="85d97-243">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-243">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-244">drivers license</span></span>  <br/> <span data-ttu-id="85d97-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-245">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-246">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-246">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-247">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-247">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-248">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-248">driving license number</span></span>  <br/> <span data-ttu-id="85d97-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-249">dlno#</span></span>  <br/> <span data-ttu-id="85d97-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="85d97-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="85d97-251">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="85d97-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="85d97-252">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-252">Format</span></span>

<span data-ttu-id="85d97-253">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-254">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-254">Pattern</span></span>

<span data-ttu-id="85d97-255">8 개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="85d97-256">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="85d97-257">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85d97-257">A space (optional)</span></span>
    
- <span data-ttu-id="85d97-258">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-259">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-259">Checksum</span></span>

<span data-ttu-id="85d97-260">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-261">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-261">Definition</span></span>

<span data-ttu-id="85d97-262">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-263">정규식이 해당 `Regex_czech_republic_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-264">From `Keywords_czech_republic_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="85d97-265">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-265">Keywords</span></span>

<span data-ttu-id="85d97-266">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-266"></span></span>
|<span data-ttu-id="85d97-267">**Keywords_czech_republic_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-268">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-268">dl#</span></span>  <br/> <span data-ttu-id="85d97-269">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-269">driver license</span></span>  <br/> <span data-ttu-id="85d97-270">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-270">driver license number</span></span>  <br/> <span data-ttu-id="85d97-271">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-271">driver licence</span></span>  <br/> <span data-ttu-id="85d97-272">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-272">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-273">drivers license</span></span>  <br/> <span data-ttu-id="85d97-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-274">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-275">driver's license</span></span>  <br/> <span data-ttu-id="85d97-276">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-276">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-277">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-277">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-278">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-278">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-279">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-279">driving license number</span></span>  <br/> <span data-ttu-id="85d97-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-280">dlno#</span></span>  <br/> <span data-ttu-id="85d97-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="85d97-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="85d97-282">덴마크</span><span class="sxs-lookup"><span data-stu-id="85d97-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="85d97-283">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-283">Format</span></span>

<span data-ttu-id="85d97-284">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-285">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-285">Pattern</span></span>

<span data-ttu-id="85d97-286">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-287">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-287">Checksum</span></span>

<span data-ttu-id="85d97-288">예</span><span class="sxs-lookup"><span data-stu-id="85d97-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-289">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-289">Definition</span></span>

<span data-ttu-id="85d97-290">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-291">정규식이 해당 `Regex_denmark_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-292">From `Keywords_denmark_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="85d97-293">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-293">Keywords</span></span>

<span data-ttu-id="85d97-294">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-294"></span></span>
|<span data-ttu-id="85d97-295">**Keywords_denmark_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-296">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-296">dl#</span></span>  <br/> <span data-ttu-id="85d97-297">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-297">driver license</span></span>  <br/> <span data-ttu-id="85d97-298">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-298">driver license number</span></span>  <br/> <span data-ttu-id="85d97-299">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-299">driver licence</span></span>  <br/> <span data-ttu-id="85d97-300">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-300">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-301">drivers license</span></span>  <br/> <span data-ttu-id="85d97-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-302">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-303">driver's license</span></span>  <br/> <span data-ttu-id="85d97-304">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-304">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-305">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-305">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-306">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-306">driving license number</span></span>  <br/> <span data-ttu-id="85d97-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-307">dlno#</span></span>  <br/> <span data-ttu-id="85d97-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="85d97-308">kørekort</span></span>  <br/> <span data-ttu-id="85d97-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="85d97-310">에스토니아</span><span class="sxs-lookup"><span data-stu-id="85d97-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="85d97-311">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-311">Format</span></span>

<span data-ttu-id="85d97-312">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-313">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-313">Pattern</span></span>

<span data-ttu-id="85d97-314">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="85d97-315">문자 "ET" (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="85d97-316">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-317">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-317">Checksum</span></span>

<span data-ttu-id="85d97-318">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-319">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-319">Definition</span></span>

<span data-ttu-id="85d97-320">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-321">정규식이 해당 `Regex_estonia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-322">From `Keywords_estonia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-323">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-323">Keywords</span></span>

<span data-ttu-id="85d97-324">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-324"></span></span>
|<span data-ttu-id="85d97-325">**Keywords_estonia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-326">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-326">dl#</span></span>  <br/> <span data-ttu-id="85d97-327">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-327">driver license</span></span>  <br/> <span data-ttu-id="85d97-328">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-328">driver license number</span></span>  <br/> <span data-ttu-id="85d97-329">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-329">driver license number</span></span>  <br/> <span data-ttu-id="85d97-330">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-330">driver licence</span></span>  <br/> <span data-ttu-id="85d97-331">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-331">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-332">drivers license</span></span>  <br/> <span data-ttu-id="85d97-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-333">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-334">driver's license</span></span>  <br/> <span data-ttu-id="85d97-335">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-335">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-336">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-336">driving license number</span></span>  <br/> <span data-ttu-id="85d97-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-337">dlno#</span></span>  <br/> <span data-ttu-id="85d97-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="85d97-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="85d97-339">핀란드</span><span class="sxs-lookup"><span data-stu-id="85d97-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="85d97-340">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-340">Format</span></span>

<span data-ttu-id="85d97-341">하이픈을 포함하는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-342">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-342">Pattern</span></span>

<span data-ttu-id="85d97-343">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="85d97-344">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-344">Six digits</span></span> 
    
- <span data-ttu-id="85d97-345">하이픈</span><span class="sxs-lookup"><span data-stu-id="85d97-345">A hyphen</span></span>
    
-  <span data-ttu-id="85d97-346">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="85d97-347">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-347">Checksum</span></span>

<span data-ttu-id="85d97-348">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-349">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-349">Definition</span></span>

<span data-ttu-id="85d97-350">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-351">정규식이 해당 `Regex_finland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-352">From `Keywords_finland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-353">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-353">Keywords</span></span>

<span data-ttu-id="85d97-354">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-354"></span></span>
|<span data-ttu-id="85d97-355">**Keywords_finland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-356">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-356">dl#</span></span>  <br/> <span data-ttu-id="85d97-357">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-357">driver license</span></span>  <br/> <span data-ttu-id="85d97-358">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-358">driver license number</span></span>  <br/> <span data-ttu-id="85d97-359">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-359">driver licence</span></span>  <br/> <span data-ttu-id="85d97-360">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-360">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-361">drivers license</span></span>  <br/> <span data-ttu-id="85d97-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-362">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-363">driver's license</span></span>  <br/> <span data-ttu-id="85d97-364">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-364">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-365">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-365">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-366">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-366">driving license number</span></span>  <br/> <span data-ttu-id="85d97-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-367">dlno#</span></span>  <br/> <span data-ttu-id="85d97-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="85d97-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="85d97-369">프랑스</span><span class="sxs-lookup"><span data-stu-id="85d97-369">France</span></span>

<span data-ttu-id="85d97-370">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"경기도 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85d97-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="85d97-371">독일</span><span class="sxs-lookup"><span data-stu-id="85d97-371">Germany</span></span>

<span data-ttu-id="85d97-372">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일어 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85d97-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="85d97-373">그리스</span><span class="sxs-lookup"><span data-stu-id="85d97-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="85d97-374">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-374">Format</span></span>

<span data-ttu-id="85d97-375">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-376">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-376">Pattern</span></span>

 <span data-ttu-id="85d97-377">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85d97-378">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-378">Checksum</span></span>

<span data-ttu-id="85d97-379">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-380">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-380">Definition</span></span>

<span data-ttu-id="85d97-381">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-382">정규식이 해당 `Regex_greece_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-383">From `Keywords_greece_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-384">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-384">Keywords</span></span>

<span data-ttu-id="85d97-385">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-385"></span></span>
|<span data-ttu-id="85d97-386">**Keywords_greece_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="85d97-387">dlL#</span></span>  <br/> <span data-ttu-id="85d97-388">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-388">driver license</span></span>  <br/> <span data-ttu-id="85d97-389">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-389">driver license number</span></span>  <br/> <span data-ttu-id="85d97-390">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-390">driver licence</span></span>  <br/> <span data-ttu-id="85d97-391">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-391">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-392">drivers license</span></span>  <br/> <span data-ttu-id="85d97-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-393">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-394">driver's license</span></span>  <br/> <span data-ttu-id="85d97-395">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-395">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-396">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-396">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-397">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-397">driving license number</span></span>  <br/> <span data-ttu-id="85d97-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-398">dlno#</span></span>  <br/> <span data-ttu-id="85d97-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="85d97-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="85d97-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="85d97-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="85d97-401">헝가리</span><span class="sxs-lookup"><span data-stu-id="85d97-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="85d97-402">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-402">Format</span></span>

<span data-ttu-id="85d97-403">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-404">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-404">Pattern</span></span>

<span data-ttu-id="85d97-405">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="85d97-406">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="85d97-407">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-408">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-408">Checksum</span></span>

<span data-ttu-id="85d97-409">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-410">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-410">Definition</span></span>

<span data-ttu-id="85d97-411">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-412">정규식이 해당 `Regex_hungary_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-413">From `Keywords_hungary_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-414">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-414">Keywords</span></span>

<span data-ttu-id="85d97-415">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-415"></span></span>
|<span data-ttu-id="85d97-416">**Keywords_hungary_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-417">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-417">dl#</span></span>  <br/> <span data-ttu-id="85d97-418">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-418">driver license</span></span>  <br/> <span data-ttu-id="85d97-419">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-419">driver license number</span></span>  <br/> <span data-ttu-id="85d97-420">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-420">driver licence</span></span>  <br/> <span data-ttu-id="85d97-421">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-421">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-422">drivers license</span></span>  <br/> <span data-ttu-id="85d97-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-423">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-424">driver's license</span></span>  <br/> <span data-ttu-id="85d97-425">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-425">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-426">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-426">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-427">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-427">driving license number</span></span>  <br/> <span data-ttu-id="85d97-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-428">dlno#</span></span>  <br/> <span data-ttu-id="85d97-429">vezetoi</span><span class="sxs-lookup"><span data-stu-id="85d97-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="85d97-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="85d97-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="85d97-431">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-431">Format</span></span>

<span data-ttu-id="85d97-432">6 자리 숫자와 4 개 문자</span><span class="sxs-lookup"><span data-stu-id="85d97-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-433">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-433">Pattern</span></span>

<span data-ttu-id="85d97-434">6 자리 숫자와 4 개 문자:</span><span class="sxs-lookup"><span data-stu-id="85d97-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="85d97-435">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-435">Six digits</span></span>
    
- <span data-ttu-id="85d97-436">4 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-437">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-437">Checksum</span></span>

<span data-ttu-id="85d97-438">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-439">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-439">Definition</span></span>

<span data-ttu-id="85d97-440">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-441">정규식이 해당 `Regex_ireland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-442">From `Keywords_ireland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-443">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-443">Keywords</span></span>

<span data-ttu-id="85d97-444">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-444"></span></span>
|<span data-ttu-id="85d97-445">**Keywords_ireland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-446">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-446">dl#</span></span>  <br/> <span data-ttu-id="85d97-447">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-447">driver license</span></span>  <br/> <span data-ttu-id="85d97-448">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-448">driver license number</span></span>  <br/> <span data-ttu-id="85d97-449">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-449">driver licence</span></span>  <br/> <span data-ttu-id="85d97-450">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-450">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-451">drivers license</span></span>  <br/> <span data-ttu-id="85d97-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-452">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-453">driver's license</span></span>  <br/> <span data-ttu-id="85d97-454">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-454">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-455">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-455">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-456">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-456">driving license number</span></span>  <br/> <span data-ttu-id="85d97-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-457">dlno#</span></span>  <br/> <span data-ttu-id="85d97-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="85d97-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="85d97-459">이탈리아</span><span class="sxs-lookup"><span data-stu-id="85d97-459">Italy</span></span>

<span data-ttu-id="85d97-460">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"이탈리아 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85d97-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="85d97-461">라트비아</span><span class="sxs-lookup"><span data-stu-id="85d97-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="85d97-462">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-462">Format</span></span>

<span data-ttu-id="85d97-463">3 개의 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-464">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-464">Pattern</span></span>

<span data-ttu-id="85d97-465">3 개의 문자 및 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="85d97-466">3 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="85d97-467">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-468">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-468">Checksum</span></span>

<span data-ttu-id="85d97-469">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-470">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-470">Definition</span></span>

<span data-ttu-id="85d97-471">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-472">정규식이 해당 `Regex_latvia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-473">From `Keywords_latvia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-474">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-474">Keywords</span></span>

<span data-ttu-id="85d97-475">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-475"></span></span>
|<span data-ttu-id="85d97-476">**Keywords_latvia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-477">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-477">dl#</span></span>  <br/> <span data-ttu-id="85d97-478">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-478">driver license</span></span>  <br/> <span data-ttu-id="85d97-479">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-479">driver license number</span></span>  <br/> <span data-ttu-id="85d97-480">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-480">driver licence</span></span>  <br/> <span data-ttu-id="85d97-481">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-481">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-482">drivers license</span></span>  <br/> <span data-ttu-id="85d97-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-483">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-484">driver's license</span></span>  <br/> <span data-ttu-id="85d97-485">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-485">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-486">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-486">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-487">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-487">driving license number</span></span>  <br/> <span data-ttu-id="85d97-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-488">dlno#</span></span>  <br/> <span data-ttu-id="85d97-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="85d97-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="85d97-490">리투아니아</span><span class="sxs-lookup"><span data-stu-id="85d97-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="85d97-491">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-491">Format</span></span>

<span data-ttu-id="85d97-492">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-493">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-493">Pattern</span></span>

 <span data-ttu-id="85d97-494">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85d97-495">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-495">Checksum</span></span>

<span data-ttu-id="85d97-496">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-497">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-497">Definition</span></span>

<span data-ttu-id="85d97-498">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-499">정규식이 해당 `Regex_lithuania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-500">From `Keywords_lithuania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-501">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-501">Keywords</span></span>

<span data-ttu-id="85d97-502">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-502"></span></span>
|<span data-ttu-id="85d97-503">**Keywords_lithuania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-504">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-504">dl#</span></span>  <br/> <span data-ttu-id="85d97-505">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-505">driver license</span></span>  <br/> <span data-ttu-id="85d97-506">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-506">driver license number</span></span>  <br/> <span data-ttu-id="85d97-507">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-507">driver licence</span></span>  <br/> <span data-ttu-id="85d97-508">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-508">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-509">drivers license</span></span>  <br/> <span data-ttu-id="85d97-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-510">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-511">driver's license</span></span>  <br/> <span data-ttu-id="85d97-512">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-512">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-513">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-513">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-514">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-514">driving license number</span></span>  <br/> <span data-ttu-id="85d97-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-515">dlno#</span></span>  <br/> <span data-ttu-id="85d97-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="85d97-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="85d97-517">셈</span><span class="sxs-lookup"><span data-stu-id="85d97-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="85d97-518">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-518">Format</span></span>

<span data-ttu-id="85d97-519">공백과 구분 기호가 없는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-520">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-520">Pattern</span></span>

 <span data-ttu-id="85d97-521">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="85d97-522">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-522">Checksum</span></span>

<span data-ttu-id="85d97-523">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-524">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-524">Definition</span></span>

<span data-ttu-id="85d97-525">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-526">정규식이 해당 `Regex_luxemburg_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-527">From `Keywords_luxemburg_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-528">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-528">Keywords</span></span>

<span data-ttu-id="85d97-529">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-529"></span></span>
|<span data-ttu-id="85d97-530">**Keywords_luxemburg_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-531">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-531">dl#</span></span>  <br/> <span data-ttu-id="85d97-532">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-532">driver license</span></span>  <br/> <span data-ttu-id="85d97-533">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-533">driver license number</span></span>  <br/> <span data-ttu-id="85d97-534">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-534">driver licence</span></span>  <br/> <span data-ttu-id="85d97-535">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-535">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-536">drivers license</span></span>  <br/> <span data-ttu-id="85d97-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-537">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-538">driver's license</span></span>  <br/> <span data-ttu-id="85d97-539">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-539">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-540">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-540">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-541">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-541">driving license number</span></span>  <br/> <span data-ttu-id="85d97-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-542">dlno#</span></span>  <br/> <span data-ttu-id="85d97-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="85d97-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="85d97-544">몰타</span><span class="sxs-lookup"><span data-stu-id="85d97-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="85d97-545">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-545">Format</span></span>

<span data-ttu-id="85d97-546">지정 된 패턴에서 두 개의 문자와 6 자리 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="85d97-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-547">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-547">Pattern</span></span>

<span data-ttu-id="85d97-548">두 문자와 6 자리 숫자의 조합:</span><span class="sxs-lookup"><span data-stu-id="85d97-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="85d97-549">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="85d97-550">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85d97-550">A space (optional)</span></span>
    
- <span data-ttu-id="85d97-551">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-551">Three digits</span></span>
    
- <span data-ttu-id="85d97-552">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="85d97-552">A space (optional)</span></span>
    
- <span data-ttu-id="85d97-553">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-554">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-554">Checksum</span></span>

<span data-ttu-id="85d97-555">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-556">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-556">Definition</span></span>

<span data-ttu-id="85d97-557">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-558">정규식이 해당 `Regex_malta_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-559">From `Keywords_malta_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-560">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-560">Keywords</span></span>

<span data-ttu-id="85d97-561">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-561"></span></span>
|<span data-ttu-id="85d97-562">**Keywords_malta_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-563">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-563">dl#</span></span>  <br/> <span data-ttu-id="85d97-564">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-564">driver license</span></span>  <br/> <span data-ttu-id="85d97-565">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-565">driver license number</span></span>  <br/> <span data-ttu-id="85d97-566">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-566">driver licence</span></span>  <br/> <span data-ttu-id="85d97-567">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-567">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-568">drivers license</span></span>  <br/> <span data-ttu-id="85d97-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-569">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-570">driver's license</span></span>  <br/> <span data-ttu-id="85d97-571">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-571">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-572">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-572">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-573">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-573">driving license number</span></span>  <br/> <span data-ttu-id="85d97-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-574">dlno#</span></span>  <br/> <span data-ttu-id="85d97-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="85d97-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="85d97-576">네덜란드</span><span class="sxs-lookup"><span data-stu-id="85d97-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="85d97-577">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-577">Format</span></span>

<span data-ttu-id="85d97-578">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-579">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-579">Pattern</span></span>

<span data-ttu-id="85d97-580">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-581">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-581">Checksum</span></span>

<span data-ttu-id="85d97-582">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-583">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-583">Definition</span></span>

<span data-ttu-id="85d97-584">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-585">정규식이 해당 `Regex_netherlands_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-586">From `Keywords_netherlands_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-587">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-587">Keywords</span></span>

<span data-ttu-id="85d97-588">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-588"></span></span>
|<span data-ttu-id="85d97-589">**Keywords_netherlands_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-590">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-590">dl#</span></span>  <br/> <span data-ttu-id="85d97-591">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-591">driver license</span></span>  <br/> <span data-ttu-id="85d97-592">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-592">driver license number</span></span>  <br/> <span data-ttu-id="85d97-593">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-593">driver licence</span></span>  <br/> <span data-ttu-id="85d97-594">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-594">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-595">drivers license</span></span>  <br/> <span data-ttu-id="85d97-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-596">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-597">driver's license</span></span>  <br/> <span data-ttu-id="85d97-598">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-598">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-599">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-599">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-600">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-600">driving license number</span></span>  <br/> <span data-ttu-id="85d97-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-601">dlno#</span></span>  <br/> <span data-ttu-id="85d97-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="85d97-602">permis de conduire</span></span>  <br/> <span data-ttu-id="85d97-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="85d97-603">rijbewijs</span></span>  <br/> <span data-ttu-id="85d97-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="85d97-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="85d97-605">폴란드</span><span class="sxs-lookup"><span data-stu-id="85d97-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="85d97-606">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-606">Format</span></span>

<span data-ttu-id="85d97-607">두 개의 슬래시를 포함 하는 14 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-608">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-608">Pattern</span></span>

<span data-ttu-id="85d97-609">14 자리 숫자와 2 개의 슬래시:</span><span class="sxs-lookup"><span data-stu-id="85d97-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="85d97-610">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-610">Five digits</span></span> 
    
- <span data-ttu-id="85d97-611">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="85d97-611">A forward slash</span></span>
    
- <span data-ttu-id="85d97-612">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-612">Two digits</span></span>
    
- <span data-ttu-id="85d97-613">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="85d97-613">A forward slash</span></span>
    
- <span data-ttu-id="85d97-614">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-615">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-615">Checksum</span></span>

<span data-ttu-id="85d97-616">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-617">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-617">Definition</span></span>

<span data-ttu-id="85d97-618">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-619">정규식이 해당 `Regex_poland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-620">From `Keywords_poland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-621">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-621">Keywords</span></span>

<span data-ttu-id="85d97-622">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-622"></span></span>
|<span data-ttu-id="85d97-623">**Keywords_poland_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-624">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-624">dl#</span></span>  <br/> <span data-ttu-id="85d97-625">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-625">driver license</span></span>  <br/> <span data-ttu-id="85d97-626">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-626">driver license number</span></span>  <br/> <span data-ttu-id="85d97-627">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-627">driver licence</span></span>  <br/> <span data-ttu-id="85d97-628">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-628">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-629">drivers license</span></span>  <br/> <span data-ttu-id="85d97-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-630">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-631">driver's license</span></span>  <br/> <span data-ttu-id="85d97-632">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-632">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-633">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-633">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-634">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-634">driving license number</span></span>  <br/> <span data-ttu-id="85d97-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-635">dlno#</span></span>  <br/> <span data-ttu-id="85d97-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="85d97-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="85d97-637">포르투갈</span><span class="sxs-lookup"><span data-stu-id="85d97-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="85d97-638">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-638">Format</span></span>

<span data-ttu-id="85d97-639">두 개의 문자와 지정 된 패턴에 있는 일곱 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-640">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-640">Pattern</span></span>

<span data-ttu-id="85d97-641">두 문자 다음에 특수 문자를 사용한 7 개의 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="85d97-642">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="85d97-643">하이픈</span><span class="sxs-lookup"><span data-stu-id="85d97-643">A hyphen</span></span>
    
- <span data-ttu-id="85d97-644">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-644">Six digits</span></span>
    
- <span data-ttu-id="85d97-645">공백</span><span class="sxs-lookup"><span data-stu-id="85d97-645">A space</span></span>
    
- <span data-ttu-id="85d97-646">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-647">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-647">Checksum</span></span>

<span data-ttu-id="85d97-648">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-649">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-649">Definition</span></span>

<span data-ttu-id="85d97-650">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-651">정규식이 해당 `Regex_portugal_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-652">From `Keywords_portugal_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-653">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-653">Keywords</span></span>

<span data-ttu-id="85d97-654">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-654"></span></span>
|<span data-ttu-id="85d97-655">**Keywords_portugal_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-656">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-656">dl#</span></span>  <br/> <span data-ttu-id="85d97-657">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-657">driver license</span></span>  <br/> <span data-ttu-id="85d97-658">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-658">driver license number</span></span>  <br/> <span data-ttu-id="85d97-659">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-659">driver licence</span></span>  <br/> <span data-ttu-id="85d97-660">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-660">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-661">drivers license</span></span>  <br/> <span data-ttu-id="85d97-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-662">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-663">driver's license</span></span>  <br/> <span data-ttu-id="85d97-664">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-664">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-665">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-665">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-666">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-666">driving license number</span></span>  <br/> <span data-ttu-id="85d97-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-667">dlno#</span></span>  <br/> <span data-ttu-id="85d97-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="85d97-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="85d97-669">루마니아</span><span class="sxs-lookup"><span data-stu-id="85d97-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="85d97-670">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-670">Format</span></span>

<span data-ttu-id="85d97-671">한 문자 다음에 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-672">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-672">Pattern</span></span>

<span data-ttu-id="85d97-673">1 개의 문자 다음에 8 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="85d97-674">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="85d97-675">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-676">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-676">Checksum</span></span>

<span data-ttu-id="85d97-677">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-678">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-678">Definition</span></span>

<span data-ttu-id="85d97-679">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-680">정규식이 해당 `Regex_romania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-681">From `Keywords_romania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-682">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-682">Keywords</span></span>

<span data-ttu-id="85d97-683">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-683"></span></span>
|<span data-ttu-id="85d97-684">**Keywords_romania_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-685">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-685">dl#</span></span>  <br/> <span data-ttu-id="85d97-686">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-686">driver license</span></span>  <br/> <span data-ttu-id="85d97-687">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-687">driver license number</span></span>  <br/> <span data-ttu-id="85d97-688">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-688">driver licence</span></span>  <br/> <span data-ttu-id="85d97-689">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-689">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-690">drivers license</span></span>  <br/> <span data-ttu-id="85d97-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-691">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-692">driver's license</span></span>  <br/> <span data-ttu-id="85d97-693">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-693">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-694">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-694">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-695">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-695">driving license number</span></span>  <br/> <span data-ttu-id="85d97-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-696">dlno#</span></span>  <br/> <span data-ttu-id="85d97-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="85d97-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="85d97-698">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="85d97-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="85d97-699">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-699">Format</span></span>

<span data-ttu-id="85d97-700">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-701">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-701">Pattern</span></span>

<span data-ttu-id="85d97-702">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="85d97-703">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="85d97-704">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="85d97-705">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-705">Checksum</span></span>

<span data-ttu-id="85d97-706">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-707">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-707">Definition</span></span>

<span data-ttu-id="85d97-708">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-709">정규식이 해당 `Regex_slovakia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-710">From `Keywords_slovakia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-711">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-711">Keywords</span></span>

<span data-ttu-id="85d97-712">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-712"></span></span>
|<span data-ttu-id="85d97-713">**Keywords_slovakia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-714">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-714">dl#</span></span>  <br/> <span data-ttu-id="85d97-715">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-715">driver license</span></span>  <br/> <span data-ttu-id="85d97-716">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-716">driver license number</span></span>  <br/> <span data-ttu-id="85d97-717">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-717">driver licence</span></span>  <br/> <span data-ttu-id="85d97-718">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-718">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-719">drivers license</span></span>  <br/> <span data-ttu-id="85d97-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-720">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-721">driver's license</span></span>  <br/> <span data-ttu-id="85d97-722">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-722">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-723">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-723">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-724">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-724">driving license number</span></span>  <br/> <span data-ttu-id="85d97-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-725">dlno#</span></span>  <br/> <span data-ttu-id="85d97-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="85d97-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="85d97-727">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="85d97-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="85d97-728">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-728">Format</span></span>

<span data-ttu-id="85d97-729">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-730">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-730">Pattern</span></span>

<span data-ttu-id="85d97-731">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="85d97-732">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-732">Checksum</span></span>

<span data-ttu-id="85d97-733">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-734">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-734">Definition</span></span>

<span data-ttu-id="85d97-735">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-736">정규식이 해당 `Regex_slovenia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-737">From `Keywords_slovenia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-738">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-738">Keywords</span></span>

<span data-ttu-id="85d97-739">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-739"></span></span>
|<span data-ttu-id="85d97-740">**Keywords_slovenia_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-741">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-741">dl#</span></span>  <br/> <span data-ttu-id="85d97-742">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-742">driver license</span></span>  <br/> <span data-ttu-id="85d97-743">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-743">driver license number</span></span>  <br/> <span data-ttu-id="85d97-744">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-744">driver licence</span></span>  <br/> <span data-ttu-id="85d97-745">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-745">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-746">drivers license</span></span>  <br/> <span data-ttu-id="85d97-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-747">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-748">driver's license</span></span>  <br/> <span data-ttu-id="85d97-749">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-749">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-750">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-750">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-751">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-751">driving license number</span></span>  <br/> <span data-ttu-id="85d97-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-752">dlno#</span></span>  <br/> <span data-ttu-id="85d97-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="85d97-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="85d97-754">스페인</span><span class="sxs-lookup"><span data-stu-id="85d97-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="85d97-755">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-755">Format</span></span>

<span data-ttu-id="85d97-756">8 자리 숫자와 문자 1 개</span><span class="sxs-lookup"><span data-stu-id="85d97-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-757">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-757">Pattern</span></span>

<span data-ttu-id="85d97-758">8 자리 숫자와 문자 1 개:</span><span class="sxs-lookup"><span data-stu-id="85d97-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="85d97-759">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-759">Eight digits</span></span> 
    
- <span data-ttu-id="85d97-760">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="85d97-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-761">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-761">Checksum</span></span>

<span data-ttu-id="85d97-762">예</span><span class="sxs-lookup"><span data-stu-id="85d97-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-763">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-763">Definition</span></span>

<span data-ttu-id="85d97-764">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-765">이 함수 `Func_spain_eu_driver's_license_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-766">From `Keywords_spain_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="85d97-767">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-767">Keywords</span></span>

<span data-ttu-id="85d97-768">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-768"></span></span>
|<span data-ttu-id="85d97-769">**Keywords_spain_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-770">dlno#</span></span>  <br/> <span data-ttu-id="85d97-771">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-771">dl#</span></span>  <br/> <span data-ttu-id="85d97-772">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-772">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-773">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-773">driver licence</span></span>  <br/> <span data-ttu-id="85d97-774">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-774">driver license</span></span>  <br/> <span data-ttu-id="85d97-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-775">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-776">drivers license</span></span>  <br/> <span data-ttu-id="85d97-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="85d97-777">driver's licence</span></span>  <br/> <span data-ttu-id="85d97-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-778">driver's license</span></span>  <br/> <span data-ttu-id="85d97-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="85d97-779">driving licence</span></span>  <br/> <span data-ttu-id="85d97-780">driving license</span><span class="sxs-lookup"><span data-stu-id="85d97-780">driving license</span></span>  <br/> <span data-ttu-id="85d97-781">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-781">driver licence number</span></span>  <br/> <span data-ttu-id="85d97-782">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-782">driver license number</span></span>  <br/> <span data-ttu-id="85d97-783">영향 요소 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-783">drivers licence number</span></span>  <br/> <span data-ttu-id="85d97-784">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-784">drivers license number</span></span>  <br/> <span data-ttu-id="85d97-785">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-785">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-786">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-786">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-787">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-787">driving licence number</span></span>  <br/> <span data-ttu-id="85d97-788">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-788">driving license number</span></span>  <br/> <span data-ttu-id="85d97-789">추진 허용</span><span class="sxs-lookup"><span data-stu-id="85d97-789">driving permit</span></span>  <br/> <span data-ttu-id="85d97-790">제어 허용 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-790">driving permit number</span></span>  <br/> <span data-ttu-id="85d97-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="85d97-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="85d97-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="85d97-792">permiso conducción</span></span>  <br/> <span data-ttu-id="85d97-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="85d97-794">número de 네트워크 de conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="85d97-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="85d97-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-796">licencia conducir</span></span>  <br/> <span data-ttu-id="85d97-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="85d97-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="85d97-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="85d97-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-800">permiso conducir</span></span>  <br/> <span data-ttu-id="85d97-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="85d97-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="85d97-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="85d97-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="85d97-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="85d97-804">스웨덴</span><span class="sxs-lookup"><span data-stu-id="85d97-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="85d97-805">형식일</span><span class="sxs-lookup"><span data-stu-id="85d97-805">Format</span></span>

<span data-ttu-id="85d97-806">하이픈을 포함 하는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="85d97-807">패턴</span><span class="sxs-lookup"><span data-stu-id="85d97-807">Pattern</span></span>

<span data-ttu-id="85d97-808">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="85d97-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="85d97-809">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-809">Six digits</span></span> 
    
- <span data-ttu-id="85d97-810">하이픈</span><span class="sxs-lookup"><span data-stu-id="85d97-810">A hyphen</span></span>
    
- <span data-ttu-id="85d97-811">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="85d97-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="85d97-812">제외</span><span class="sxs-lookup"><span data-stu-id="85d97-812">Checksum</span></span>

<span data-ttu-id="85d97-813">아니요</span><span class="sxs-lookup"><span data-stu-id="85d97-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="85d97-814">정의</span><span class="sxs-lookup"><span data-stu-id="85d97-814">Definition</span></span>

<span data-ttu-id="85d97-815">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="85d97-816">정규식이 해당 `Regex_sweden_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="85d97-817">From `Keywords_sweden_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="85d97-818">키워드</span><span class="sxs-lookup"><span data-stu-id="85d97-818">Keywords</span></span>

<span data-ttu-id="85d97-819">| |</span><span class="sxs-lookup"><span data-stu-id="85d97-819"></span></span>
|<span data-ttu-id="85d97-820">**Keywords_sweden_eu_driver's_license_number**</span><span class="sxs-lookup"><span data-stu-id="85d97-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="85d97-821">dl #</span><span class="sxs-lookup"><span data-stu-id="85d97-821">dl#</span></span>  <br/> <span data-ttu-id="85d97-822">driver license</span><span class="sxs-lookup"><span data-stu-id="85d97-822">driver license</span></span>  <br/> <span data-ttu-id="85d97-823">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-823">driver license number</span></span>  <br/> <span data-ttu-id="85d97-824">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="85d97-824">driver licence</span></span>  <br/> <span data-ttu-id="85d97-825">drivers lic</span><span class="sxs-lookup"><span data-stu-id="85d97-825">drivers lic.</span></span>  <br/> <span data-ttu-id="85d97-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="85d97-826">drivers license</span></span>  <br/> <span data-ttu-id="85d97-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="85d97-827">drivers licence</span></span>  <br/> <span data-ttu-id="85d97-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="85d97-828">driver's license</span></span>  <br/> <span data-ttu-id="85d97-829">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-829">driver's license number</span></span>  <br/> <span data-ttu-id="85d97-830">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-830">driver's licence number</span></span>  <br/> <span data-ttu-id="85d97-831">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="85d97-831">driving license number</span></span>  <br/> <span data-ttu-id="85d97-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="85d97-832">dlno#</span></span>  <br/> <span data-ttu-id="85d97-833">körkort</span><span class="sxs-lookup"><span data-stu-id="85d97-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="85d97-834">영국의</span><span class="sxs-lookup"><span data-stu-id="85d97-834">UK</span></span>

<span data-ttu-id="85d97-835">자세한 내용은 영국 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="85d97-835">For details, see the section "U.K.</span></span> <span data-ttu-id="85d97-836">[중요 한 정보 유형에 서 확인 되는](what-the-sensitive-information-types-look-for.md)운전 면허 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="85d97-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="85d97-837">참고 항목</span><span class="sxs-lookup"><span data-stu-id="85d97-837">See also</span></span>

[<span data-ttu-id="85d97-838">중요한 정보 형식이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="85d97-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

