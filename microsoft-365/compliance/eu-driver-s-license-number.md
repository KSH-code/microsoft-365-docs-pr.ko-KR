---
title: EU 운전 면허 번호
f1.keywords:
- NOCSH
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
ms.openlocfilehash: c54fcefcda08d0bc2ec500d25c74bb5789e27398
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41592659"
---
# <a name="eu-drivers-license-number"></a><span data-ttu-id="7ad3d-104">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-104">EU Driver's License Number</span></span>

<span data-ttu-id="7ad3d-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 드라이버의 라이선스 번호 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Driver's License Number sensitive information type.</span></span> <span data-ttu-id="7ad3d-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="7ad3d-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-108">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-108">Format</span></span>

<span data-ttu-id="7ad3d-109">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-109">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-110">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-110">Pattern</span></span>

<span data-ttu-id="7ad3d-111">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-111">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-112">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-112">Checksum</span></span>

<span data-ttu-id="7ad3d-113">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-113">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-114">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-114">Definition</span></span>

<span data-ttu-id="7ad3d-115">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-115">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-116">정규식이 해당 `Regex_austria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-116">The regular expression  `Regex_austria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-117">From `Keywords_austria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-117">A keyword from  `Keywords_austria_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_austria_eu_driver's_license_number" />
          <Match idRef="Keywords_austria_eu_driver's_license_number" />
        </Pattern>
    </Entity>

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-118">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-118">Keywords</span></span>

<span data-ttu-id="7ad3d-119">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-119">| |</span></span>
|<span data-ttu-id="7ad3d-120">**Keywords_austria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-120">**Keywords_austria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-121">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-121">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-122">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-122">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-123">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-123">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-124">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-124">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-125">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-125">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-126">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-126">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-127">driver's licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-127">driver's licence</span></span>  <br/> <span data-ttu-id="7ad3d-128">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-128">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-129">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-129">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-130">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-130">driver's licence number</span></span>  <br/>  <span data-ttu-id="7ad3d-131">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-131">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-132">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-132">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-133">fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="7ad3d-133">fuhrerschein</span></span>  <br/> <span data-ttu-id="7ad3d-134">fuhrerschein republik osterreich</span><span class="sxs-lookup"><span data-stu-id="7ad3d-134">fuhrerschein republik osterreich</span></span>  <br/> |
   
## <a name="belgium"></a><span data-ttu-id="7ad3d-135">벨기에</span><span class="sxs-lookup"><span data-stu-id="7ad3d-135">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-136">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-136">Format</span></span>

<span data-ttu-id="7ad3d-137">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-137">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-138">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-138">Pattern</span></span>

<span data-ttu-id="7ad3d-139">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-139">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-140">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-140">Checksum</span></span>

<span data-ttu-id="7ad3d-141">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-141">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-142">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-142">Definition</span></span>

<span data-ttu-id="7ad3d-143">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-143">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-144">정규식이 해당 `Regex_belgium_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-144">The regular expression  `Regex_belgium_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-145">From `Keywords_belgium_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-145">A keyword from  `Keywords_belgium_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_driver's_license_number" />
          <Match idRef="Keywords_belgium_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-146">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-146">Keywords</span></span>

<span data-ttu-id="7ad3d-147">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-147">| |</span></span>
|<span data-ttu-id="7ad3d-148">**Keywords__belgium_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-148">**Keywords__belgium_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-149">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-149">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-150">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-150">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-151">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-151">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-152">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-152">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-153">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-153">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-154">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-154">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-155">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-155">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-156">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-156">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-157">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-157">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-158">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-158">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-159">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-159">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-160">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="7ad3d-160">rijbewijs</span></span>  <br/> <span data-ttu-id="7ad3d-161">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-161">rijbewijsnummer</span></span>  <br/> <span data-ttu-id="7ad3d-162">führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-162">führerscheinnummer</span></span>  <br/> <span data-ttu-id="7ad3d-163">fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-163">fuhrerscheinnummer</span></span>  <br/> <span data-ttu-id="7ad3d-164">fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-164">fuehrerscheinnummer</span></span>  <br/> <span data-ttu-id="7ad3d-165">führerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="7ad3d-165">führerschein- nr</span></span>  <br/> <span data-ttu-id="7ad3d-166">fuehrerschein-Veiligheid</span><span class="sxs-lookup"><span data-stu-id="7ad3d-166">fuehrerschein- Nr</span></span>  <br/> <span data-ttu-id="7ad3d-167">fuehrerschein-veiligheid</span><span class="sxs-lookup"><span data-stu-id="7ad3d-167">fuehrerschein- nr</span></span>  <br/> |
   
## <a name="bulgaria"></a><span data-ttu-id="7ad3d-168">불가리아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-168">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-169">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-169">Format</span></span>

<span data-ttu-id="7ad3d-170">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-170">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-171">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-171">Pattern</span></span>

<span data-ttu-id="7ad3d-172">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-172">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-173">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-173">Checksum</span></span>

<span data-ttu-id="7ad3d-174">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-174">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-175">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-175">Definition</span></span>

