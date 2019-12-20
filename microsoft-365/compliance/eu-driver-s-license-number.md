---
title: EU 운전 면허 번호
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: 6df025caf8d06c617e09a3b53dc6c82d69aaf5a8
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/19/2019
ms.locfileid: "40805961"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="b59dd-104">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-104">EU Driver's License Number</span></span>

<span data-ttu-id="b59dd-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="b59dd-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b59dd-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="b59dd-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-108">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-108">Format</span></span>

<span data-ttu-id="b59dd-109">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-110">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-110">Pattern</span></span>

<span data-ttu-id="b59dd-111">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-112">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-112">Checksum</span></span>

<span data-ttu-id="b59dd-113">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-114">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-114">Definition</span></span>

<span data-ttu-id="b59dd-115">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-116">정규식이 해당 `Regex_austria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-117">From `Keywords_austria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="b59dd-118">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-118">Keywords</span></span>

<span data-ttu-id="b59dd-119">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-119"></span></span>
|<span data-ttu-id="b59dd-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-121">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-121">dl#</span></span>  <br/> <span data-ttu-id="b59dd-122">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-122">driver license</span></span>  <br/> <span data-ttu-id="b59dd-123">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-123">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-124">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-124">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-125">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-125">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-126">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-127">driver's licence</span></span>  <br/> <span data-ttu-id="b59dd-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-128">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-129">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-129">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-130">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="b59dd-131">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-131">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-132">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="b59dd-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="b59dd-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="b59dd-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="b59dd-135">벨기에</span><span class="sxs-lookup"><span data-stu-id="b59dd-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-136">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-136">Format</span></span>

<span data-ttu-id="b59dd-137">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-138">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-138">Pattern</span></span>

<span data-ttu-id="b59dd-139">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-140">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-140">Checksum</span></span>

<span data-ttu-id="b59dd-141">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-142">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-142">Definition</span></span>

<span data-ttu-id="b59dd-143">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-144">정규식이 해당 `Regex_belgium_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-145">From `Keywords_belgium_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b59dd-146">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-146">Keywords</span></span>

<span data-ttu-id="b59dd-147">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-147"></span></span>
|<span data-ttu-id="b59dd-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-149">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-149">dl#</span></span>  <br/> <span data-ttu-id="b59dd-150">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-150">driver license</span></span>  <br/> <span data-ttu-id="b59dd-151">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-151">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-152">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-152">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-153">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-153">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-154">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-155">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-156">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-157">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-157">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-158">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-158">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-159">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="b59dd-160">rijbewijs</span></span>  <br/> <span data-ttu-id="b59dd-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="b59dd-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="b59dd-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="b59dd-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="b59dd-165">führerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="b59dd-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="b59dd-166">fuehrerschein-Veiligheid</span><span class="sxs-lookup"><span data-stu-id="b59dd-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="b59dd-167">fuehrerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="b59dd-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="b59dd-168">불가리아</span><span class="sxs-lookup"><span data-stu-id="b59dd-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-169">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-169">Format</span></span>

<span data-ttu-id="b59dd-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-171">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-171">Pattern</span></span>

<span data-ttu-id="b59dd-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-173">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-173">Checksum</span></span>

<span data-ttu-id="b59dd-174">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-175">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-175">Definition</span></span>

<span data-ttu-id="b59dd-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-177">정규식이 해당 `Regex_bulgaria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-178">From `Keywords_bulgaria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="b59dd-179">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-179">Keywords</span></span>

<span data-ttu-id="b59dd-180">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-180"></span></span>
|<span data-ttu-id="b59dd-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-182">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-182">dl#</span></span>  <br/> <span data-ttu-id="b59dd-183">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-183">driver license</span></span>  <br/> <span data-ttu-id="b59dd-184">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-184">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-185">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-185">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-186">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-186">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-187">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-188">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-189">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-190">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-190">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-191">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-191">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-192">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-192">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-193">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="b59dd-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="b59dd-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="b59dd-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="b59dd-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="b59dd-196">сумпс</span></span>  <br/> <span data-ttu-id="b59dd-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="b59dd-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="b59dd-198">크로아티아</span><span class="sxs-lookup"><span data-stu-id="b59dd-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-199">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-199">Format</span></span>

<span data-ttu-id="b59dd-200">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-201">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-201">Pattern</span></span>