<span data-ttu-id="7ad3d-176">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-176">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-177">정규식이 해당 `Regex_bulgaria_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-177">The regular expression  `Regex_bulgaria_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-178">From `Keywords_bulgaria_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-178">A keyword from  `Keywords_bulgaria_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
             <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_bulgaria_eu_driver's_license_number" />
          <Match idRef="Keywords_bulgaria_eu_driver's_license_number" />
        </Pattern> 
</Entity>    

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-179">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-179">Keywords</span></span>

<span data-ttu-id="7ad3d-180">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-180">| |</span></span>
|<span data-ttu-id="7ad3d-181">**Keywords_bulgaria_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-181">**Keywords_bulgaria_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-182">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-182">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-183">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-183">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-184">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-184">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-185">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-185">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-186">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-186">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-187">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-187">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-188">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-188">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-189">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-189">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-190">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-190">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-191">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-191">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-192">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-192">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-193">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-193">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-194">свидетелство за управление на мпс</span><span class="sxs-lookup"><span data-stu-id="7ad3d-194">свидетелство за управление на мпс</span></span>  <br/> <span data-ttu-id="7ad3d-195">свидетелство за управление на моторно превозно средство</span><span class="sxs-lookup"><span data-stu-id="7ad3d-195">свидетелство за управление на моторно превозно средство</span></span>  <br/> <span data-ttu-id="7ad3d-196">сумпс</span><span class="sxs-lookup"><span data-stu-id="7ad3d-196">сумпс</span></span>  <br/> <span data-ttu-id="7ad3d-197">шофьорска книжка</span><span class="sxs-lookup"><span data-stu-id="7ad3d-197">шофьорска книжка</span></span>  <br/> |
   
## <a name="croatia"></a><span data-ttu-id="7ad3d-198">크로아티아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-198">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-199">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-199">Format</span></span>

<span data-ttu-id="7ad3d-200">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-200">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-201">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-201">Pattern</span></span>

<span data-ttu-id="7ad3d-202">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-202">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-203">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-203">Checksum</span></span>

<span data-ttu-id="7ad3d-204">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-204">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-205">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-205">Definition</span></span>

<span data-ttu-id="7ad3d-206">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-206">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-207">정규식이 해당 `Regex_croatia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-207">The regular expression  `Regex_croatia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-208">From `Keywords_croatia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-208">A keyword from  `Keywords_croatia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_croatia_eu_driver's_license_number" />
          <Match idRef="Keywords_croatia_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-209">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-209">Keywords</span></span>

<span data-ttu-id="7ad3d-210">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-210">| |</span></span>
|<span data-ttu-id="7ad3d-211">**Keywords_croatia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-211">**Keywords_croatia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-212">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-212">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-213">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-213">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-214">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-214">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-215">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-215">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-216">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-216">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-217">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-217">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-218">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-218">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-219">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-219">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-220">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-220">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-221">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-221">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-222">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-222">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-223">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-223">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-224">vozačka dozvola</span><span class="sxs-lookup"><span data-stu-id="7ad3d-224">vozačka dozvola</span></span>  <br/> |
   
## <a name="cyprus"></a><span data-ttu-id="7ad3d-225">키프로스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-225">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-226">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-226">Format</span></span>

<span data-ttu-id="7ad3d-227">공백과 구분 기호를 사용 하지 않고 12 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-227">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-228">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-228">Pattern</span></span>

<span data-ttu-id="7ad3d-229">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-229">12 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-230">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-230">Checksum</span></span>

<span data-ttu-id="7ad3d-231">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-231">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-232">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-232">Definition</span></span>

<span data-ttu-id="7ad3d-233">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-233">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-234">정규식이 해당 `Regex_cyprus_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-234">The regular expression  `Regex_cyprus_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-235">From `Keywords_cyprus_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-235">A keyword from  `Keywords_cyprus_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_cyprus_eu_driver's_license_number" />
          <Match idRef="Keywords_cyprus_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-236">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-236">Keywords</span></span>

<span data-ttu-id="7ad3d-237">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-237">| |</span></span>
|<span data-ttu-id="7ad3d-238">**Keywords_cyprus_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-238">**Keywords_cyprus_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-239">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-239">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-240">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-240">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-241">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-241">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-242">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-242">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-243">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-243">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-244">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-244">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-245">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-245">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-246">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-246">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-247">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-247">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-248">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-248">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-249">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-249">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-250">άδεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="7ad3d-250">άδεια οδήγησης</span></span>  <br/> |
   
## <a name="czech-republic"></a><span data-ttu-id="7ad3d-251">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="7ad3d-251">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-252">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-252">Format</span></span>

<span data-ttu-id="7ad3d-253">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-253">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-254">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-254">Pattern</span></span>

<span data-ttu-id="7ad3d-255">8 개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-255">Eight letters and digits:</span></span>
  
- <span data-ttu-id="7ad3d-256">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-256">Two letters (not case-sensitive)</span></span>
    
- <span data-ttu-id="7ad3d-257">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-257">A space (optional)</span></span>
    
- <span data-ttu-id="7ad3d-258">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-258">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-259">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-259">Checksum</span></span>

<span data-ttu-id="7ad3d-260">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-260">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-261">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-261">Definition</span></span>

<span data-ttu-id="7ad3d-262">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-262">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-263">정규식이 해당 `Regex_czech_republic_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-263">The regular expression  `Regex_czech_republic_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-264">From `Keywords_czech_republic_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-264">A keyword from  `Keywords_czech_republic_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_driver's_license_number" />
          <Match idRef="Keywords_czech_republic_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-265">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-265">Keywords</span></span>

<span data-ttu-id="7ad3d-266">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-266">| |</span></span>
|<span data-ttu-id="7ad3d-267">**Keywords_czech_republic_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-267">**Keywords_czech_republic_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-268">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-268">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-269">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-269">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-270">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-270">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-271">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-271">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-272">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-272">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-273">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-273">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-274">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-274">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-275">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-275">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-276">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-276">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-277">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-277">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-278">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-278">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-279">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-279">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-280">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-280">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-281">řidičský prúkaz</span><span class="sxs-lookup"><span data-stu-id="7ad3d-281">řidičský prúkaz</span></span>  <br/> |
   
## <a name="denmark"></a><span data-ttu-id="7ad3d-282">덴마크</span><span class="sxs-lookup"><span data-stu-id="7ad3d-282">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-283">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-283">Format</span></span>

<span data-ttu-id="7ad3d-284">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-284">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-285">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-285">Pattern</span></span>

<span data-ttu-id="7ad3d-286">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-286">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-287">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-287">Checksum</span></span>

<span data-ttu-id="7ad3d-288">예</span><span class="sxs-lookup"><span data-stu-id="7ad3d-288">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-289">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-289">Definition</span></span>

<span data-ttu-id="7ad3d-290">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-290">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-291">정규식이 해당 `Regex_denmark_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-291">The regular expression  `Regex_denmark_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-292">From `Keywords_denmark_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-292">A keyword from  `Keywords_denmark_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_denmark_eu_driver's_license_number" />
          <Match idRef="Keywords_denmark_eu_driver's_license_number" />
        </Pattern>
</Entity>

```