<span data-ttu-id="b59dd-202">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-203">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-203">Checksum</span></span>

<span data-ttu-id="b59dd-204">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-205">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-205">Definition</span></span>

<span data-ttu-id="b59dd-206">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-207">정규식이 해당 `Regex_croatia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-208">From `Keywords_croatia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b59dd-209">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-209">Keywords</span></span>

<span data-ttu-id="b59dd-210">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-210"></span></span>
|<span data-ttu-id="b59dd-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-212">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-212">dl#</span></span>  <br/> <span data-ttu-id="b59dd-213">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-213">driver license</span></span>  <br/> <span data-ttu-id="b59dd-214">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-214">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-215">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-215">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-216">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-216">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-217">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-218">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-219">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-220">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-220">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-221">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-221">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-222">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-222">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-223">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="b59dd-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="b59dd-225">키프로스</span><span class="sxs-lookup"><span data-stu-id="b59dd-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-226">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-226">Format</span></span>

<span data-ttu-id="b59dd-227">공백과 구분 기호를 사용 하지 않고 12 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-228">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-228">Pattern</span></span>

<span data-ttu-id="b59dd-229">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-230">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-230">Checksum</span></span>

<span data-ttu-id="b59dd-231">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-232">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-232">Definition</span></span>

<span data-ttu-id="b59dd-233">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-234">정규식이 해당 `Regex_cyprus_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-235">From `Keywords_cyprus_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-236">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-236">Keywords</span></span>

<span data-ttu-id="b59dd-237">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-237"></span></span>
|<span data-ttu-id="b59dd-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-239">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-239">dl#</span></span>  <br/> <span data-ttu-id="b59dd-240">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-240">driver license</span></span>  <br/> <span data-ttu-id="b59dd-241">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-241">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-242">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-242">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-243">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-243">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-244">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-245">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-246">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-246">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-247">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-247">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-248">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-248">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-249">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="b59dd-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="b59dd-251">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="b59dd-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-252">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-252">Format</span></span>

<span data-ttu-id="b59dd-253">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-254">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-254">Pattern</span></span>

<span data-ttu-id="b59dd-255">8 개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="b59dd-256">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="b59dd-257">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b59dd-257">A space (optional)</span></span>
    
- <span data-ttu-id="b59dd-258">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-259">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-259">Checksum</span></span>

<span data-ttu-id="b59dd-260">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-261">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-261">Definition</span></span>

<span data-ttu-id="b59dd-262">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-263">정규식이 해당 `Regex_czech_republic_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-264">From `Keywords_czech_republic_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b59dd-265">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-265">Keywords</span></span>

<span data-ttu-id="b59dd-266">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-266"></span></span>
|<span data-ttu-id="b59dd-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-268">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-268">dl#</span></span>  <br/> <span data-ttu-id="b59dd-269">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-269">driver license</span></span>  <br/> <span data-ttu-id="b59dd-270">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-270">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-271">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-271">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-272">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-272">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-273">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-274">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-275">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-276">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-276">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-277">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-277">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-278">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-278">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-279">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-279">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-280">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="b59dd-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="b59dd-282">덴마크</span><span class="sxs-lookup"><span data-stu-id="b59dd-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-283">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-283">Format</span></span>

<span data-ttu-id="b59dd-284">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-285">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-285">Pattern</span></span>

<span data-ttu-id="b59dd-286">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-287">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-287">Checksum</span></span>

<span data-ttu-id="b59dd-288">예</span><span class="sxs-lookup"><span data-stu-id="b59dd-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-289">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-289">Definition</span></span>

<span data-ttu-id="b59dd-290">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-291">정규식이 해당 `Regex_denmark_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-292">From `Keywords_denmark_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="b59dd-293">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-293">Keywords</span></span>

<span data-ttu-id="b59dd-294">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-294"></span></span>
|<span data-ttu-id="b59dd-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-296">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-296">dl#</span></span>  <br/> <span data-ttu-id="b59dd-297">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-297">driver license</span></span>  <br/> <span data-ttu-id="b59dd-298">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-298">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-299">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-299">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-300">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-300">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-301">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-302">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-303">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-304">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-304">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-305">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-305">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-306">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-306">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-307">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="b59dd-308">kørekort</span></span>  <br/> <span data-ttu-id="b59dd-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="b59dd-310">에스토니아</span><span class="sxs-lookup"><span data-stu-id="b59dd-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-311">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-311">Format</span></span>