### <a name="keywords"></a><span data-ttu-id="7ad3d-293">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-293">Keywords</span></span>

<span data-ttu-id="7ad3d-294">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-294">| |</span></span>
|<span data-ttu-id="7ad3d-295">**Keywords_denmark_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-295">**Keywords_denmark_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-296">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-296">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-297">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-297">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-298">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-298">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-299">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-299">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-300">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-300">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-301">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-301">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-302">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-302">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-303">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-303">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-304">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-304">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-305">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-305">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-306">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-306">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-307">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-307">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-308">kørekort</span><span class="sxs-lookup"><span data-stu-id="7ad3d-308">kørekort</span></span>  <br/> <span data-ttu-id="7ad3d-309">kørekortnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-309">kørekortnummer</span></span>  <br/> |
   
## <a name="estonia"></a><span data-ttu-id="7ad3d-310">에스토니아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-310">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-311">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-311">Format</span></span>

<span data-ttu-id="7ad3d-312">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-312">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-313">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-313">Pattern</span></span>

<span data-ttu-id="7ad3d-314">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-314">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="7ad3d-315">문자 "ET" (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-315">The letters "ET" (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7ad3d-316">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-316">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-317">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-317">Checksum</span></span>

<span data-ttu-id="7ad3d-318">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-318">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-319">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-319">Definition</span></span>

<span data-ttu-id="7ad3d-320">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-320">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-321">정규식이 해당 `Regex_estonia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-321">The regular expression  `Regex_estonia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-322">From `Keywords_estonia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-322">A keyword from  `Keywords_estonia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_estonia_eu_driver's_license_number" />
          <Match idRef="Keywords_estonia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-323">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-323">Keywords</span></span>

<span data-ttu-id="7ad3d-324">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-324">| |</span></span>
|<span data-ttu-id="7ad3d-325">**Keywords_estonia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-325">**Keywords_estonia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-326">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-326">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-327">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-327">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-328">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-328">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-329">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-329">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-330">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-330">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-331">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-331">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-332">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-332">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-333">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-333">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-334">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-334">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-335">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-335">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-336">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-336">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-337">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-337">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-338">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="7ad3d-338">permis de conduire</span></span>  <br/> |
   
## <a name="finland"></a><span data-ttu-id="7ad3d-339">핀란드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-339">Finland</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-340">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-340">Format</span></span>

<span data-ttu-id="7ad3d-341">하이픈을 포함하는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-341">10 digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-342">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-342">Pattern</span></span>

<span data-ttu-id="7ad3d-343">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-343">10 digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="7ad3d-344">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-344">Six digits</span></span> 
    
- <span data-ttu-id="7ad3d-345">하이픈</span><span class="sxs-lookup"><span data-stu-id="7ad3d-345">A hyphen</span></span>
    
-  <span data-ttu-id="7ad3d-346">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-346">Four digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-347">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-347">Checksum</span></span>

<span data-ttu-id="7ad3d-348">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-348">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-349">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-349">Definition</span></span>

<span data-ttu-id="7ad3d-350">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-350">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-351">정규식이 해당 `Regex_finland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-351">The regular expression  `Regex_finland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-352">From `Keywords_finland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-352">A keyword from  `Keywords_finland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_finland_eu_driver's_license_number" />
          <Match idRef="Keywords_finland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-353">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-353">Keywords</span></span>

<span data-ttu-id="7ad3d-354">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-354">| |</span></span>
|<span data-ttu-id="7ad3d-355">**Keywords_finland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-355">**Keywords_finland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-356">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-356">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-357">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-357">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-358">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-358">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-359">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-359">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-360">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-360">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-361">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-361">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-362">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-362">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-363">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-363">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-364">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-364">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-365">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-365">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-366">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-366">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-367">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-367">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-368">ajokortti</span><span class="sxs-lookup"><span data-stu-id="7ad3d-368">ajokortti</span></span>  <br/> |
   
## <a name="france"></a><span data-ttu-id="7ad3d-369">프랑스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-369">France</span></span>

<span data-ttu-id="7ad3d-370">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"경기도 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-370">For details, see the section "France Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="7ad3d-371">독일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-371">Germany</span></span>

<span data-ttu-id="7ad3d-372">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일어 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-372">For details, see the section "German Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="7ad3d-373">그리스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-373">Greece</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-374">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-374">Format</span></span>

<span data-ttu-id="7ad3d-375">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-375">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-376">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-376">Pattern</span></span>

 <span data-ttu-id="7ad3d-377">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-377">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-378">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-378">Checksum</span></span>

<span data-ttu-id="7ad3d-379">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-379">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-380">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-380">Definition</span></span>

<span data-ttu-id="7ad3d-381">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-381">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-382">정규식이 해당 `Regex_greece_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-382">The regular expression  `Regex_greece_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-383">From `Keywords_greece_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-383">A keyword from  `Keywords_greece_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_driver's_license_number" />
          <Match idRef="Keywords_greece_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-384">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-384">Keywords</span></span>

<span data-ttu-id="7ad3d-385">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-385">| |</span></span>
|<span data-ttu-id="7ad3d-386">**Keywords_greece_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-386">**Keywords_greece_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-387">dlL #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-387">dlL#</span></span>  <br/> <span data-ttu-id="7ad3d-388">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-388">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-389">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-389">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-390">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-390">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-391">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-391">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-392">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-392">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-393">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-393">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-394">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-394">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-395">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-395">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-396">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-396">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-397">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-397">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-398">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-398">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-399">δεια οδήγησης</span><span class="sxs-lookup"><span data-stu-id="7ad3d-399">δεια οδήγησης</span></span>  <br/> <span data-ttu-id="7ad3d-400">Adeia odigisis</span><span class="sxs-lookup"><span data-stu-id="7ad3d-400">Adeia odigisis</span></span>  <br/> |
   
## <a name="hungary"></a><span data-ttu-id="7ad3d-401">헝가리</span><span class="sxs-lookup"><span data-stu-id="7ad3d-401">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-402">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-402">Format</span></span>

<span data-ttu-id="7ad3d-403">2 개의 문자 다음에 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-403">Two letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-404">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-404">Pattern</span></span>

<span data-ttu-id="7ad3d-405">2 개의 문자와 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-405">Two letters and six digits:</span></span>
  
-  <span data-ttu-id="7ad3d-406">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-406">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7ad3d-407">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-407">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-408">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-408">Checksum</span></span>

<span data-ttu-id="7ad3d-409">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-409">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-410">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-410">Definition</span></span>

<span data-ttu-id="7ad3d-411">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-411">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-412">정규식이 해당 `Regex_hungary_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-412">The regular expression  `Regex_hungary_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-413">From `Keywords_hungary_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-413">A keyword from  `Keywords_hungary_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_hungary_eu_driver's_license_number" />
          <Match idRef="Keywords_hungary_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-414">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-414">Keywords</span></span>

<span data-ttu-id="7ad3d-415">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-415">| |</span></span>
|<span data-ttu-id="7ad3d-416">**Keywords_hungary_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-416">**Keywords_hungary_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-417">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-417">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-418">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-418">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-419">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-419">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-420">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-420">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-421">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-421">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-422">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-422">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-423">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-423">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-424">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-424">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-425">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-425">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-426">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-426">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-427">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-427">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-428">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-428">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-429">vezetoi</span><span class="sxs-lookup"><span data-stu-id="7ad3d-429">vezetoi engedely</span></span>  <br/> |
   
## <a name="ireland"></a><span data-ttu-id="7ad3d-430">Ireland</span><span class="sxs-lookup"><span data-stu-id="7ad3d-430">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-431">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-431">Format</span></span>

<span data-ttu-id="7ad3d-432">6 자리 숫자와 4 개 문자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-432">Six digits followed by four letters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-433">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-433">Pattern</span></span>

<span data-ttu-id="7ad3d-434">6 자리 숫자와 4 개 문자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-434">Six digits and four letters:</span></span>
  
- <span data-ttu-id="7ad3d-435">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-435">Six digits</span></span>
    
- <span data-ttu-id="7ad3d-436">4 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-436">Four letters (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-437">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-437">Checksum</span></span>

<span data-ttu-id="7ad3d-438">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-438">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-439">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-439">Definition</span></span>

<span data-ttu-id="7ad3d-440">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-440">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-441">정규식이 해당 `Regex_ireland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-441">The regular expression  `Regex_ireland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-442">From `Keywords_ireland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-442">A keyword from  `Keywords_ireland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_ireland_eu_driver's_license_number" />
          <Match idRef="Keywords_ireland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-443">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-443">Keywords</span></span>

<span data-ttu-id="7ad3d-444">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-444">| |</span></span>
|<span data-ttu-id="7ad3d-445">**Keywords_ireland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-445">**Keywords_ireland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-446">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-446">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-447">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-447">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-448">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-448">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-449">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-449">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-450">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-450">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-451">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-451">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-452">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-452">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-453">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-453">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-454">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-454">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-455">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-455">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-456">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-456">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-457">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-457">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-458">ceadúnas tiomána</span><span class="sxs-lookup"><span data-stu-id="7ad3d-458">ceadúnas tiomána</span></span>  <br/> |
   
## <a name="italy"></a><span data-ttu-id="7ad3d-459">이탈리아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-459">Italy</span></span>

<span data-ttu-id="7ad3d-460">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"이탈리아 운전 면허 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-460">For details, see the section "Italy Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="latvia"></a><span data-ttu-id="7ad3d-461">라트비아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-461">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-462">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-462">Format</span></span>

<span data-ttu-id="7ad3d-463">3 개의 문자 및 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-463">Three letters followed by six digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-464">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-464">Pattern</span></span>

<span data-ttu-id="7ad3d-465">3 개의 문자 및 6 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-465">Three letters and six digits:</span></span>
  
-  <span data-ttu-id="7ad3d-466">3 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-466">Three letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7ad3d-467">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-467">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-468">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-468">Checksum</span></span>

<span data-ttu-id="7ad3d-469">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-469">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-470">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-470">Definition</span></span>

<span data-ttu-id="7ad3d-471">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-471">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-472">정규식이 해당 `Regex_latvia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-472">The regular expression  `Regex_latvia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-473">From `Keywords_latvia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-473">A keyword from  `Keywords_latvia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_latvia_eu_driver's_license_number" />
          <Match idRef="Keywords_latvia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-474">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-474">Keywords</span></span>

<span data-ttu-id="7ad3d-475">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-475">| |</span></span>
|<span data-ttu-id="7ad3d-476">**Keywords_latvia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-476">**Keywords_latvia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-477">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-477">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-478">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-478">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-479">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-479">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-480">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-480">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-481">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-481">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-482">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-482">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-483">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-483">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-484">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-484">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-485">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-485">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-486">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-486">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-487">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-487">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-488">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-488">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-489">autovadītāja apliecība</span><span class="sxs-lookup"><span data-stu-id="7ad3d-489">autovadītāja apliecība</span></span>  <br/> |
   
## <a name="lithuania"></a><span data-ttu-id="7ad3d-490">리투아니아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-490">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-491">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-491">Format</span></span>

<span data-ttu-id="7ad3d-492">공백과 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-492">Eight digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-493">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-493">Pattern</span></span>

 <span data-ttu-id="7ad3d-494">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-494">Eight digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-495">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-495">Checksum</span></span>

<span data-ttu-id="7ad3d-496">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-496">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-497">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-497">Definition</span></span>

<span data-ttu-id="7ad3d-498">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-498">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-499">정규식이 해당 `Regex_lithuania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-499">The regular expression  `Regex_lithuania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-500">From `Keywords_lithuania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-500">A keyword from  `Keywords_lithuania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_lithuania_eu_driver's_license_number" />
          <Match idRef="Keywords_lithuania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-501">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-501">Keywords</span></span>

<span data-ttu-id="7ad3d-502">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-502">| |</span></span>
|<span data-ttu-id="7ad3d-503">**Keywords_lithuania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-503">**Keywords_lithuania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-504">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-504">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-505">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-505">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-506">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-506">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-507">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-507">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-508">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-508">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-509">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-509">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-510">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-510">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-511">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-511">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-512">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-512">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-513">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-513">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-514">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-514">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-515">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-515">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-516">vairuotojo pažymėjimas</span><span class="sxs-lookup"><span data-stu-id="7ad3d-516">vairuotojo pažymėjimas</span></span>  <br/> |
   
## <a name="luxemburg"></a><span data-ttu-id="7ad3d-517">셈</span><span class="sxs-lookup"><span data-stu-id="7ad3d-517">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-518">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-518">Format</span></span>

<span data-ttu-id="7ad3d-519">공백과 구분 기호가 없는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-519">Six digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-520">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-520">Pattern</span></span>

 <span data-ttu-id="7ad3d-521">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-521">Six digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-522">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-522">Checksum</span></span>

<span data-ttu-id="7ad3d-523">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-523">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-524">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-524">Definition</span></span>

<span data-ttu-id="7ad3d-525">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-525">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-526">정규식이 해당 `Regex_luxemburg_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-526">The regular expression  `Regex_luxemburg_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-527">From `Keywords_luxemburg_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-527">A keyword from  `Keywords_luxemburg_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_luxemburg_eu_driver's_license_number" />
          <Match idRef="Keywords_luxemburg_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-528">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-528">Keywords</span></span>

<span data-ttu-id="7ad3d-529">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-529">| |</span></span>
|<span data-ttu-id="7ad3d-530">**Keywords_luxemburg_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-530">**Keywords_luxemburg_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-531">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-531">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-532">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-532">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-533">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-533">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-534">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-534">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-535">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-535">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-536">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-536">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-537">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-537">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-538">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-538">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-539">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-539">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-540">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-540">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-541">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-541">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-542">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-542">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-543">fahrerlaubnis</span><span class="sxs-lookup"><span data-stu-id="7ad3d-543">fahrerlaubnis</span></span>  <br/> |
   
## <a name="malta"></a><span data-ttu-id="7ad3d-544">몰타</span><span class="sxs-lookup"><span data-stu-id="7ad3d-544">Malta</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-545">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-545">Format</span></span>

<span data-ttu-id="7ad3d-546">지정 된 패턴에서 두 개의 문자와 6 자리 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="7ad3d-546">Combination of two characters and six digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-547">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-547">Pattern</span></span>

<span data-ttu-id="7ad3d-548">두 문자와 6 자리 숫자의 조합:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-548">Combination of two characters and six digits:</span></span>
  
- <span data-ttu-id="7ad3d-549">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-549">Two characters (digits or letters, not case-sensitive)</span></span>
    
- <span data-ttu-id="7ad3d-550">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-550">A space (optional)</span></span>
    
- <span data-ttu-id="7ad3d-551">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-551">Three digits</span></span>
    
- <span data-ttu-id="7ad3d-552">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-552">A space (optional)</span></span>
    
- <span data-ttu-id="7ad3d-553">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-553">Three digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-554">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-554">Checksum</span></span>

<span data-ttu-id="7ad3d-555">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-555">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-556">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-556">Definition</span></span>

<span data-ttu-id="7ad3d-557">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-558">정규식이 해당 `Regex_malta_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-558">The regular expression  `Regex_malta_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-559">From `Keywords_malta_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-559">A keyword from  `Keywords_malta_eu_driver's_license_number` is found.</span></span> 
    
```
<!-- EU Driver's License Number -->
 <Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_malta_eu_driver's_license_number" />
          <Match idRef="Keywords_malta_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-560">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-560">Keywords</span></span>

<span data-ttu-id="7ad3d-561">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-561">| |</span></span>
|<span data-ttu-id="7ad3d-562">**Keywords_malta_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-562">**Keywords_malta_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-563">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-563">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-564">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-564">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-565">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-565">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-566">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-566">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-567">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-567">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-568">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-568">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-569">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-569">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-570">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-570">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-571">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-571">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-572">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-572">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-573">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-573">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-574">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-574">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-575">liċenzja tas-sewqan</span><span class="sxs-lookup"><span data-stu-id="7ad3d-575">liċenzja tas-sewqan</span></span>  <br/> |
   
## <a name="netherlands"></a><span data-ttu-id="7ad3d-576">네덜란드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-576">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-577">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-577">Format</span></span>

<span data-ttu-id="7ad3d-578">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-578">10 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-579">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-579">Pattern</span></span>

<span data-ttu-id="7ad3d-580">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-580">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-581">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-581">Checksum</span></span>

<span data-ttu-id="7ad3d-582">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-582">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-583">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-583">Definition</span></span>

<span data-ttu-id="7ad3d-584">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-584">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-585">정규식이 해당 `Regex_netherlands_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-585">The regular expression  `Regex_netherlands_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-586">From `Keywords_netherlands_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-586">A keyword from  `Keywords_netherlands_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_netherlands_eu_driver's_license_number" />
          <Match idRef="Keywords_netherlands_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-587">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-587">Keywords</span></span>

<span data-ttu-id="7ad3d-588">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-588">| |</span></span>
|<span data-ttu-id="7ad3d-589">**Keywords_netherlands_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-589">**Keywords_netherlands_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-590">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-590">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-591">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-591">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-592">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-592">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-593">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-593">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-594">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-594">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-595">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-595">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-596">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-596">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-597">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-597">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-598">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-598">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-599">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-599">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-600">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-600">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-601">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-601">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-602">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="7ad3d-602">permis de conduire</span></span>  <br/> <span data-ttu-id="7ad3d-603">rijbewijs</span><span class="sxs-lookup"><span data-stu-id="7ad3d-603">rijbewijs</span></span>  <br/> <span data-ttu-id="7ad3d-604">rijbewijsnummer</span><span class="sxs-lookup"><span data-stu-id="7ad3d-604">rijbewijsnummer</span></span>  <br/> |
   
## <a name="poland"></a><span data-ttu-id="7ad3d-605">폴란드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-605">Poland</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-606">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-606">Format</span></span>

<span data-ttu-id="7ad3d-607">두 개의 슬래시를 포함 하는 14 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-607">14 digits containing 2 forward slashes</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-608">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-608">Pattern</span></span>

<span data-ttu-id="7ad3d-609">14 자리 숫자와 2 개의 슬래시:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-609">14 digits and 2 forward slashes:</span></span>
  
-  <span data-ttu-id="7ad3d-610">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-610">Five digits</span></span> 
    
- <span data-ttu-id="7ad3d-611">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="7ad3d-611">A forward slash</span></span>
    
- <span data-ttu-id="7ad3d-612">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-612">Two digits</span></span>
    
- <span data-ttu-id="7ad3d-613">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="7ad3d-613">A forward slash</span></span>
    
- <span data-ttu-id="7ad3d-614">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-614">Seven digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-615">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-615">Checksum</span></span>

<span data-ttu-id="7ad3d-616">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-616">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-617">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-617">Definition</span></span>

<span data-ttu-id="7ad3d-618">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-618">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-619">정규식이 해당 `Regex_poland_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-619">The regular expression  `Regex_poland_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-620">From `Keywords_poland_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-620">A keyword from  `Keywords_poland_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_poland_eu_driver's_license_number" />
          <Match idRef="Keywords_poland_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-621">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-621">Keywords</span></span>

<span data-ttu-id="7ad3d-622">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-622">| |</span></span>
|<span data-ttu-id="7ad3d-623">**Keywords_poland_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-623">**Keywords_poland_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-624">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-624">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-625">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-625">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-626">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-626">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-627">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-627">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-628">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-628">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-629">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-629">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-630">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-630">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-631">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-631">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-632">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-632">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-633">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-633">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-634">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-634">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-635">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-635">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-636">prawo jazdy</span><span class="sxs-lookup"><span data-stu-id="7ad3d-636">prawo jazdy</span></span>  <br/> |
   
## <a name="portugal"></a><span data-ttu-id="7ad3d-637">포르투갈</span><span class="sxs-lookup"><span data-stu-id="7ad3d-637">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-638">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-638">Format</span></span>

<span data-ttu-id="7ad3d-639">두 개의 문자와 지정 된 패턴에 있는 일곱 개의 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-639">Two letters followed by a seven numbers in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-640">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-640">Pattern</span></span>

<span data-ttu-id="7ad3d-641">두 문자 다음에 특수 문자를 사용한 7 개의 숫자를 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-641">Two letters followed by seven numbers with special characters:</span></span>
  
-  <span data-ttu-id="7ad3d-642">2 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-642">Two letters (not case-sensitive)</span></span> 
    
- <span data-ttu-id="7ad3d-643">하이픈</span><span class="sxs-lookup"><span data-stu-id="7ad3d-643">A hyphen</span></span>
    
- <span data-ttu-id="7ad3d-644">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-644">Six digits</span></span>
    
- <span data-ttu-id="7ad3d-645">공백</span><span class="sxs-lookup"><span data-stu-id="7ad3d-645">A space</span></span>
    
- <span data-ttu-id="7ad3d-646">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-646">One digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-647">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-647">Checksum</span></span>

<span data-ttu-id="7ad3d-648">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-648">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-649">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-649">Definition</span></span>

<span data-ttu-id="7ad3d-650">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-650">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-651">정규식이 해당 `Regex_portugal_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-651">The regular expression  `Regex_portugal_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-652">From `Keywords_portugal_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-652">A keyword from  `Keywords_portugal_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_portugal_eu_driver's_license_number" />
          <Match idRef="Keywords_portugal_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-653">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-653">Keywords</span></span>

<span data-ttu-id="7ad3d-654">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-654">| |</span></span>
|<span data-ttu-id="7ad3d-655">**Keywords_portugal_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-655">**Keywords_portugal_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-656">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-656">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-657">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-657">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-658">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-658">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-659">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-659">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-660">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-660">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-661">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-661">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-662">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-662">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-663">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-663">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-664">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-664">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-665">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-665">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-666">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-666">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-667">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-667">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-668">carteira de motorista</span><span class="sxs-lookup"><span data-stu-id="7ad3d-668">carteira de motorista</span></span>  <br/> |
   
## <a name="romania"></a><span data-ttu-id="7ad3d-669">루마니아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-669">Romania</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-670">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-670">Format</span></span>

<span data-ttu-id="7ad3d-671">한 문자 다음에 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-671">One character followed by eight digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-672">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-672">Pattern</span></span>

<span data-ttu-id="7ad3d-673">1 개의 문자 다음에 8 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-673">One character followed by eight digits:</span></span>
  
-  <span data-ttu-id="7ad3d-674">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-674">One letter (not case-sensitive) or digit</span></span> 
    
- <span data-ttu-id="7ad3d-675">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-675">Eight digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-676">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-676">Checksum</span></span>

<span data-ttu-id="7ad3d-677">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-677">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-678">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-678">Definition</span></span>

<span data-ttu-id="7ad3d-679">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-679">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-680">정규식이 해당 `Regex_romania_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-680">The regular expression  `Regex_romania_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-681">From `Keywords_romania_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-681">A keyword from  `Keywords_romania_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_driver's_license_number" />
          <Match idRef="Keywords_romania_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-682">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-682">Keywords</span></span>

<span data-ttu-id="7ad3d-683">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-683">| |</span></span>
|<span data-ttu-id="7ad3d-684">**Keywords_romania_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-684">**Keywords_romania_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-685">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-685">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-686">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-686">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-687">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-687">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-688">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-688">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-689">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-689">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-690">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-690">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-691">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-691">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-692">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-692">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-693">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-693">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-694">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-694">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-695">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-695">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-696">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-696">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-697">permis de conducere</span><span class="sxs-lookup"><span data-stu-id="7ad3d-697">permis de conducere</span></span>  <br/> |
   
## <a name="slovakia"></a><span data-ttu-id="7ad3d-698">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-698">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-699">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-699">Format</span></span>

<span data-ttu-id="7ad3d-700">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-700">One character followed by seven digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-701">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-701">Pattern</span></span>

<span data-ttu-id="7ad3d-702">한 문자 다음에 7 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-702">One character followed by seven digits</span></span>
  
- <span data-ttu-id="7ad3d-703">1 개 문자 (대/소문자 구분 안 함) 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-703">One letter (not case-sensitive) or digit</span></span>
    
-  <span data-ttu-id="7ad3d-704">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-704">Seven digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-705">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-705">Checksum</span></span>

<span data-ttu-id="7ad3d-706">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-706">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-707">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-707">Definition</span></span>

<span data-ttu-id="7ad3d-708">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-708">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-709">정규식이 해당 `Regex_slovakia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-709">The regular expression  `Regex_slovakia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-710">From `Keywords_slovakia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-710">A keyword from  `Keywords_slovakia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovaknia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovakia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-711">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-711">Keywords</span></span>

<span data-ttu-id="7ad3d-712">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-712">| |</span></span>
|<span data-ttu-id="7ad3d-713">**Keywords_slovakia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-713">**Keywords_slovakia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-714">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-714">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-715">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-715">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-716">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-716">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-717">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-717">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-718">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-718">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-719">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-719">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-720">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-720">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-721">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-721">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-722">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-722">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-723">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-723">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-724">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-724">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-725">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-725">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-726">vodičský preukaz</span><span class="sxs-lookup"><span data-stu-id="7ad3d-726">vodičský preukaz</span></span>  <br/> |
   
## <a name="slovenia"></a><span data-ttu-id="7ad3d-727">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="7ad3d-727">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-728">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-728">Format</span></span>

<span data-ttu-id="7ad3d-729">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-729">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-730">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-730">Pattern</span></span>

<span data-ttu-id="7ad3d-731">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-731">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="7ad3d-732">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-732">Checksum</span></span>

<span data-ttu-id="7ad3d-733">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-733">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-734">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-734">Definition</span></span>

<span data-ttu-id="7ad3d-735">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-735">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-736">정규식이 해당 `Regex_slovenia_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-736">The regular expression  `Regex_slovenia_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-737">From `Keywords_slovenia_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-737">A keyword from  `Keywords_slovenia_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovenia_eu_driver's_license_number" />
          <Match idRef="Keywords_slovenia_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-738">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-738">Keywords</span></span>

<span data-ttu-id="7ad3d-739">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-739">| |</span></span>
|<span data-ttu-id="7ad3d-740">**Keywords_slovenia_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-740">**Keywords_slovenia_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-741">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-741">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-742">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-742">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-743">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-743">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-744">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-744">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-745">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-745">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-746">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-746">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-747">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-747">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-748">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-748">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-749">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-749">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-750">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-750">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-751">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-751">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-752">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-752">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-753">vozniško dovoljenje</span><span class="sxs-lookup"><span data-stu-id="7ad3d-753">vozniško dovoljenje</span></span>  <br/> |
   
## <a name="spain"></a><span data-ttu-id="7ad3d-754">스페인</span><span class="sxs-lookup"><span data-stu-id="7ad3d-754">Spain</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-755">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-755">Format</span></span>

<span data-ttu-id="7ad3d-756">8 자리 숫자와 문자 1 개</span><span class="sxs-lookup"><span data-stu-id="7ad3d-756">Eight digits followed by one character</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-757">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-757">Pattern</span></span>

<span data-ttu-id="7ad3d-758">8 자리 숫자와 문자 1 개:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-758">Eight digits followed by one character:</span></span>
  
-  <span data-ttu-id="7ad3d-759">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-759">Eight digits</span></span> 
    
- <span data-ttu-id="7ad3d-760">1 자리 숫자 또는 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="7ad3d-760">One digit or letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-761">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-761">Checksum</span></span>

<span data-ttu-id="7ad3d-762">예</span><span class="sxs-lookup"><span data-stu-id="7ad3d-762">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-763">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-763">Definition</span></span>

<span data-ttu-id="7ad3d-764">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-764">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-765">이 함수 `Func_spain_eu_driver's_license_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-765">The function  `Func_spain_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-766">From `Keywords_spain_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-766">A keyword from  `Keywords_spain_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_driver's_license_number" />
          <Match idRef="Keywords_spain_eu_driver's_license_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-767">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-767">Keywords</span></span>

<span data-ttu-id="7ad3d-768">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-768">| |</span></span>
|<span data-ttu-id="7ad3d-769">**Keywords_spain_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-769">**Keywords_spain_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-770">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-770">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-771">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-771">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-772">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-772">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-773">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-773">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-774">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-774">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-775">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-775">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-776">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-776">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-777">driver's licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-777">driver's licence</span></span>  <br/> <span data-ttu-id="7ad3d-778">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-778">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-779">driving licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-779">driving licence</span></span>  <br/> <span data-ttu-id="7ad3d-780">driving license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-780">driving license</span></span>  <br/> <span data-ttu-id="7ad3d-781">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-781">driver licence number</span></span>  <br/> <span data-ttu-id="7ad3d-782">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-782">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-783">영향 요소 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-783">drivers licence number</span></span>  <br/> <span data-ttu-id="7ad3d-784">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-784">drivers license number</span></span>  <br/> <span data-ttu-id="7ad3d-785">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-785">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-786">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-786">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-787">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-787">driving licence number</span></span>  <br/> <span data-ttu-id="7ad3d-788">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-788">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-789">추진 허용</span><span class="sxs-lookup"><span data-stu-id="7ad3d-789">driving permit</span></span>  <br/> <span data-ttu-id="7ad3d-790">제어 허용 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-790">driving permit number</span></span>  <br/> <span data-ttu-id="7ad3d-791">permiso de conducción</span><span class="sxs-lookup"><span data-stu-id="7ad3d-791">permiso de conducción</span></span>  <br/> <span data-ttu-id="7ad3d-792">permiso conducción</span><span class="sxs-lookup"><span data-stu-id="7ad3d-792">permiso conducción</span></span>  <br/> <span data-ttu-id="7ad3d-793">número licencia conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-793">número licencia conducir</span></span>  <br/> <span data-ttu-id="7ad3d-794">número de 네트워크 de conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-794">número de carnet de conducir</span></span>  <br/> <span data-ttu-id="7ad3d-795">número carnet conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-795">número carnet conducir</span></span>  <br/> <span data-ttu-id="7ad3d-796">licencia conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-796">licencia conducir</span></span>  <br/> <span data-ttu-id="7ad3d-797">número de permiso de conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-797">número de permiso de conducir</span></span>  <br/> <span data-ttu-id="7ad3d-798">número de permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-798">número de permiso conducir</span></span>  <br/> <span data-ttu-id="7ad3d-799">número permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-799">número permiso conducir</span></span>  <br/> <span data-ttu-id="7ad3d-800">permiso conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-800">permiso conducir</span></span>  <br/> <span data-ttu-id="7ad3d-801">licencia de manejo</span><span class="sxs-lookup"><span data-stu-id="7ad3d-801">licencia de manejo</span></span>  <br/> <span data-ttu-id="7ad3d-802">el carnet de conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-802">el carnet de conducir</span></span>  <br/> <span data-ttu-id="7ad3d-803">carnet conducir</span><span class="sxs-lookup"><span data-stu-id="7ad3d-803">carnet conducir</span></span>  <br/> |
   
## <a name="sweden"></a><span data-ttu-id="7ad3d-804">스웨덴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-804">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="7ad3d-805">형식일</span><span class="sxs-lookup"><span data-stu-id="7ad3d-805">Format</span></span>

<span data-ttu-id="7ad3d-806">하이픈을 포함 하는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-806">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="7ad3d-807">패턴</span><span class="sxs-lookup"><span data-stu-id="7ad3d-807">Pattern</span></span>

<span data-ttu-id="7ad3d-808">하이픈을 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="7ad3d-808">Ten digits containing a hyphen:</span></span>
  
-  <span data-ttu-id="7ad3d-809">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-809">Six digits</span></span> 
    
- <span data-ttu-id="7ad3d-810">하이픈</span><span class="sxs-lookup"><span data-stu-id="7ad3d-810">A hyphen</span></span>
    
- <span data-ttu-id="7ad3d-811">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="7ad3d-811">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="7ad3d-812">제외</span><span class="sxs-lookup"><span data-stu-id="7ad3d-812">Checksum</span></span>

<span data-ttu-id="7ad3d-813">아니요</span><span class="sxs-lookup"><span data-stu-id="7ad3d-813">No</span></span>
  
### <a name="definition"></a><span data-ttu-id="7ad3d-814">정의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-814">Definition</span></span>

<span data-ttu-id="7ad3d-815">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-815">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="7ad3d-816">정규식이 해당 `Regex_sweden_eu_driver's_license_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-816">The regular expression  `Regex_sweden_eu_driver's_license_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="7ad3d-817">From `Keywords_sweden_eu_driver's_license_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-817">A keyword from  `Keywords_sweden_eu_driver's_license_number` is found.</span></span> 
    
```
 <!-- EU Driver's License Number -->
<Entity id="b8fe86d1-c056-453b-bfaa-9fe698699ecc" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_sweden_eu_driver's_license_number" />
          <Match idRef="Keywords_sweden_eu_driver's_license_number" />
        </Pattern>
</Entity> 
```

### <a name="keywords"></a><span data-ttu-id="7ad3d-818">키워드</span><span class="sxs-lookup"><span data-stu-id="7ad3d-818">Keywords</span></span>

<span data-ttu-id="7ad3d-819">| |</span><span class="sxs-lookup"><span data-stu-id="7ad3d-819">| |</span></span>
|<span data-ttu-id="7ad3d-820">**Keywords_sweden_eu_driver ' s_license_number**</span><span class="sxs-lookup"><span data-stu-id="7ad3d-820">**Keywords_sweden_eu_driver's_license_number**</span></span>|
|:-----|
|<span data-ttu-id="7ad3d-821">dl #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-821">dl#</span></span>  <br/> <span data-ttu-id="7ad3d-822">driver license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-822">driver license</span></span>  <br/> <span data-ttu-id="7ad3d-823">드라이버 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-823">driver license number</span></span>  <br/> <span data-ttu-id="7ad3d-824">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="7ad3d-824">driver licence</span></span>  <br/> <span data-ttu-id="7ad3d-825">drivers lic</span><span class="sxs-lookup"><span data-stu-id="7ad3d-825">drivers lic.</span></span>  <br/> <span data-ttu-id="7ad3d-826">drivers license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-826">drivers license</span></span>  <br/> <span data-ttu-id="7ad3d-827">drivers licence</span><span class="sxs-lookup"><span data-stu-id="7ad3d-827">drivers licence</span></span>  <br/> <span data-ttu-id="7ad3d-828">driver's license</span><span class="sxs-lookup"><span data-stu-id="7ad3d-828">driver's license</span></span>  <br/> <span data-ttu-id="7ad3d-829">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-829">driver's license number</span></span>  <br/> <span data-ttu-id="7ad3d-830">운전 라이선스 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-830">driver's licence number</span></span>  <br/> <span data-ttu-id="7ad3d-831">운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="7ad3d-831">driving license number</span></span>  <br/> <span data-ttu-id="7ad3d-832">dlno #</span><span class="sxs-lookup"><span data-stu-id="7ad3d-832">dlno#</span></span>  <br/> <span data-ttu-id="7ad3d-833">körkort</span><span class="sxs-lookup"><span data-stu-id="7ad3d-833">körkort</span></span>  <br/> |
   
## <a name="uk"></a><span data-ttu-id="7ad3d-834">영국의</span><span class="sxs-lookup"><span data-stu-id="7ad3d-834">UK</span></span>

<span data-ttu-id="7ad3d-835">자세한 내용은 영국 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-835">For details, see the section "U.K.</span></span> <span data-ttu-id="7ad3d-836">[중요 한 정보 유형에 서 확인 되는](what-the-sensitive-information-types-look-for.md)운전 면허 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="7ad3d-836">Driver's License Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="7ad3d-837">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7ad3d-837">See also</span></span>

[<span data-ttu-id="7ad3d-838">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="7ad3d-838">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