<span data-ttu-id="b59dd-312">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-313">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-313">Pattern</span></span>

<span data-ttu-id="b59dd-314">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="b59dd-315">문자 "ET" (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b59dd-316">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-317">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-317">Checksum</span></span>

<span data-ttu-id="b59dd-318">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-319">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-319">Definition</span></span>

<span data-ttu-id="b59dd-320">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-321">정규식이 해당 `Regex_estonia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-322">From `Keywords_estonia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-323">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-323">Keywords</span></span>

<span data-ttu-id="b59dd-324">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-324"></span></span>
|<span data-ttu-id="b59dd-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-326">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-326">dl#</span></span>  <br/> <span data-ttu-id="b59dd-327">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-327">driver license</span></span>  <br/> <span data-ttu-id="b59dd-328">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-328">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-329">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-329">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-330">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-330">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-331">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-331">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-332">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-333">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-334">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-335">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-335">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-336">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-336">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-337">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="b59dd-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="b59dd-339">핀란드</span><span class="sxs-lookup"><span data-stu-id="b59dd-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-340">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-340">Format</span></span>

<span data-ttu-id="b59dd-341">하이픈을 포함하는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-342">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-342">Pattern</span></span>

<span data-ttu-id="b59dd-343">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="b59dd-344">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-344">Six digits</span></span> 
    
- <span data-ttu-id="b59dd-345">하이픈</span><span class="sxs-lookup"><span data-stu-id="b59dd-345">A hyphen</span></span>
    
-  <span data-ttu-id="b59dd-346">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b59dd-347">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-347">Checksum</span></span>

<span data-ttu-id="b59dd-348">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-349">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-349">Definition</span></span>

<span data-ttu-id="b59dd-350">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-351">정규식이 해당 `Regex_finland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-352">From `Keywords_finland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-353">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-353">Keywords</span></span>

<span data-ttu-id="b59dd-354">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-354"></span></span>
|<span data-ttu-id="b59dd-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-356">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-356">dl#</span></span>  <br/> <span data-ttu-id="b59dd-357">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-357">driver license</span></span>  <br/> <span data-ttu-id="b59dd-358">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-358">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-359">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-359">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-360">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-360">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-361">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-362">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-363">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-364">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-364">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-365">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-365">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-366">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-366">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-367">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="b59dd-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="b59dd-369">프랑스</span><span class="sxs-lookup"><span data-stu-id="b59dd-369">France</span></span>

<span data-ttu-id="b59dd-370">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"경기도 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b59dd-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="b59dd-371">독일</span><span class="sxs-lookup"><span data-stu-id="b59dd-371">Germany</span></span>

<span data-ttu-id="b59dd-372">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일어 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b59dd-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="b59dd-373">그리스</span><span class="sxs-lookup"><span data-stu-id="b59dd-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-374">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-374">Format</span></span>

<span data-ttu-id="b59dd-375">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-376">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-376">Pattern</span></span>

 <span data-ttu-id="b59dd-377">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b59dd-378">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-378">Checksum</span></span>

<span data-ttu-id="b59dd-379">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-380">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-380">Definition</span></span>

<span data-ttu-id="b59dd-381">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-382">정규식이 해당 `Regex_greece_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-383">From `Keywords_greece_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-384">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-384">Keywords</span></span>

<span data-ttu-id="b59dd-385">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-385"></span></span>
|<span data-ttu-id="b59dd-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="b59dd-387">dlL#</span></span>  <br/> <span data-ttu-id="b59dd-388">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-388">driver license</span></span>  <br/> <span data-ttu-id="b59dd-389">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-389">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-390">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-390">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-391">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-391">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-392">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-393">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-394">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-395">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-395">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-396">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-396">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-397">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-397">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-398">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="b59dd-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="b59dd-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="b59dd-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="b59dd-401">헝가리</span><span class="sxs-lookup"><span data-stu-id="b59dd-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-402">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-402">Format</span></span>

<span data-ttu-id="b59dd-403">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-404">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-404">Pattern</span></span>

<span data-ttu-id="b59dd-405">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="b59dd-406">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b59dd-407">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-408">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-408">Checksum</span></span>

<span data-ttu-id="b59dd-409">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-410">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-410">Definition</span></span>

<span data-ttu-id="b59dd-411">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-412">정규식이 해당 `Regex_hungary_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-413">From `Keywords_hungary_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-414">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-414">Keywords</span></span>

<span data-ttu-id="b59dd-415">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-415"></span></span>
|<span data-ttu-id="b59dd-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-417">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-417">dl#</span></span>  <br/> <span data-ttu-id="b59dd-418">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-418">driver license</span></span>  <br/> <span data-ttu-id="b59dd-419">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-419">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-420">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-420">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-421">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-421">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-422">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-423">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-424">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-425">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-425">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-426">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-426">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-427">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-427">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-428">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-429">vezetoi</span><span class="sxs-lookup"><span data-stu-id="b59dd-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="b59dd-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="b59dd-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-431">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-431">Format</span></span>

<span data-ttu-id="b59dd-432">6 자리 숫자와 4 개 문자</span><span class="sxs-lookup"><span data-stu-id="b59dd-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-433">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-433">Pattern</span></span>

<span data-ttu-id="b59dd-434">6 자리 숫자와 4 개 문자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="b59dd-435">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-435">Six digits</span></span>
    
- <span data-ttu-id="b59dd-436">4 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-437">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-437">Checksum</span></span>

<span data-ttu-id="b59dd-438">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-439">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-439">Definition</span></span>

<span data-ttu-id="b59dd-440">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-441">정규식이 해당 `Regex_ireland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-442">From `Keywords_ireland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-443">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-443">Keywords</span></span>

<span data-ttu-id="b59dd-444">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-444"></span></span>
|<span data-ttu-id="b59dd-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-446">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-446">dl#</span></span>  <br/> <span data-ttu-id="b59dd-447">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-447">driver license</span></span>  <br/> <span data-ttu-id="b59dd-448">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-448">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-449">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-449">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-450">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-450">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-451">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-452">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-453">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-454">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-454">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-455">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-455">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-456">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-456">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-457">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="b59dd-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="b59dd-459">이탈리아</span><span class="sxs-lookup"><span data-stu-id="b59dd-459">Italy</span></span>

<span data-ttu-id="b59dd-460">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"이탈리아 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b59dd-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="b59dd-461">라트비아</span><span class="sxs-lookup"><span data-stu-id="b59dd-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-462">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-462">Format</span></span>

<span data-ttu-id="b59dd-463">3 개의 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-464">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-464">Pattern</span></span>

<span data-ttu-id="b59dd-465">3 개의 문자 및 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="b59dd-466">3 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b59dd-467">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-468">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-468">Checksum</span></span>

<span data-ttu-id="b59dd-469">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-470">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-470">Definition</span></span>

<span data-ttu-id="b59dd-471">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-472">정규식이 해당 `Regex_latvia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-473">From `Keywords_latvia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-474">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-474">Keywords</span></span>

<span data-ttu-id="b59dd-475">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-475"></span></span>
|<span data-ttu-id="b59dd-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-477">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-477">dl#</span></span>  <br/> <span data-ttu-id="b59dd-478">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-478">driver license</span></span>  <br/> <span data-ttu-id="b59dd-479">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-479">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-480">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-480">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-481">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-481">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-482">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-483">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-484">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-485">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-485">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-486">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-486">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-487">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-487">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-488">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="b59dd-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="b59dd-490">리투아니아</span><span class="sxs-lookup"><span data-stu-id="b59dd-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-491">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-491">Format</span></span>

<span data-ttu-id="b59dd-492">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-493">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-493">Pattern</span></span>

 <span data-ttu-id="b59dd-494">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b59dd-495">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-495">Checksum</span></span>

<span data-ttu-id="b59dd-496">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-497">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-497">Definition</span></span>

<span data-ttu-id="b59dd-498">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-499">정규식이 해당 `Regex_lithuania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-500">From `Keywords_lithuania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-501">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-501">Keywords</span></span>

<span data-ttu-id="b59dd-502">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-502"></span></span>
|<span data-ttu-id="b59dd-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-504">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-504">dl#</span></span>  <br/> <span data-ttu-id="b59dd-505">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-505">driver license</span></span>  <br/> <span data-ttu-id="b59dd-506">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-506">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-507">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-507">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-508">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-508">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-509">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-510">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-511">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-512">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-512">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-513">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-513">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-514">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-514">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-515">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="b59dd-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="b59dd-517">셈</span><span class="sxs-lookup"><span data-stu-id="b59dd-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-518">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-518">Format</span></span>

<span data-ttu-id="b59dd-519">공백과 구분 기호가 없는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-520">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-520">Pattern</span></span>

 <span data-ttu-id="b59dd-521">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b59dd-522">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-522">Checksum</span></span>

<span data-ttu-id="b59dd-523">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-524">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-524">Definition</span></span>

<span data-ttu-id="b59dd-525">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-526">정규식이 해당 `Regex_luxemburg_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-527">From `Keywords_luxemburg_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-528">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-528">Keywords</span></span>

<span data-ttu-id="b59dd-529">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-529"></span></span>
|<span data-ttu-id="b59dd-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-531">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-531">dl#</span></span>  <br/> <span data-ttu-id="b59dd-532">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-532">driver license</span></span>  <br/> <span data-ttu-id="b59dd-533">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-533">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-534">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-534">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-535">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-535">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-536">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-537">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-538">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-539">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-539">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-540">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-540">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-541">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-541">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-542">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="b59dd-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="b59dd-544">몰타</span><span class="sxs-lookup"><span data-stu-id="b59dd-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-545">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-545">Format</span></span>

<span data-ttu-id="b59dd-546">지정 된 패턴에서 두 개의 문자와 6 자리 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="b59dd-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-547">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-547">Pattern</span></span>

<span data-ttu-id="b59dd-548">두 문자와 6 자리 숫자의 조합:</span><span class="sxs-lookup"><span data-stu-id="b59dd-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="b59dd-549">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="b59dd-550">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b59dd-550">A space (optional)</span></span>
    
- <span data-ttu-id="b59dd-551">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-551">Three digits</span></span>
    
- <span data-ttu-id="b59dd-552">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b59dd-552">A space (optional)</span></span>
    
- <span data-ttu-id="b59dd-553">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-554">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-554">Checksum</span></span>

<span data-ttu-id="b59dd-555">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-556">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-556">Definition</span></span>

<span data-ttu-id="b59dd-557">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-558">정규식이 해당 `Regex_malta_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-559">From `Keywords_malta_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-560">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-560">Keywords</span></span>

<span data-ttu-id="b59dd-561">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-561"></span></span>
|<span data-ttu-id="b59dd-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-563">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-563">dl#</span></span>  <br/> <span data-ttu-id="b59dd-564">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-564">driver license</span></span>  <br/> <span data-ttu-id="b59dd-565">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-565">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-566">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-566">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-567">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-567">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-568">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-569">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-570">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-571">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-571">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-572">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-572">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-573">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-573">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-574">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="b59dd-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="b59dd-576">네덜란드</span><span class="sxs-lookup"><span data-stu-id="b59dd-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-577">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-577">Format</span></span>

<span data-ttu-id="b59dd-578">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-579">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-579">Pattern</span></span>

<span data-ttu-id="b59dd-580">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-581">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-581">Checksum</span></span>

<span data-ttu-id="b59dd-582">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-583">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-583">Definition</span></span>

<span data-ttu-id="b59dd-584">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-585">정규식이 해당 `Regex_netherlands_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-586">From `Keywords_netherlands_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-587">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-587">Keywords</span></span>

<span data-ttu-id="b59dd-588">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-588"></span></span>
|<span data-ttu-id="b59dd-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-590">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-590">dl#</span></span>  <br/> <span data-ttu-id="b59dd-591">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-591">driver license</span></span>  <br/> <span data-ttu-id="b59dd-592">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-592">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-593">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-593">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-594">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-594">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-595">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-596">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-597">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-598">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-598">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-599">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-599">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-600">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-600">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-601">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="b59dd-602">permis de conduire</span></span>  <br/> <span data-ttu-id="b59dd-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="b59dd-603">rijbewijs</span></span>  <br/> <span data-ttu-id="b59dd-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="b59dd-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="b59dd-605">폴란드</span><span class="sxs-lookup"><span data-stu-id="b59dd-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-606">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-606">Format</span></span>

<span data-ttu-id="b59dd-607">두 개의 슬래시를 포함 하는 14 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-608">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-608">Pattern</span></span>

<span data-ttu-id="b59dd-609">14 자리 숫자와 2 개의 슬래시:</span><span class="sxs-lookup"><span data-stu-id="b59dd-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="b59dd-610">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-610">Five digits</span></span> 
    
- <span data-ttu-id="b59dd-611">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="b59dd-611">A forward slash</span></span>
    
- <span data-ttu-id="b59dd-612">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-612">Two digits</span></span>
    
- <span data-ttu-id="b59dd-613">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="b59dd-613">A forward slash</span></span>
    
- <span data-ttu-id="b59dd-614">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-615">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-615">Checksum</span></span>

<span data-ttu-id="b59dd-616">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-617">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-617">Definition</span></span>

<span data-ttu-id="b59dd-618">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-619">정규식이 해당 `Regex_poland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-620">From `Keywords_poland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-621">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-621">Keywords</span></span>

<span data-ttu-id="b59dd-622">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-622"></span></span>
|<span data-ttu-id="b59dd-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-624">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-624">dl#</span></span>  <br/> <span data-ttu-id="b59dd-625">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-625">driver license</span></span>  <br/> <span data-ttu-id="b59dd-626">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-626">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-627">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-627">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-628">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-628">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-629">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-630">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-631">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-632">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-632">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-633">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-633">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-634">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-634">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-635">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="b59dd-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="b59dd-637">포르투갈</span><span class="sxs-lookup"><span data-stu-id="b59dd-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-638">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-638">Format</span></span>

<span data-ttu-id="b59dd-639">두 개의 문자와 지정 된 패턴에 있는 일곱 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-640">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-640">Pattern</span></span>

<span data-ttu-id="b59dd-641">두 문자 다음에 특수 문자를 사용한 7 개의 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="b59dd-642">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="b59dd-643">하이픈</span><span class="sxs-lookup"><span data-stu-id="b59dd-643">A hyphen</span></span>
    
- <span data-ttu-id="b59dd-644">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-644">Six digits</span></span>
    
- <span data-ttu-id="b59dd-645">공백</span><span class="sxs-lookup"><span data-stu-id="b59dd-645">A space</span></span>
    
- <span data-ttu-id="b59dd-646">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-647">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-647">Checksum</span></span>

<span data-ttu-id="b59dd-648">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-649">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-649">Definition</span></span>

<span data-ttu-id="b59dd-650">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-651">정규식이 해당 `Regex_portugal_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-652">From `Keywords_portugal_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-653">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-653">Keywords</span></span>

<span data-ttu-id="b59dd-654">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-654"></span></span>
|<span data-ttu-id="b59dd-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-656">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-656">dl#</span></span>  <br/> <span data-ttu-id="b59dd-657">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-657">driver license</span></span>  <br/> <span data-ttu-id="b59dd-658">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-658">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-659">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-659">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-660">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-660">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-661">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-662">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-663">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-664">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-664">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-665">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-665">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-666">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-666">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-667">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="b59dd-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="b59dd-669">루마니아</span><span class="sxs-lookup"><span data-stu-id="b59dd-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-670">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-670">Format</span></span>

<span data-ttu-id="b59dd-671">한 문자 다음에 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-672">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-672">Pattern</span></span>

<span data-ttu-id="b59dd-673">1 개의 문자 다음에 8 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="b59dd-674">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="b59dd-675">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-676">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-676">Checksum</span></span>

<span data-ttu-id="b59dd-677">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-678">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-678">Definition</span></span>

<span data-ttu-id="b59dd-679">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-680">정규식이 해당 `Regex_romania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-681">From `Keywords_romania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-682">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-682">Keywords</span></span>

<span data-ttu-id="b59dd-683">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-683"></span></span>
|<span data-ttu-id="b59dd-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-685">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-685">dl#</span></span>  <br/> <span data-ttu-id="b59dd-686">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-686">driver license</span></span>  <br/> <span data-ttu-id="b59dd-687">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-687">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-688">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-688">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-689">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-689">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-690">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-691">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-692">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-693">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-693">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-694">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-694">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-695">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-695">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-696">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="b59dd-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="b59dd-698">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="b59dd-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-699">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-699">Format</span></span>

<span data-ttu-id="b59dd-700">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-701">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-701">Pattern</span></span>

<span data-ttu-id="b59dd-702">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="b59dd-703">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="b59dd-704">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b59dd-705">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-705">Checksum</span></span>

<span data-ttu-id="b59dd-706">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-707">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-707">Definition</span></span>

<span data-ttu-id="b59dd-708">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-709">정규식이 해당 `Regex_slovakia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-710">From `Keywords_slovakia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-711">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-711">Keywords</span></span>

<span data-ttu-id="b59dd-712">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-712"></span></span>
|<span data-ttu-id="b59dd-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-714">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-714">dl#</span></span>  <br/> <span data-ttu-id="b59dd-715">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-715">driver license</span></span>  <br/> <span data-ttu-id="b59dd-716">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-716">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-717">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-717">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-718">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-718">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-719">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-720">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-721">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-722">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-722">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-723">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-723">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-724">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-724">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-725">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="b59dd-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="b59dd-727">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="b59dd-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-728">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-728">Format</span></span>

<span data-ttu-id="b59dd-729">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-730">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-730">Pattern</span></span>

<span data-ttu-id="b59dd-731">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b59dd-732">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-732">Checksum</span></span>

<span data-ttu-id="b59dd-733">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-734">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-734">Definition</span></span>

<span data-ttu-id="b59dd-735">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-736">정규식이 해당 `Regex_slovenia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-737">From `Keywords_slovenia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-738">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-738">Keywords</span></span>

<span data-ttu-id="b59dd-739">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-739"></span></span>
|<span data-ttu-id="b59dd-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-741">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-741">dl#</span></span>  <br/> <span data-ttu-id="b59dd-742">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-742">driver license</span></span>  <br/> <span data-ttu-id="b59dd-743">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-743">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-744">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-744">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-745">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-745">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-746">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-747">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-748">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-749">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-749">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-750">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-750">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-751">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-751">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-752">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="b59dd-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="b59dd-754">스페인</span><span class="sxs-lookup"><span data-stu-id="b59dd-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-755">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-755">Format</span></span>

<span data-ttu-id="b59dd-756">8 자리 숫자와 문자 1 개</span><span class="sxs-lookup"><span data-stu-id="b59dd-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-757">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-757">Pattern</span></span>

<span data-ttu-id="b59dd-758">8 자리 숫자와 문자 1 개:</span><span class="sxs-lookup"><span data-stu-id="b59dd-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="b59dd-759">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-759">Eight digits</span></span> 
    
- <span data-ttu-id="b59dd-760">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b59dd-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-761">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-761">Checksum</span></span>

<span data-ttu-id="b59dd-762">예</span><span class="sxs-lookup"><span data-stu-id="b59dd-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-763">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-763">Definition</span></span>

<span data-ttu-id="b59dd-764">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-765">이 함수 `Func_spain_eu_driver's_license_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-766">From `Keywords_spain_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b59dd-767">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-767">Keywords</span></span>

<span data-ttu-id="b59dd-768">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-768"></span></span>
|<span data-ttu-id="b59dd-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-770">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-771">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-771">dl#</span></span>  <br/> <span data-ttu-id="b59dd-772">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-772">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-773">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-773">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-774">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-774">driver license</span></span>  <br/> <span data-ttu-id="b59dd-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-775">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-776">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-777">driver's licence</span></span>  <br/> <span data-ttu-id="b59dd-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-778">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-779">driving licence</span></span>  <br/> <span data-ttu-id="b59dd-780">driving license</span><span class="sxs-lookup"><span data-stu-id="b59dd-780">driving license</span></span>  <br/> <span data-ttu-id="b59dd-781">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-781">driver licence number</span></span>  <br/> <span data-ttu-id="b59dd-782">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-782">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-783">영향 요소 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-783">drivers licence number</span></span>  <br/> <span data-ttu-id="b59dd-784">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-784">drivers license number</span></span>  <br/> <span data-ttu-id="b59dd-785">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-785">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-786">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-786">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-787">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-787">driving licence number</span></span>  <br/> <span data-ttu-id="b59dd-788">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-788">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-789">추진 허용</span><span class="sxs-lookup"><span data-stu-id="b59dd-789">driving permit</span></span>  <br/> <span data-ttu-id="b59dd-790">제어 허용 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-790">driving permit number</span></span>  <br/> <span data-ttu-id="b59dd-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="b59dd-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="b59dd-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="b59dd-792">permiso conducción</span></span>  <br/> <span data-ttu-id="b59dd-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="b59dd-794">número de 네트워크 de conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="b59dd-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="b59dd-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-796">licencia conducir</span></span>  <br/> <span data-ttu-id="b59dd-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="b59dd-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="b59dd-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="b59dd-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-800">permiso conducir</span></span>  <br/> <span data-ttu-id="b59dd-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="b59dd-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="b59dd-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="b59dd-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="b59dd-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="b59dd-804">스웨덴</span><span class="sxs-lookup"><span data-stu-id="b59dd-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="b59dd-805">형식일</span><span class="sxs-lookup"><span data-stu-id="b59dd-805">Format</span></span>

<span data-ttu-id="b59dd-806">하이픈을 포함 하는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b59dd-807">패턴</span><span class="sxs-lookup"><span data-stu-id="b59dd-807">Pattern</span></span>

<span data-ttu-id="b59dd-808">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b59dd-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="b59dd-809">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-809">Six digits</span></span> 
    
- <span data-ttu-id="b59dd-810">하이픈</span><span class="sxs-lookup"><span data-stu-id="b59dd-810">A hyphen</span></span>
    
- <span data-ttu-id="b59dd-811">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b59dd-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b59dd-812">제외</span><span class="sxs-lookup"><span data-stu-id="b59dd-812">Checksum</span></span>

<span data-ttu-id="b59dd-813">아니요</span><span class="sxs-lookup"><span data-stu-id="b59dd-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="b59dd-814">정의</span><span class="sxs-lookup"><span data-stu-id="b59dd-814">Definition</span></span>

<span data-ttu-id="b59dd-815">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b59dd-816">정규식이 해당 `Regex_sweden_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b59dd-817">From `Keywords_sweden_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="b59dd-818">키워드</span><span class="sxs-lookup"><span data-stu-id="b59dd-818">Keywords</span></span>

<span data-ttu-id="b59dd-819">| |</span><span class="sxs-lookup"><span data-stu-id="b59dd-819"></span></span>
|<span data-ttu-id="b59dd-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="b59dd-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="b59dd-821">dl #</span><span class="sxs-lookup"><span data-stu-id="b59dd-821">dl#</span></span>  <br/> <span data-ttu-id="b59dd-822">driver license</span><span class="sxs-lookup"><span data-stu-id="b59dd-822">driver license</span></span>  <br/> <span data-ttu-id="b59dd-823">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-823">driver license number</span></span>  <br/> <span data-ttu-id="b59dd-824">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="b59dd-824">driver licence</span></span>  <br/> <span data-ttu-id="b59dd-825">drivers lic</span><span class="sxs-lookup"><span data-stu-id="b59dd-825">drivers lic.</span></span>  <br/> <span data-ttu-id="b59dd-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="b59dd-826">drivers license</span></span>  <br/> <span data-ttu-id="b59dd-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="b59dd-827">drivers licence</span></span>  <br/> <span data-ttu-id="b59dd-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="b59dd-828">driver's license</span></span>  <br/> <span data-ttu-id="b59dd-829">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-829">driver's license number</span></span>  <br/> <span data-ttu-id="b59dd-830">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-830">driver's licence number</span></span>  <br/> <span data-ttu-id="b59dd-831">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="b59dd-831">driving license number</span></span>  <br/> <span data-ttu-id="b59dd-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="b59dd-832">dlno#</span></span>  <br/> <span data-ttu-id="b59dd-833">körkort</span><span class="sxs-lookup"><span data-stu-id="b59dd-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="b59dd-834">영국의</span><span class="sxs-lookup"><span data-stu-id="b59dd-834">UK</span></span>

<span data-ttu-id="b59dd-835">자세한 내용은 영국 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="b59dd-835">For details, see the section "U.K.</span></span> <span data-ttu-id="b59dd-836">[중요 한 정보 유형에 서 확인 되는](what-the-sensitive-information-types-look-for.md)운전 면허 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b59dd-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b59dd-837">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b59dd-837">See also</span></span>

[<span data-ttu-id="b59dd-838">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="b59dd-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

