---
title: EU 세금 확인 번호
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
description: 이 항목에서는 EU 세금 식별 번호 중요 정보 유형을 검색할 때 DLP (데이터 손실 방지) 정책이 어떤 역할을 검색 하나요를 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: 5467db921bd518eeeab18a36ee2de473f9017358
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41591019"
---
# <a name="eu-tax-identification-number"></a><span data-ttu-id="b3a27-104">EU 세금 확인 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-104">EU Tax Identification Number</span></span>

<span data-ttu-id="b3a27-105">이 항목에서는 언급 (데이터 손실 방지) 정책이 EU (유럽 세금 식별 번호) 중요 한 정보 유형을 검색할 때 찾는 항목을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Tax Identification Number (TIN) sensitive information type.</span></span> <span data-ttu-id="b3a27-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="b3a27-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="b3a27-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-108">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-108">Format</span></span>

<span data-ttu-id="b3a27-109">하이픈 및 슬래시가 있는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-109">Nine digits with optional hyphen and forward slash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-110">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-110">Pattern</span></span>

<span data-ttu-id="b3a27-111">하이픈 및 슬래시가 있는 9 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-111">Nine digits with optional hyphen and forward slash:</span></span>
  
-  <span data-ttu-id="b3a27-112">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-112">Two digits</span></span> 
    
- <span data-ttu-id="b3a27-113">하이픈 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b3a27-113">A hyphen (optional)</span></span>
    
- <span data-ttu-id="b3a27-114">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-114">Three digits</span></span>
    
- <span data-ttu-id="b3a27-115">정방향 슬래시 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b3a27-115">A forward slash (optional)</span></span>
    
- <span data-ttu-id="b3a27-116">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-116">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-117">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-117">Checksum</span></span>

<span data-ttu-id="b3a27-118">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-118">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-119">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-119">Definition</span></span>

<span data-ttu-id="b3a27-120">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-120">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-121">이 함수 `Func_austria_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-121">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-122">From `Keywords_austria_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-122">A keyword from  `Keywords_austria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-123">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-123">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-124">이 함수 `Func_austria_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-124">The function  `Func_austria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
          <Match idRef="Keywords_austria_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_austria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-125">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-125">Keywords</span></span>

#### <a name="keywords_austria_eu_tax_file_number"></a><span data-ttu-id="b3a27-126">Keywords_austria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-126">Keywords_austria_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-127">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-127">tax number</span></span>
  
<span data-ttu-id="b3a27-128">수</span><span class="sxs-lookup"><span data-stu-id="b3a27-128">number</span></span>
  
<span data-ttu-id="b3a27-129">세금 등록 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-129">tax registration number</span></span>
  
<span data-ttu-id="b3a27-130">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-130">tax id</span></span>
  
<span data-ttu-id="b3a27-131">st.nr</span><span class="sxs-lookup"><span data-stu-id="b3a27-131">st.nr.</span></span>
  
<span data-ttu-id="b3a27-132">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-132">steuernummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="b3a27-133">벨기에</span><span class="sxs-lookup"><span data-stu-id="b3a27-133">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-134">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-134">Format</span></span>

<span data-ttu-id="b3a27-135">공백과 구분 기호를 사용 하지 않고 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-135">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-136">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-136">Pattern</span></span>

<span data-ttu-id="b3a27-137">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-137">11 digits:</span></span>
  
- <span data-ttu-id="b3a27-138">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-138">Two digits</span></span>
    
- <span data-ttu-id="b3a27-139">"0" 또는 "1"</span><span class="sxs-lookup"><span data-stu-id="b3a27-139">A "0" or "1"</span></span>
    
- <span data-ttu-id="b3a27-140">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-140">One digit</span></span>
    
- <span data-ttu-id="b3a27-141">"0" 또는 "1" 또는 "2" 또는 "3"</span><span class="sxs-lookup"><span data-stu-id="b3a27-141">A "0" or "1" or "2" or "3"</span></span> 
    
- <span data-ttu-id="b3a27-142">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-142">Six digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-143">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-143">Checksum</span></span>

<span data-ttu-id="b3a27-144">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-144">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-145">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-145">Definition</span></span>

<span data-ttu-id="b3a27-146">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-146">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-147">정규식이 해당 `Regex_belgium_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-147">The regular expression  `Regex_belgium_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-148">From `Keywords_belgium_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-148">A keyword from  `Keywords_belgium_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_belgium_eu_tax_file_number" />
          <Match idRef="Keywords_belgium_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-149">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-149">Keywords</span></span>

#### <a name="keywords_belgium_eu_tax_file_number"></a><span data-ttu-id="b3a27-150">Keywords_belgium_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-150">Keywords_belgium_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-151">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-151">tax number</span></span>
  
<span data-ttu-id="b3a27-152">국가 등록 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-152">national registration number</span></span>
  
<span data-ttu-id="b3a27-153">세금 등록 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-153">tax registration number</span></span>
  
<span data-ttu-id="b3a27-154">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-154">tax id</span></span>
  
<span data-ttu-id="b3a27-155">m</span><span class="sxs-lookup"><span data-stu-id="b3a27-155">nif</span></span>
  
<span data-ttu-id="b3a27-156">m #</span><span class="sxs-lookup"><span data-stu-id="b3a27-156">nif#</span></span>
  
<span data-ttu-id="b3a27-157">numéro de registre 국립</span><span class="sxs-lookup"><span data-stu-id="b3a27-157">numéro de registre national</span></span>
  
<span data-ttu-id="b3a27-158">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b3a27-158">numéro d'identification fiscale</span></span>
  
## <a name="bulgaria"></a><span data-ttu-id="b3a27-159">불가리아</span><span class="sxs-lookup"><span data-stu-id="b3a27-159">Bulgaria</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-160">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-160">Format</span></span>

<span data-ttu-id="b3a27-161">공백과 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-161">Ten digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-162">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-162">Pattern</span></span>

<span data-ttu-id="b3a27-163">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-163">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-164">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-164">Checksum</span></span>

<span data-ttu-id="b3a27-165">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-165">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-166">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-166">Definition</span></span>

<span data-ttu-id="b3a27-167">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-167">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-168">이 함수 `Func_bulgaria_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-168">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-169">From `Keywords_bulgaria_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-169">A keyword from  `Keywords_bulgaria_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-170">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-170">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-171">이 함수 `Func_bulgaria_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-171">The function  `Func_bulgaria_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
          <Match idRef="Keywords_bulgaria_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_bulgaria_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-172">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-172">Keywords</span></span>

#### <a name="keywords_bulgaria_eu_tax_file_number"></a><span data-ttu-id="b3a27-173">Keywords_bulgaria_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-173">Keywords_bulgaria_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-174">고 대 cn</span><span class="sxs-lookup"><span data-stu-id="b3a27-174">bucn</span></span>
  
<span data-ttu-id="b3a27-175">일관적인 민사 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-175">uniform civil number</span></span>
  
<span data-ttu-id="b3a27-176">고 대 cn #</span><span class="sxs-lookup"><span data-stu-id="b3a27-176">bucn#</span></span>
  
<span data-ttu-id="b3a27-177">uniformcivilnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-177">uniformcivilnumber#</span></span>
  
<span data-ttu-id="b3a27-178">일정 한 민사 일련번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-178">uniform civil id</span></span>
  
<span data-ttu-id="b3a27-179">일관적인 민사</span><span class="sxs-lookup"><span data-stu-id="b3a27-179">uniform civil no</span></span>
  
<span data-ttu-id="b3a27-180">egn</span><span class="sxs-lookup"><span data-stu-id="b3a27-180">egn</span></span>
  
<span data-ttu-id="b3a27-181">불가리아어 (민사)</span><span class="sxs-lookup"><span data-stu-id="b3a27-181">bulgarian uniform civil number</span></span>
  
<span data-ttu-id="b3a27-182">uniformcivilno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-182">uniformcivilno#</span></span>
  
<span data-ttu-id="b3a27-183">egn #</span><span class="sxs-lookup"><span data-stu-id="b3a27-183">egn#</span></span>
  
<span data-ttu-id="b3a27-184">униформ граждански номер</span><span class="sxs-lookup"><span data-stu-id="b3a27-184">униформ граждански номер</span></span>
  
<span data-ttu-id="b3a27-185">униформ id</span><span class="sxs-lookup"><span data-stu-id="b3a27-185">униформ id</span></span>
  
<span data-ttu-id="b3a27-186">униформ граждански id</span><span class="sxs-lookup"><span data-stu-id="b3a27-186">униформ граждански id</span></span>
  
<span data-ttu-id="b3a27-187">униформ граждански не</span><span class="sxs-lookup"><span data-stu-id="b3a27-187">униформ граждански не</span></span>
  
## <a name="croatia"></a><span data-ttu-id="b3a27-188">크로아티아</span><span class="sxs-lookup"><span data-stu-id="b3a27-188">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-189">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-189">Format</span></span>

<span data-ttu-id="b3a27-190">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-190">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-191">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-191">Pattern</span></span>

<span data-ttu-id="b3a27-192">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-192">11 digits:</span></span>
  
- <span data-ttu-id="b3a27-193">임의로 선택한 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-193">Ten digits, randomly chosen</span></span>
    
- <span data-ttu-id="b3a27-194">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-194">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-195">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-195">Checksum</span></span>

<span data-ttu-id="b3a27-196">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-196">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-197">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-197">Definition</span></span>

<span data-ttu-id="b3a27-198">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-198">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-199">이 함수 `Func_croatia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-199">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-200">From `Keywords_croatia_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-200">A keyword from  `Keywords_croatia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-201">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-201">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-202">이 함수 `Func_croatia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-202">The function  `Func_croatia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
          <Match idRef="Keywords_croatia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-203">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-203">Keywords</span></span>

#### <a name="keywords_croatia_eu_tax_file_number"></a><span data-ttu-id="b3a27-204">Keywords_croatia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-204">Keywords_croatia_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-205">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-205">tax number</span></span>
  
<span data-ttu-id="b3a27-206">세금</span><span class="sxs-lookup"><span data-stu-id="b3a27-206">tax</span></span>
  
<span data-ttu-id="b3a27-207">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-207">tax id</span></span>
  
<span data-ttu-id="b3a27-208">원환형</span><span class="sxs-lookup"><span data-stu-id="b3a27-208">oid</span></span>
  
<span data-ttu-id="b3a27-209">원환형 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-209">oid#</span></span>
  
<span data-ttu-id="b3a27-210">porezni broj</span><span class="sxs-lookup"><span data-stu-id="b3a27-210">porezni broj</span></span>
  
## <a name="cyprus"></a><span data-ttu-id="b3a27-211">키프로스</span><span class="sxs-lookup"><span data-stu-id="b3a27-211">Cyprus</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-212">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-212">Format</span></span>

<span data-ttu-id="b3a27-213">지정 된 패턴에서 8 자리 및 1 개 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-213">Eight digits and one letter in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-214">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-214">Pattern</span></span>

<span data-ttu-id="b3a27-215">8 자리 숫자와 1 개 문자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-215">Eight digits and one letter:</span></span>
  
-  <span data-ttu-id="b3a27-216">"0"</span><span class="sxs-lookup"><span data-stu-id="b3a27-216">A "0"</span></span> 
    
- <span data-ttu-id="b3a27-217">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-217">Seven digits</span></span>
    
- <span data-ttu-id="b3a27-218">1 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b3a27-218">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-219">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-219">Checksum</span></span>

<span data-ttu-id="b3a27-220">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-220">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-221">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-221">Definition</span></span>

<span data-ttu-id="b3a27-222">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-222">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-223">이 함수 `Func_cyprus_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-223">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-224">From `Keywords_cyprus_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-224">A keyword from  `Keywords_cyprus_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-225">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-226">이 함수 `Func_cyprus_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-226">The function  `Func_cyprus_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
          <Match idRef="Keywords_cyprus_eu_tax_file_number" />
        </Pattern>
Pattern confidenceLevel="75">
          <IdMatch idRef="Func_cyprus_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-227">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-227">Keywords</span></span>

#### <a name="keywords_cyprus_eu_tax_file_number"></a><span data-ttu-id="b3a27-228">Keywords_cyprus_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-228">Keywords_cyprus_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-229">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-229">tax number</span></span>
  
<span data-ttu-id="b3a27-230">세금</span><span class="sxs-lookup"><span data-stu-id="b3a27-230">tax</span></span>
  
<span data-ttu-id="b3a27-231">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-231">tax id</span></span>
  
<span data-ttu-id="b3a27-232">세금 식별 코드</span><span class="sxs-lookup"><span data-stu-id="b3a27-232">tax identification code</span></span>
  
<span data-ttu-id="b3a27-233">tic</span><span class="sxs-lookup"><span data-stu-id="b3a27-233">tic</span></span>
  
<span data-ttu-id="b3a27-234">tic #</span><span class="sxs-lookup"><span data-stu-id="b3a27-234">tic#</span></span>
  
<span data-ttu-id="b3a27-235">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b3a27-235">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b3a27-236">φορολογική ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="b3a27-236">φορολογική ταυτότητα</span></span>
  
<span data-ttu-id="b3a27-237">κωδικός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b3a27-237">κωδικός φορολογικού μητρώου</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="b3a27-238">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="b3a27-238">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-239">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-239">Format</span></span>

<span data-ttu-id="b3a27-240">선택적 백슬래시가 있는 9 자리 또는 10 진수</span><span class="sxs-lookup"><span data-stu-id="b3a27-240">Nine or ten digits with an optional backslash</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-241">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-241">Pattern</span></span>

<span data-ttu-id="b3a27-242">선택적 backslashl이 있는 아홉 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-242">Nine or ten digits with an optional backslashl:</span></span>
  
- <span data-ttu-id="b3a27-243">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-243">Six digits</span></span> 
    
- <span data-ttu-id="b3a27-244">백슬래시 (선택 사항)</span><span class="sxs-lookup"><span data-stu-id="b3a27-244">A backslash (optional)</span></span>
    
- <span data-ttu-id="b3a27-245">3 ~ 4 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-245">Three or four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-246">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-246">Checksum</span></span>

<span data-ttu-id="b3a27-247">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-247">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-248">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-248">Definition</span></span>

<span data-ttu-id="b3a27-249">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-250">정규식이 해당 `Regex_czech_republic_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-250">The regular expression  `Regex_czech_republic_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-251">From `Keywords_czech_republic_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-251">A keyword from  `Keywords_czech_republic_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_czech_republic_eu_tax_file_number" />
          <Match idRef="Keywords_czech_republic_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-252">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-252">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_tax_file_number"></a><span data-ttu-id="b3a27-253">Keywords_czech_republic_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-253">Keywords_czech_republic_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-254">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-254">tax number</span></span>
  
<span data-ttu-id="b3a27-255">세금</span><span class="sxs-lookup"><span data-stu-id="b3a27-255">tax</span></span>
  
<span data-ttu-id="b3a27-256">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-256">tax id</span></span>
  
<span data-ttu-id="b3a27-257">개인 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-257">personal number</span></span>
  
<span data-ttu-id="b3a27-258">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b3a27-258">daňové číslo</span></span>
  
<span data-ttu-id="b3a27-259">osobní číslo</span><span class="sxs-lookup"><span data-stu-id="b3a27-259">osobní číslo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="b3a27-260">덴마크</span><span class="sxs-lookup"><span data-stu-id="b3a27-260">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-261">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-261">Format</span></span>

<span data-ttu-id="b3a27-262">하이픈을 포함 하는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-262">Ten digits containing a hyphen</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-263">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-263">Pattern</span></span>

<span data-ttu-id="b3a27-264">Hyphenl를 포함 하는 10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-264">Ten digits containing a hyphenl:</span></span>
  
-  <span data-ttu-id="b3a27-265">생년월일에 해당 하는 6 자리 숫자 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="b3a27-265">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="b3a27-266">하이픈</span><span class="sxs-lookup"><span data-stu-id="b3a27-266">A hyphen</span></span>
    
- <span data-ttu-id="b3a27-267">첫 번째 숫자가 출생 세기에 해당 하 고 마지막 숫자가 개별 성별에 해당 하는 시퀀스 번호에 해당 하는 4 자리 숫자 (남성의 경우 홀수 및 암에도 해당)</span><span class="sxs-lookup"><span data-stu-id="b3a27-267">Four digits that correspond to a sequence number where the first digit corresponds to the century of birth and the last digit corresponds to the individual's gender (odd for male and even for female)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-268">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-268">Checksum</span></span>

<span data-ttu-id="b3a27-269">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-269">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-270">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-270">Definition</span></span>

<span data-ttu-id="b3a27-271">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-271">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-272">이 함수 `Func_denmark_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-272">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-273">From `Keywords_denmark_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-273">A keyword from  `Keywords_denmark_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-274">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-274">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-275">이 함수 `Func_denmark_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-275">The function  `Func_denmark_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
          <Match idRef="Keywords_denmark_eu_tax_file_number" />
        </Pattern> 
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-276">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-276">Keywords</span></span>

#### <a name="keywords_denmark_eu_tax_file_number"></a><span data-ttu-id="b3a27-277">Keywords_denmark_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-277">Keywords_denmark_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-278">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-278">tax number</span></span>
  
<span data-ttu-id="b3a27-279">세금</span><span class="sxs-lookup"><span data-stu-id="b3a27-279">tax</span></span>
  
<span data-ttu-id="b3a27-280">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-280">tax id</span></span>
  
<span data-ttu-id="b3a27-281">cpr 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-281">cpr number</span></span>
  
<span data-ttu-id="b3a27-282">cpr #</span><span class="sxs-lookup"><span data-stu-id="b3a27-282">cpr#</span></span>
  
<span data-ttu-id="b3a27-283">nummer에서</span><span class="sxs-lookup"><span data-stu-id="b3a27-283">skat nummer</span></span>
  
<span data-ttu-id="b3a27-284">번호 (|)</span><span class="sxs-lookup"><span data-stu-id="b3a27-284">skat id</span></span>
  
## <a name="estonia"></a><span data-ttu-id="b3a27-285">에스토니아</span><span class="sxs-lookup"><span data-stu-id="b3a27-285">Estonia</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-286">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-286">Format</span></span>

<span data-ttu-id="b3a27-287">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-287">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-288">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-288">Pattern</span></span>

<span data-ttu-id="b3a27-289">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-289">11 digits:</span></span>
  
-  <span data-ttu-id="b3a27-290">성별에 해당 하는 숫자와 홀수로 해당 하 고, 홀수를 지정 하 여 19th 세기에 대해 1, 2를 나타내는 숫자입니다. 3, 20th 세기에 대해 4를 적용 합니다. 21 세기에 대해 5, 6</span><span class="sxs-lookup"><span data-stu-id="b3a27-290">One digit that corresponds to gender and century of birth where an odd number indicates male and the even number indicates female as follows: 1, 2 for the 19th century; 3, 4 for the 20th century; and 5, 6 for the 21st century</span></span> 
    
- <span data-ttu-id="b3a27-291">생년월일에 해당 하는 6 자리 숫자 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="b3a27-291">Six digits that correspond to birth date (YYMMDD)</span></span>
    
- <span data-ttu-id="b3a27-292">같은 날짜에 태어난 사람을 구분 하는 일련 번호에 해당 하는 3 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-292">Three digits that correspond to a serial number separating persons born on the same date</span></span>
    
- <span data-ttu-id="b3a27-293">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-293">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-294">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-294">Checksum</span></span>

<span data-ttu-id="b3a27-295">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-295">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-296">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-296">Definition</span></span>

<span data-ttu-id="b3a27-297">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-297">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-298">이 함수 `Func_estonia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-298">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-299">From `Keywords_estonia_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-299">A keyword from  `Keywords_estonia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-300">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-300">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-301">이 함수 `Func_estonia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-301">The function  `Func_estonia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
          <Match idRef="Keywords_estonia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_estonia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-302">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-302">Keywords</span></span>

#### <a name="keywords_estonia_eu_tax_file_number"></a><span data-ttu-id="b3a27-303">Keywords_estonia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-303">Keywords_estonia_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-304">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-304">tax number</span></span>
  
<span data-ttu-id="b3a27-305">세금</span><span class="sxs-lookup"><span data-stu-id="b3a27-305">tax</span></span>
  
<span data-ttu-id="b3a27-306">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-306">tax id</span></span>
  
<span data-ttu-id="b3a27-307">개인 코드</span><span class="sxs-lookup"><span data-stu-id="b3a27-307">personal code</span></span>
  
<span data-ttu-id="b3a27-308">maksunumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-308">maksunumber</span></span>
  
<span data-ttu-id="b3a27-309">maksu id</span><span class="sxs-lookup"><span data-stu-id="b3a27-309">maksu id</span></span>
  
<span data-ttu-id="b3a27-310">isikukood</span><span class="sxs-lookup"><span data-stu-id="b3a27-310">isikukood</span></span>
  
## <a name="finland"></a><span data-ttu-id="b3a27-311">핀란드</span><span class="sxs-lookup"><span data-stu-id="b3a27-311">Finland</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-312">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-312">Format</span></span>

<span data-ttu-id="b3a27-313">숫자, 문자, 더하기 및 빼기 기호를 11 문자로 조합</span><span class="sxs-lookup"><span data-stu-id="b3a27-313">An 11-character combination of digits, letters, and plus and minus sign</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-314">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-314">Pattern</span></span>

<span data-ttu-id="b3a27-315">숫자, 문자, 더하기 및 빼기 기호를 11 문자로 조합한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-315">An 11-character combination of digits, letters, and plus and minus sign:</span></span>
  
- <span data-ttu-id="b3a27-316">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-316">Six digits</span></span>
    
- <span data-ttu-id="b3a27-317">더하기 기호, 빼기 기호 또는 + 기호가 1800-1899 사이에 태어난 것을 의미 하는 "A" (대/소문자 구분 안 함), 빼기 기호는 1900-1999 사이에 출생를 의미 하며 "A"는 "A"를 2000 의미 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-317">One of the following: a plus sign, a minus sign, or the letter "A" (not case sensitive) where the plus sign means born between 1800-1899, the minus sign means born between 1900-1999, and "A" means born 2000 and after</span></span>
    
- <span data-ttu-id="b3a27-318">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-318">Three digits</span></span>
    
- <span data-ttu-id="b3a27-319">1 개의 문자 또는 한 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-319">One letter or one number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-320">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-320">Checksum</span></span>

<span data-ttu-id="b3a27-321">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-321">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-322">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-322">Definition</span></span>

<span data-ttu-id="b3a27-323">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-323">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-324">이 함수 `Func_finland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-324">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-325">From `Keywords_finland_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-325">A keyword from  `Keywords_finland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-326">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-326">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-327">이 함수 `Func_finland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-327">The function  `Func_finland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
          <Match idRef="Keywords_finland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-328">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-328">Keywords</span></span>

#### <a name="keywords_finland_eu_tax_file_number"></a><span data-ttu-id="b3a27-329">Keywords_finland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-329">Keywords_finland_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-330">identification number</span><span class="sxs-lookup"><span data-stu-id="b3a27-330">identification number</span></span>
  
<span data-ttu-id="b3a27-331">개인 id</span><span class="sxs-lookup"><span data-stu-id="b3a27-331">personal id</span></span>
  
<span data-ttu-id="b3a27-332">id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-332">identity number</span></span>
  
<span data-ttu-id="b3a27-333">핀란드어 국가 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-333">finnish national id number</span></span>
  
<span data-ttu-id="b3a27-334">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-334">personalidnumber#</span></span>
  
<span data-ttu-id="b3a27-335">national identification number</span><span class="sxs-lookup"><span data-stu-id="b3a27-335">national identification number</span></span>
  
<span data-ttu-id="b3a27-336">id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-336">id number</span></span>
  
<span data-ttu-id="b3a27-337">국가 id 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-337">national id no.</span></span>
  
<span data-ttu-id="b3a27-338">국가 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-338">national id number</span></span>
  
<span data-ttu-id="b3a27-339">id 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-339">id no</span></span>
  
<span data-ttu-id="b3a27-340">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b3a27-340">tunnistenumero</span></span>
  
<span data-ttu-id="b3a27-341">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b3a27-341">henkilötunnus</span></span>
  
<span data-ttu-id="b3a27-342">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b3a27-342">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="b3a27-343">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="b3a27-343">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="b3a27-344">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="b3a27-344">identiteetti numero</span></span>
  
<span data-ttu-id="b3a27-345">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="b3a27-345">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="b3a27-346">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="b3a27-346">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="b3a27-347">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="b3a27-347">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="b3a27-348">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="b3a27-348">tunnusnumero</span></span>
  
<span data-ttu-id="b3a27-349">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="b3a27-349">kansallinen tunnus numero</span></span>
  
## <a name="france"></a><span data-ttu-id="b3a27-350">프랑스</span><span class="sxs-lookup"><span data-stu-id="b3a27-350">France</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-351">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-351">Format</span></span>

<span data-ttu-id="b3a27-352">개별 사용자의 경우 13 자리 숫자 및 엔터티의 경우 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-352">13 digits for individuals and nine digits for entities</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-353">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-353">Pattern</span></span>

<span data-ttu-id="b3a27-354">개별 사용자에 대 한 13 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-354">13 digits for individuals:</span></span>
  
- <span data-ttu-id="b3a27-355">0, 1, 2 또는 3 이어야 하는 1 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-355">One digit that must be 0, 1, 2, or 3</span></span>
    
- <span data-ttu-id="b3a27-356">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-356">12 digits</span></span>
    
<span data-ttu-id="b3a27-357">엔터티의 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-357">Nine digits for entities</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-358">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-358">Checksum</span></span>

<span data-ttu-id="b3a27-359">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-359">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-360">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-360">Definition</span></span>

<span data-ttu-id="b3a27-361">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-361">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-362">이 함수 `Func_france_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-362">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-363">From `Keywords_france_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-363">A keyword from  `Keywords_france_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-364">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-365">이 함수 `Func_france_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-365">The function  `Func_france_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
          <Match idRef="Keywords_france_eu_tax_file_number" />
        </Pattern>
 <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_france_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-366">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-366">Keywords</span></span>

#### <a name="keywords_france_eu_tax_file_number"></a><span data-ttu-id="b3a27-367">Keywords_france_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-367">Keywords_france_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-368">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-368">tax identification number</span></span>
  
<span data-ttu-id="b3a27-369">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-369">tax number</span></span>
  
<span data-ttu-id="b3a27-370">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-370">tax id</span></span>
  
<span data-ttu-id="b3a27-371">numéro d'identification fiscale</span><span class="sxs-lookup"><span data-stu-id="b3a27-371">numéro d'identification fiscale</span></span>
  
## <a name="germany"></a><span data-ttu-id="b3a27-372">독일</span><span class="sxs-lookup"><span data-stu-id="b3a27-372">Germany</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-373">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-373">Format</span></span>

<span data-ttu-id="b3a27-374">공백과 구분 기호를 사용 하지 않고 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-374">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-375">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-375">Pattern</span></span>

<span data-ttu-id="b3a27-376">11 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-376">11 digits :</span></span>
  
-  <span data-ttu-id="b3a27-377">10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-377">Ten digits</span></span> 
    
- <span data-ttu-id="b3a27-378">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-378">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-379">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-379">Checksum</span></span>

<span data-ttu-id="b3a27-380">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-380">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-381">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-381">Definition</span></span>

<span data-ttu-id="b3a27-382">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-382">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-383">이 함수 `Func_germany_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-383">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-384">From `Keywords_germany_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-384">A keyword from  `Keywords_germany_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-385">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-385">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-386">이 함수 `Func_germany_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-386">The function  `Func_germany_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
          <Match idRef="Keywords_germany_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_germany_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-387">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-387">Keywords</span></span>

#### <a name="keywords_germany_eu_tax_file_number"></a><span data-ttu-id="b3a27-388">Keywords_germany_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-388">Keywords_germany_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-389">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-389">tax number</span></span>
  
<span data-ttu-id="b3a27-390">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-390">tax no.</span></span>
  
<span data-ttu-id="b3a27-391">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-391">taxno#</span></span>
  
<span data-ttu-id="b3a27-392">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-392">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-393">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-393">taxnumber</span></span>
  
<span data-ttu-id="b3a27-394">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-394">tax id</span></span>
  
<span data-ttu-id="b3a27-395">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-395">taxid#</span></span>
  
<span data-ttu-id="b3a27-396">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-396">tax identification number</span></span>
  
<span data-ttu-id="b3a27-397">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-397">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-398">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-398">steuernummer</span></span>
  
<span data-ttu-id="b3a27-399">steuer id</span><span class="sxs-lookup"><span data-stu-id="b3a27-399">steuer id</span></span>
  
<span data-ttu-id="b3a27-400">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-400">steueridentifikationsnummer</span></span>
  
## <a name="greece"></a><span data-ttu-id="b3a27-401">그리스</span><span class="sxs-lookup"><span data-stu-id="b3a27-401">Greece</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-402">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-402">Format</span></span>

<span data-ttu-id="b3a27-403">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-403">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-404">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-404">Pattern</span></span>

<span data-ttu-id="b3a27-405">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-405">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-406">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-406">Checksum</span></span>

<span data-ttu-id="b3a27-407">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-407">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-408">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-408">Definition</span></span>

<span data-ttu-id="b3a27-409">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-409">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-410">정규식이 해당 `Regex_greece_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-410">The regular expression  `Regex_greece_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-411">From `Keywords_greece_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-411">A keyword from  `Keywords_greece_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_greece_eu_tax_file_number" />
          <Match idRef="Keywords_greece_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-412">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-412">Keywords</span></span>

#### <a name="keywords_greece_eu_tax_file_number"></a><span data-ttu-id="b3a27-413">Keywords_greece_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-413">Keywords_greece_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-414">afm</span><span class="sxs-lookup"><span data-stu-id="b3a27-414">afm</span></span>
  
<span data-ttu-id="b3a27-415">언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-415">tin</span></span>
  
<span data-ttu-id="b3a27-416">세금 번호 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-416">tax id no.</span></span>
  
<span data-ttu-id="b3a27-417">세금 번호 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-417">tax id no</span></span>
  
<span data-ttu-id="b3a27-418">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-418">tax identification number</span></span>
  
<span data-ttu-id="b3a27-419">세금 레지스트리 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-419">tax registry number</span></span>
  
<span data-ttu-id="b3a27-420">세금 레지스트리 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-420">tax registry no.</span></span>
  
<span data-ttu-id="b3a27-421">afm #</span><span class="sxs-lookup"><span data-stu-id="b3a27-421">afm#</span></span>
  
<span data-ttu-id="b3a27-422">언급 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-422">tin#</span></span>
  
<span data-ttu-id="b3a27-423">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-423">taxidno#</span></span>
  
<span data-ttu-id="b3a27-424">taxregistryno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-424">taxregistryno#</span></span>
  
<span data-ttu-id="b3a27-425">αριθμός φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b3a27-425">αριθμός φορολογικού μητρώου</span></span>
  
<span data-ttu-id="b3a27-426">aφμ</span><span class="sxs-lookup"><span data-stu-id="b3a27-426">aφμ</span></span>
  
<span data-ttu-id="b3a27-427">aφμ αριθμός</span><span class="sxs-lookup"><span data-stu-id="b3a27-427">aφμ αριθμός</span></span>
  
<span data-ttu-id="b3a27-428">φορολογικού μητρώου νο.</span><span class="sxs-lookup"><span data-stu-id="b3a27-428">φορολογικού μητρώου νο.</span></span>
  
<span data-ttu-id="b3a27-429">τον αριθμό φορολογικού μητρώου</span><span class="sxs-lookup"><span data-stu-id="b3a27-429">τον αριθμό φορολογικού μητρώου</span></span>
  
## <a name="hungary"></a><span data-ttu-id="b3a27-430">헝가리</span><span class="sxs-lookup"><span data-stu-id="b3a27-430">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-431">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-431">Format</span></span>

<span data-ttu-id="b3a27-432">공백이 나 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-432">Ten digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-433">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-433">Pattern</span></span>

<span data-ttu-id="b3a27-434">10 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-434">Ten digits:</span></span>
  
-  <span data-ttu-id="b3a27-435">"8" 이어야 하는 1 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-435">One digit that must be "8"</span></span> 
    
- <span data-ttu-id="b3a27-436">날짜 01/01/1867과 개별 생년월일 사이의 일 수에 해당 하는 5 자리 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-436">Five digits that correspond to the number of days between the date 01/01/1867 and the date of the birth of the individual</span></span>
    
- <span data-ttu-id="b3a27-437">같은 날에 태어난 사람을 구별 하기 위해 기회가 만든 번호에 해당 하는 3 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-437">Three digits that correspond to the number generated by chance to differentiate individuals born on the same day</span></span>
    
- <span data-ttu-id="b3a27-438">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-438">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-439">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-439">Checksum</span></span>

<span data-ttu-id="b3a27-440">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-440">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-441">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-441">Definition</span></span>

<span data-ttu-id="b3a27-442">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-442">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-443">이 함수 `Func_hungary_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-443">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-444">From `Keywords_hungary_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-444">A keyword from  `Keywords_hungary_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-445">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-445">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-446">이 함수 `Func_hungary_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-446">The function  `Func_hungary_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
          <Match idRef="Keywords_hungary_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-447">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-447">Keywords</span></span>

#### <a name="keywords_hungary_eu_tax_file_number"></a><span data-ttu-id="b3a27-448">Keywords_hungary_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-448">Keywords_hungary_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-449">헝가리어 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-449">hungarian tax identification number</span></span>
  
<span data-ttu-id="b3a27-450">헝가리어 언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-450">hungarian tin</span></span>
  
<span data-ttu-id="b3a27-451">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-451">tax id number</span></span>
  
<span data-ttu-id="b3a27-452">vat 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-452">vat number</span></span>
  
<span data-ttu-id="b3a27-453">세금 기관 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-453">tax authority no</span></span>
  
<span data-ttu-id="b3a27-454">세금 id 세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-454">tax id tax identity number</span></span>
  
<span data-ttu-id="b3a27-455">taxidnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-455">taxidnumber#</span></span>
  
<span data-ttu-id="b3a27-456">언급 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-456">tin#</span></span>
  
<span data-ttu-id="b3a27-457">hungatiantin #</span><span class="sxs-lookup"><span data-stu-id="b3a27-457">hungatiantin#</span></span>
  
<span data-ttu-id="b3a27-458">세금 식별 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-458">tax identification no</span></span>
  
<span data-ttu-id="b3a27-459">taxidno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-459">taxidno#</span></span>
  
<span data-ttu-id="b3a27-460">adóazonosító szám</span><span class="sxs-lookup"><span data-stu-id="b3a27-460">adóazonosító szám</span></span>
  
<span data-ttu-id="b3a27-461">adószám</span><span class="sxs-lookup"><span data-stu-id="b3a27-461">adószám</span></span>
  
<span data-ttu-id="b3a27-462">adóhatóság szám</span><span class="sxs-lookup"><span data-stu-id="b3a27-462">adóhatóság szám</span></span>
  
## <a name="ireland"></a><span data-ttu-id="b3a27-463">Ireland</span><span class="sxs-lookup"><span data-stu-id="b3a27-463">Ireland</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-464">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-464">Format</span></span>

<span data-ttu-id="b3a27-465">공백 또는 구분 기호가 없는 7 자리 숫자와 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-465">Seven digits followed by a letter with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-466">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-466">Pattern</span></span>

<span data-ttu-id="b3a27-467">7 자리 숫자와 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-467">Seven digits followed by a letter:</span></span>
  
-  <span data-ttu-id="b3a27-468">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-468">Seven digits</span></span> 
    
- <span data-ttu-id="b3a27-469">1 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b3a27-469">One letter (not case-sensitive)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-470">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-470">Checksum</span></span>

<span data-ttu-id="b3a27-471">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-471">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-472">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-472">Definition</span></span>

<span data-ttu-id="b3a27-473">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-474">이 함수 `Func_ireland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-474">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-475">From `Keywords_ireland_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-475">A keyword from  `Keywords_ireland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-476">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-476">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-477">이 함수 `Func_ireland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-477">The function  `Func_ireland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
          <Match idRef="Keywords_ireland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_ireland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-478">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-478">Keywords</span></span>

#### <a name="keywords_ireland_eu_tax_file_number"></a><span data-ttu-id="b3a27-479">Keywords_ireland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-479">Keywords_ireland_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-480">공용 서비스 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-480">public service no</span></span>
  
<span data-ttu-id="b3a27-481">개인 공용 서비스 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-481">personal public service no</span></span>
  
<span data-ttu-id="b3a27-482">pps 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-482">pps no</span></span>
  
<span data-ttu-id="b3a27-483">개인 서비스 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-483">personal service no</span></span>
  
<span data-ttu-id="b3a27-484">pps 서비스 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-484">pps service no</span></span>
  
<span data-ttu-id="b3a27-485">ppsno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-485">ppsno#</span></span>
  
<span data-ttu-id="b3a27-486">아일랜드 pps 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-486">irish pps no</span></span>
  
<span data-ttu-id="b3a27-487">publicserviceno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-487">publicserviceno#</span></span>
  
<span data-ttu-id="b3a27-488">개인 공용 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-488">personal public service number</span></span>
  
<span data-ttu-id="b3a27-489">uimhir phearsanta seirbhíse poiblí</span><span class="sxs-lookup"><span data-stu-id="b3a27-489">uimhir phearsanta seirbhíse poiblí</span></span>
  
<span data-ttu-id="b3a27-490">pps uimh</span><span class="sxs-lookup"><span data-stu-id="b3a27-490">pps uimh</span></span>
  
<span data-ttu-id="b3a27-491">uimhir aitheantais phearsanta</span><span class="sxs-lookup"><span data-stu-id="b3a27-491">uimhir aitheantais phearsanta</span></span>
  
## <a name="italy"></a><span data-ttu-id="b3a27-492">이탈리아</span><span class="sxs-lookup"><span data-stu-id="b3a27-492">Italy</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-493">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-493">Format</span></span>

<span data-ttu-id="b3a27-494">지정 된 패턴의 문자와 숫자 16 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-494">16 letters and digits in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-495">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-495">Pattern</span></span>

<span data-ttu-id="b3a27-496">16 자의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-496">16 letters and digits:</span></span>
  
-  <span data-ttu-id="b3a27-497">가족 이름에서 처음 세 개의 자음에 해당 하는 3 개의 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-497">Three letters that correspond to the first three consonants in the family name</span></span> 
    
- <span data-ttu-id="b3a27-498">이름의 첫 번째, 세 번째 및 네 번째 자음에 해당 하는 3 개의 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-498">Three letters that correspond to the first, third, and fourth consonants in the first name</span></span>
    
- <span data-ttu-id="b3a27-499">출생 연도의 마지막 자리에 해당 하는 2 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-499">Two digits that correspond to the last digits of the birth year</span></span>
    
- <span data-ttu-id="b3a27-500">출생 달에 해당 하는 1 자리 숫자는 알파벳 순으로 사용 되지만 A에서 E, H, L, M, P, R에 해당 하는 문자만 사용 되며, 따라서 1 월은 A와 10 월이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-500">One digit that corresponds to the month of birth—letters are used in alphabetical order, but only the letters A to E, H, L, M, P, R to T are used (thus, January is A and October is R)</span></span>
    
- <span data-ttu-id="b3a27-501">남성의와 구별 하기 위해 여성의 경우 짝수에서 출생 일에 40이 추가 되는 출생 달의 날짜에 해당 하는 2 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-501">Two digits that correspond to the day of the month of birth where 40 is added to the day of birth for females to differentiate from males</span></span>
    
- <span data-ttu-id="b3a27-502">사용자가 태어난 municipality 관련 지역 번호에 해당 하는 4 자리 숫자-국가 전체 코드를 외국 국가에 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-502">Four digits that correspond to an area code specific to the municipality where the person was born—country-wide codes are used for foreign countries</span></span>
    
- <span data-ttu-id="b3a27-503">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-503">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-504">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-504">Checksum</span></span>

<span data-ttu-id="b3a27-505">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-505">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-506">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-506">Definition</span></span>

<span data-ttu-id="b3a27-507">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-507">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-508">이 함수 `Func_italy_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-508">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-509">From `Keywords_italy_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-509">A keyword from  `Keywords_italy_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-510">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-510">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-511">이 함수 `Func_italy_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-511">The function  `Func_italy_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
          <Match idRef="Keywords_italy_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_italy_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-512">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-512">Keywords</span></span>

#### <a name="keywords_italy_eu_tax_file_number"></a><span data-ttu-id="b3a27-513">Keywords_italy_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-513">Keywords_italy_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-514">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-514">tax number</span></span>
  
<span data-ttu-id="b3a27-515">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-515">tax no.</span></span>
  
<span data-ttu-id="b3a27-516">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-516">taxno#</span></span>
  
<span data-ttu-id="b3a27-517">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-517">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-518">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-518">taxnumber</span></span>
  
<span data-ttu-id="b3a27-519">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-519">tax id</span></span>
  
<span data-ttu-id="b3a27-520">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-520">taxid#</span></span>
  
<span data-ttu-id="b3a27-521">회계 코드</span><span class="sxs-lookup"><span data-stu-id="b3a27-521">fiscal code</span></span>
  
<span data-ttu-id="b3a27-522">codice</span><span class="sxs-lookup"><span data-stu-id="b3a27-522">codice fiscale</span></span>
  
## <a name="latvia"></a><span data-ttu-id="b3a27-523">라트비아</span><span class="sxs-lookup"><span data-stu-id="b3a27-523">Latvia</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-524">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-524">Format</span></span>

<span data-ttu-id="b3a27-525">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-525">11 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-526">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-526">Pattern</span></span>

<span data-ttu-id="b3a27-527">지정 된 패턴에서 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-527">11 digits in the specified pattern</span></span>
  
-  <span data-ttu-id="b3a27-528">출생 날짜에 해당 하는 6 자리 숫자 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="b3a27-528">Six digits that correspond to the date of birth (DDMMYY)</span></span> 
    
- <span data-ttu-id="b3a27-529">출생 세기에 해당 하는 1 자리 숫자 이며, "0"은 19th 세기에 해당 하 고 "1"은 20th 세기에 해당 하며 21 세기에 해당 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-529">One digit that corresponds to the century of birth where "0" corresponds to 19th century, "1" corresponds to 20th century, and "2"corresponds to 21st century</span></span>
    
- <span data-ttu-id="b3a27-530">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-530">Four digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-531">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-531">Checksum</span></span>

<span data-ttu-id="b3a27-532">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-532">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-533">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-533">Definition</span></span>

<span data-ttu-id="b3a27-534">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-534">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-535">이 함수 `Func_latvia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-535">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-536">From `Keywords_latvia_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-536">A keyword from  `Keywords_latvia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-537">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-537">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-538">이 함수 `Func_latvia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-538">The function  `Func_latvia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
          <Match idRef="Keywords_latvia_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_latvia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-539">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-539">Keywords</span></span>

#### <a name="keywords_latvia_eu_tax_file_number"></a><span data-ttu-id="b3a27-540">Keywords_latvia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-540">Keywords_latvia_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-541">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-541">tax number</span></span>
  
<span data-ttu-id="b3a27-542">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-542">tax no.</span></span>
  
<span data-ttu-id="b3a27-543">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-543">taxno#</span></span>
  
<span data-ttu-id="b3a27-544">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-544">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-545">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-545">taxnumber</span></span>
  
<span data-ttu-id="b3a27-546">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-546">tax id</span></span>
  
<span data-ttu-id="b3a27-547">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-547">taxid#</span></span>
  
<span data-ttu-id="b3a27-548">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-548">tax identification number</span></span>
  
<span data-ttu-id="b3a27-549">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-549">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-550">nodokļa numurs</span><span class="sxs-lookup"><span data-stu-id="b3a27-550">nodokļa numurs</span></span>
  
<span data-ttu-id="b3a27-551">nodokļu identifikācijas numurs</span><span class="sxs-lookup"><span data-stu-id="b3a27-551">nodokļu identifikācijas numurs</span></span>
  
<span data-ttu-id="b3a27-552">nodokļu identifikācija numurs</span><span class="sxs-lookup"><span data-stu-id="b3a27-552">nodokļu identifikācija numurs</span></span>
  
## <a name="lithuania"></a><span data-ttu-id="b3a27-553">리투아니아</span><span class="sxs-lookup"><span data-stu-id="b3a27-553">Lithuania</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-554">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-554">Format</span></span>

<span data-ttu-id="b3a27-555">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-555">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-556">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-556">Pattern</span></span>

<span data-ttu-id="b3a27-557">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-557">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-558">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-558">Checksum</span></span>

<span data-ttu-id="b3a27-559">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-559">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-560">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-560">Definition</span></span>

<span data-ttu-id="b3a27-561">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-561">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-562">이 함수 `Func_lithuania_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-562">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-563">From `Keywords_lithuania_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-563">A keyword from  `Keywords_lithuania_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-564">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-564">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-565">이 함수 `Func_lithuania_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-565">The function  `Func_lithuania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
          <Match idRef="Keywords_lithuania_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_lithuania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-566">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-566">Keywords</span></span>

#### <a name="keywords_lithuania_eu_tax_file_number"></a><span data-ttu-id="b3a27-567">Keywords_lithuania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-567">Keywords_lithuania_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-568">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-568">tax number</span></span>
  
<span data-ttu-id="b3a27-569">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-569">tax no.</span></span>
  
<span data-ttu-id="b3a27-570">세금 없음 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-570">tax no#</span></span>
  
<span data-ttu-id="b3a27-571">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-571">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-572">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-572">taxnumber</span></span>
  
<span data-ttu-id="b3a27-573">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-573">tax id</span></span>
  
<span data-ttu-id="b3a27-574">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-574">taxid#</span></span>
  
<span data-ttu-id="b3a27-575">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-575">tax identification number</span></span>
  
<span data-ttu-id="b3a27-576">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-576">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-577">mokesčių id</span><span class="sxs-lookup"><span data-stu-id="b3a27-577">mokesčių id</span></span>
  
<span data-ttu-id="b3a27-578">mokesčių numeris</span><span class="sxs-lookup"><span data-stu-id="b3a27-578">mokesčių numeris</span></span>
  
<span data-ttu-id="b3a27-579">mokesčių identifikavimas numeris</span><span class="sxs-lookup"><span data-stu-id="b3a27-579">mokesčių identifikavimas numeris</span></span>
  
## <a name="luxemburg"></a><span data-ttu-id="b3a27-580">셈</span><span class="sxs-lookup"><span data-stu-id="b3a27-580">Luxemburg</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-581">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-581">Format</span></span>

<span data-ttu-id="b3a27-582">공백이 나 구분 기호가 없는 13 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-582">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-583">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-583">Pattern</span></span>

<span data-ttu-id="b3a27-584">13자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="b3a27-584">13 digits:</span></span>
  
-  <span data-ttu-id="b3a27-585">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-585">11 digits</span></span> 
    
- <span data-ttu-id="b3a27-586">2개의 검사 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-586">Two check digits</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-587">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-587">Checksum</span></span>

<span data-ttu-id="b3a27-588">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-588">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-589">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-589">Definition</span></span>

<span data-ttu-id="b3a27-590">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-590">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-591">이 함수 `Func_luxemburg_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-591">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-592">From `Keywords_luxemburg_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-592">A keyword from  `Keywords_luxemburg_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-593">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-594">이 함수 `Func_luxemburg_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-594">The function  `Func_luxemburg_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
          <Match idRef="Keywords_luxemburg_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_luxemburg_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-595">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-595">Keywords</span></span>

#### <a name="keywords_luxemburg_eu_tax_file_number"></a><span data-ttu-id="b3a27-596">Keywords_luxemburg_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-596">Keywords_luxemburg_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-597">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-597">tax number</span></span>
  
<span data-ttu-id="b3a27-598">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-598">tax no.</span></span>
  
<span data-ttu-id="b3a27-599">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-599">taxno#</span></span>
  
<span data-ttu-id="b3a27-600">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-600">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-601">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-601">taxnumber</span></span>
  
<span data-ttu-id="b3a27-602">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-602">tax id</span></span>
  
<span data-ttu-id="b3a27-603">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-603">taxid#</span></span>
  
<span data-ttu-id="b3a27-604">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-604">tax identification number</span></span>
  
<span data-ttu-id="b3a27-605">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-605">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-606">steuernummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-606">steuernummer</span></span>
  
<span data-ttu-id="b3a27-607">steuer id</span><span class="sxs-lookup"><span data-stu-id="b3a27-607">steuer id</span></span>
  
<span data-ttu-id="b3a27-608">steueridentifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-608">steueridentifikationsnummer</span></span>
  
## <a name="malta"></a><span data-ttu-id="b3a27-609">몰타</span><span class="sxs-lookup"><span data-stu-id="b3a27-609">Malta</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-610">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-610">Format</span></span>

<span data-ttu-id="b3a27-611">몰타어 nationals의 경우 지정 된 패턴의 7 자리 및 한 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-611">For Maltese nationals: 7 digits and one letter in the specified pattern</span></span>
  
<span data-ttu-id="b3a27-612">몰타어 이외의 nationals 및 몰타어 엔터티: 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-612">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-613">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-613">Pattern</span></span>

<span data-ttu-id="b3a27-614">몰타어 nationals: 7 자리 숫자 및 1 개 문자</span><span class="sxs-lookup"><span data-stu-id="b3a27-614">Maltese nationals: 7 digits and one letter</span></span>
  
-  <span data-ttu-id="b3a27-615">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-615">Seven digits</span></span> 
    
- <span data-ttu-id="b3a27-616">1 개 문자 (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="b3a27-616">One letter (not case-sensitive)</span></span>
    
<span data-ttu-id="b3a27-617">몰타어 이외의 nationals 및 몰타어 엔터티: 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-617">Non-Maltese nationals and Maltese entities: 9 digits</span></span>
  
-  <span data-ttu-id="b3a27-618">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-618">Nine digits</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b3a27-619">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-619">Checksum</span></span>

<span data-ttu-id="b3a27-620">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-620">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-621">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-621">Definition</span></span>

<span data-ttu-id="b3a27-622">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-622">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-623">이 함수 `Func_malta_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-623">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-624">From `Keywords_malta_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-624">A keyword from  `Keywords_malta_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-625">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-626">이 함수 `Func_malta_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-626">The function  `Func_malta_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_malta_eu_tax_file_number" />
          <Match idRef="Keywords_malta_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="65">
          <IdMatch idRef="Regex_malta_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-627">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-627">Keywords</span></span>

#### <a name="keywords_malta_eu_tax_file_number"></a><span data-ttu-id="b3a27-628">Keywords_malta_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-628">Keywords_malta_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-629">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-629">tax number</span></span>
  
<span data-ttu-id="b3a27-630">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-630">tax no.</span></span>
  
<span data-ttu-id="b3a27-631">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-631">taxno#</span></span>
  
<span data-ttu-id="b3a27-632">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-632">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-633">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-633">taxnumber</span></span>
  
<span data-ttu-id="b3a27-634">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-634">tax id</span></span>
  
<span data-ttu-id="b3a27-635">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-635">taxid#</span></span>
  
<span data-ttu-id="b3a27-636">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-636">tax identification number</span></span>
  
<span data-ttu-id="b3a27-637">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-637">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-638">numru tat</span><span class="sxs-lookup"><span data-stu-id="b3a27-638">numru tat-taxxa</span></span>
  
<span data-ttu-id="b3a27-639">id tat-taxxa</span><span class="sxs-lookup"><span data-stu-id="b3a27-639">id tat-taxxa</span></span>
  
<span data-ttu-id="b3a27-640">numru ta ' taxxa</span><span class="sxs-lookup"><span data-stu-id="b3a27-640">numru ta 'identifikazzjoni tat-taxxa</span></span>
  
## <a name="netherlands"></a><span data-ttu-id="b3a27-641">네덜란드</span><span class="sxs-lookup"><span data-stu-id="b3a27-641">Netherlands</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-642">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-642">Format</span></span>

<span data-ttu-id="b3a27-643">공백이 나 구분 기호가 없는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-643">Nine digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-644">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-644">Pattern</span></span>

<span data-ttu-id="b3a27-645">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-645">Nine digits</span></span> 
  
### <a name="checksum"></a><span data-ttu-id="b3a27-646">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-646">Checksum</span></span>

<span data-ttu-id="b3a27-647">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-647">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-648">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-648">Definition</span></span>

<span data-ttu-id="b3a27-649">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-649">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-650">이 함수 `Func_netherlands_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-650">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-651">From `Keywords_netherlands_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-651">A keyword from  `Keywords_netherlands_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-652">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-652">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-653">이 함수 `Func_netherlands_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-653">The function  `Func_netherlands_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
          <Match idRef="Keywords_netherlands_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_netherlands_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-654">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-654">Keywords</span></span>

#### <a name="keywords_netherlands_eu_tax_file_number"></a><span data-ttu-id="b3a27-655">Keywords_netherlands_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-655">Keywords_netherlands_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-656">네덜란드 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-656">netherlands tax identification number</span></span>
  
<span data-ttu-id="b3a27-657">네덜란드 세금 식별</span><span class="sxs-lookup"><span data-stu-id="b3a27-657">netherlands tax identification</span></span>
  
<span data-ttu-id="b3a27-658">netherland의 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-658">netherland's tax identification number</span></span>
  
<span data-ttu-id="b3a27-659">netherland의 세금 식별</span><span class="sxs-lookup"><span data-stu-id="b3a27-659">netherland's tax identification</span></span>
  
<span data-ttu-id="b3a27-660">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-660">tax identification number</span></span>
  
<span data-ttu-id="b3a27-661">네덜란드어 세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-661">dutch tax id</span></span>
  
<span data-ttu-id="b3a27-662">네덜란드어 세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-662">dutch tax identification number</span></span>
  
<span data-ttu-id="b3a27-663">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-663">tax id</span></span>
  
<span data-ttu-id="b3a27-664">세금 번호 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-664">tax id#</span></span>
  
<span data-ttu-id="b3a27-665">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-665">tax number</span></span>
  
<span data-ttu-id="b3a27-666">세금 없음 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-666">tax no#</span></span>
  
<span data-ttu-id="b3a27-667">세금 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-667">tax#</span></span>
  
<span data-ttu-id="b3a27-668">언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-668">tin</span></span>
  
<span data-ttu-id="b3a27-669">언급 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-669">tin#</span></span>
  
<span data-ttu-id="b3a27-670">네덜란드 언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-670">netherlands tin</span></span>
  
<span data-ttu-id="b3a27-671">netherland의 언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-671">netherland's tin</span></span>
  
<span data-ttu-id="b3a27-672">nederlands belasting identificatienummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-672">nederlands belasting identificatienummer</span></span>
  
<span data-ttu-id="b3a27-673">identificatienummer van belasting</span><span class="sxs-lookup"><span data-stu-id="b3a27-673">identificatienummer van belasting</span></span>
  
<span data-ttu-id="b3a27-674">identificatienummer belasting</span><span class="sxs-lookup"><span data-stu-id="b3a27-674">identificatienummer belasting</span></span>
  
<span data-ttu-id="b3a27-675">nederlands belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="b3a27-675">nederlands belasting identificatie</span></span>
  
<span data-ttu-id="b3a27-676">nederlands belasting id nummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-676">nederlands belasting id nummer</span></span>
  
<span data-ttu-id="b3a27-677">nederlands belastingnummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-677">nederlands belastingnummer</span></span>
  
<span data-ttu-id="b3a27-678">btw nummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-678">btw nummer</span></span>
  
<span data-ttu-id="b3a27-679">nederlandse belasting identificatie</span><span class="sxs-lookup"><span data-stu-id="b3a27-679">nederlandse belasting identificatie</span></span>
  
## <a name="poland"></a><span data-ttu-id="b3a27-680">폴란드</span><span class="sxs-lookup"><span data-stu-id="b3a27-680">Poland</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-681">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-681">Format</span></span>

<span data-ttu-id="b3a27-682">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-682">Eleven digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-683">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-683">Pattern</span></span>

<span data-ttu-id="b3a27-684">11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-684">Eleven digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-685">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-685">Checksum</span></span>

<span data-ttu-id="b3a27-686">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-686">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-687">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-687">Definition</span></span>

<span data-ttu-id="b3a27-688">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-688">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-689">이 함수 `Func_poland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-689">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-690">From `Keywords_poland_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-690">A keyword from  `Keywords_poland_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-691">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-691">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-692">이 함수 `Func_poland_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-692">The function  `Func_poland_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
          <Match idRef="Keywords_poland_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_poland_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-693">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-693">Keywords</span></span>

#### <a name="keywords_poland_eu_tax_file_number"></a><span data-ttu-id="b3a27-694">Keywords_poland_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-694">Keywords_poland_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-695">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-695">tax number</span></span>
  
<span data-ttu-id="b3a27-696">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-696">tax no.</span></span>
  
<span data-ttu-id="b3a27-697">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-697">taxno#</span></span>
  
<span data-ttu-id="b3a27-698">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-698">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-699">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-699">taxnumber</span></span>
  
<span data-ttu-id="b3a27-700">nip</span><span class="sxs-lookup"><span data-stu-id="b3a27-700">nip</span></span>
  
<span data-ttu-id="b3a27-701">nip #</span><span class="sxs-lookup"><span data-stu-id="b3a27-701">nip#</span></span>
  
<span data-ttu-id="b3a27-702">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-702">tax id</span></span>
  
<span data-ttu-id="b3a27-703">세금 번호 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-703">tax id#</span></span>
  
<span data-ttu-id="b3a27-704">nip id</span><span class="sxs-lookup"><span data-stu-id="b3a27-704">nip id</span></span>
  
<span data-ttu-id="b3a27-705">nip id #</span><span class="sxs-lookup"><span data-stu-id="b3a27-705">nip id#</span></span>
  
<span data-ttu-id="b3a27-706">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-706">tax identification number</span></span>
  
<span data-ttu-id="b3a27-707">세금 식별 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-707">tax identification no.</span></span>
  
<span data-ttu-id="b3a27-708">vat 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-708">vat number</span></span>
  
<span data-ttu-id="b3a27-709">vat 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-709">vat no.</span></span>
  
<span data-ttu-id="b3a27-710">vatno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-710">vatno#</span></span>
  
<span data-ttu-id="b3a27-711">vat id</span><span class="sxs-lookup"><span data-stu-id="b3a27-711">vat id</span></span>
  
<span data-ttu-id="b3a27-712">vat id #</span><span class="sxs-lookup"><span data-stu-id="b3a27-712">vat id#</span></span>
  
<span data-ttu-id="b3a27-713">u r i identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="b3a27-713">numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b3a27-714">정책 스키 u r i identyfikacji podatkowej</span><span class="sxs-lookup"><span data-stu-id="b3a27-714">polski numer identyfikacji podatkowej</span></span>
  
<span data-ttu-id="b3a27-715">numeridentyfikacjipodatkowej #</span><span class="sxs-lookup"><span data-stu-id="b3a27-715">numeridentyfikacjipodatkowej#</span></span>
  
## <a name="portugal"></a><span data-ttu-id="b3a27-716">포르투갈</span><span class="sxs-lookup"><span data-stu-id="b3a27-716">Portugal</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-717">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-717">Format</span></span>

<span data-ttu-id="b3a27-718">공백이 나 구분 기호가 없는 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-718">Nine digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-719">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-719">Pattern</span></span>

<span data-ttu-id="b3a27-720">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-720">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-721">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-721">Checksum</span></span>

<span data-ttu-id="b3a27-722">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-722">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-723">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-723">Definition</span></span>

<span data-ttu-id="b3a27-724">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-724">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-725">이 함수 `Func_portugal_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-725">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-726">From `Keywords_portugal_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-726">A keyword from  `Keywords_portugal_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-727">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-728">이 함수 `Func_portugal_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-728">The function  `Func_portugal_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
          <Match idRef="Keywords_portugal_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_portugal_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-729">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-729">Keywords</span></span>

#### <a name="keywords_portugal_eu_tax_file_number"></a><span data-ttu-id="b3a27-730">Keywords_portugal_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-730">Keywords_portugal_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-731">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-731">tax number</span></span>
  
<span data-ttu-id="b3a27-732">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-732">tax no.</span></span>
  
<span data-ttu-id="b3a27-733">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-733">taxno#</span></span>
  
<span data-ttu-id="b3a27-734">taxnumber #</span><span class="sxs-lookup"><span data-stu-id="b3a27-734">taxnumber#</span></span>
  
<span data-ttu-id="b3a27-735">taxnumber</span><span class="sxs-lookup"><span data-stu-id="b3a27-735">taxnumber</span></span>
  
<span data-ttu-id="b3a27-736">m</span><span class="sxs-lookup"><span data-stu-id="b3a27-736">nif</span></span>
  
<span data-ttu-id="b3a27-737">m #</span><span class="sxs-lookup"><span data-stu-id="b3a27-737">nif#</span></span>
  
<span data-ttu-id="b3a27-738">numero 회계</span><span class="sxs-lookup"><span data-stu-id="b3a27-738">numero fiscal</span></span>
  
<span data-ttu-id="b3a27-739">número de identificação 회계</span><span class="sxs-lookup"><span data-stu-id="b3a27-739">número de identificação fiscal</span></span>
  
## <a name="romania"></a><span data-ttu-id="b3a27-740">루마니아</span><span class="sxs-lookup"><span data-stu-id="b3a27-740">Romania</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-741">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-741">Format</span></span>

<span data-ttu-id="b3a27-742">공백이 나 구분 기호가 없는 13 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-742">13 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-743">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-743">Pattern</span></span>

<span data-ttu-id="b3a27-744">13자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-744">13 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-745">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-745">Checksum</span></span>

<span data-ttu-id="b3a27-746">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-746">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-747">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-747">Definition</span></span>

<span data-ttu-id="b3a27-748">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-748">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-749">정규식이 해당 `Regex_romania_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-749">The regular expression  `Regex_romania_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-750">From `Keywords_romania_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-750">A keyword from  `Keywords_romania_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_romania_eu_tax_file_number" />
          <Match idRef="Keywords_romania_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-751">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-751">Keywords</span></span>

#### <a name="keywords_romania_eu_tax_file_number"></a><span data-ttu-id="b3a27-752">Keywords_romania_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-752">Keywords_romania_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-753">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-753">tax id</span></span>
  
<span data-ttu-id="b3a27-754">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-754">tax id number</span></span>
  
<span data-ttu-id="b3a27-755">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-755">tax file no</span></span>
  
<span data-ttu-id="b3a27-756">tax file number</span><span class="sxs-lookup"><span data-stu-id="b3a27-756">tax file number</span></span>
  
<span data-ttu-id="b3a27-757">세금 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-757">tax no</span></span>
  
<span data-ttu-id="b3a27-758">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-758">tax number</span></span>
  
<span data-ttu-id="b3a27-759">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-759">taxid#</span></span>
  
<span data-ttu-id="b3a27-760">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-760">taxno#</span></span>
  
<span data-ttu-id="b3a27-761">id-ul taxei</span><span class="sxs-lookup"><span data-stu-id="b3a27-761">id-ul taxei</span></span>
  
<span data-ttu-id="b3a27-762">numărul de identificare fiscală</span><span class="sxs-lookup"><span data-stu-id="b3a27-762">numărul de identificare fiscală</span></span>
  
## <a name="slovakia"></a><span data-ttu-id="b3a27-763">슬로바키아</span><span class="sxs-lookup"><span data-stu-id="b3a27-763">Slovakia</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-764">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-764">Format</span></span>

<span data-ttu-id="b3a27-765">공백이 나 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-765">10 digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-766">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-766">Pattern</span></span>

<span data-ttu-id="b3a27-767">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-767">10 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-768">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-768">Checksum</span></span>

<span data-ttu-id="b3a27-769">해당 사항 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-769">Not applicable</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-770">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-770">Definition</span></span>

<span data-ttu-id="b3a27-771">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-771">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-772">정규식이 해당 `Regex_slovakia_eu_tax_file_number` 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-772">The regular expression  `Regex_slovakia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-773">From `Keywords_slovakia_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-773">A keyword from  `Keywords_slovakia_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Regex_slovakia_eu_tax_file_number" />
          <Match idRef="Keywords_slovakia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-774">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-774">Keywords</span></span>

#### <a name="keywords_slovakia_eu_tax_file_number"></a><span data-ttu-id="b3a27-775">Keywords_slovakia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-775">Keywords_slovakia_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-776">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-776">tax id</span></span>
  
<span data-ttu-id="b3a27-777">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-777">tax id number</span></span>
  
<span data-ttu-id="b3a27-778">언급 id</span><span class="sxs-lookup"><span data-stu-id="b3a27-778">tin id</span></span>
  
<span data-ttu-id="b3a27-779">언급 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-779">tin no</span></span>
  
<span data-ttu-id="b3a27-780">슬로바키아어 언급 id</span><span class="sxs-lookup"><span data-stu-id="b3a27-780">slovakian tin id</span></span>
  
<span data-ttu-id="b3a27-781">언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-781">tin</span></span>
  
<span data-ttu-id="b3a27-782">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-782">tax file no</span></span>
  
<span data-ttu-id="b3a27-783">tax file number</span><span class="sxs-lookup"><span data-stu-id="b3a27-783">tax file number</span></span>
  
<span data-ttu-id="b3a27-784">세금 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-784">tax no</span></span>
  
<span data-ttu-id="b3a27-785">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-785">tax number</span></span>
  
<span data-ttu-id="b3a27-786">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-786">taxid#</span></span>
  
<span data-ttu-id="b3a27-787">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-787">taxno#</span></span>
  
<span data-ttu-id="b3a27-788">daňové identifikačné číslo</span><span class="sxs-lookup"><span data-stu-id="b3a27-788">daňové identifikačné číslo</span></span>
  
<span data-ttu-id="b3a27-789">daňové číslo</span><span class="sxs-lookup"><span data-stu-id="b3a27-789">daňové číslo</span></span>
  
<span data-ttu-id="b3a27-790">daňové číslo súboru</span><span class="sxs-lookup"><span data-stu-id="b3a27-790">daňové číslo súboru</span></span>
  
## <a name="slovenia"></a><span data-ttu-id="b3a27-791">슬로베니아</span><span class="sxs-lookup"><span data-stu-id="b3a27-791">Slovenia</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-792">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-792">Format</span></span>

<span data-ttu-id="b3a27-793">공백이 나 구분 기호가 없는 8 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-793">Eight digits with no spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-794">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-794">Pattern</span></span>

<span data-ttu-id="b3a27-795">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-795">Eight digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-796">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-796">Checksum</span></span>

<span data-ttu-id="b3a27-797">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-797">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-798">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-798">Definition</span></span>

<span data-ttu-id="b3a27-799">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-799">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-800">이 함수 `Func_slovenia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-800">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-801">From `Keywords_slovenia_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-801">A keyword from  `Keywords_slovenia_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-802">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-802">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-803">이 함수 `Func_slovenia_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-803">The function  `Func_slovenia_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_nation_eu_tax_file_number" />
          <Match idRef="Keywords_nation_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_slovenia_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-804">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-804">Keywords</span></span>

#### <a name="keywords_slovenia_eu_tax_file_number"></a><span data-ttu-id="b3a27-805">Keywords_slovenia_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-805">Keywords_slovenia_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-806">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-806">tax id</span></span>
  
<span data-ttu-id="b3a27-807">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-807">tax id number</span></span>
  
<span data-ttu-id="b3a27-808">언급 id</span><span class="sxs-lookup"><span data-stu-id="b3a27-808">tin id</span></span>
  
<span data-ttu-id="b3a27-809">언급 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-809">tin no</span></span>
  
<span data-ttu-id="b3a27-810">슬로베니아어 언급 id</span><span class="sxs-lookup"><span data-stu-id="b3a27-810">slovenian tin id</span></span>
  
<span data-ttu-id="b3a27-811">언급</span><span class="sxs-lookup"><span data-stu-id="b3a27-811">tin</span></span>
  
<span data-ttu-id="b3a27-812">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-812">tax file no</span></span>
  
<span data-ttu-id="b3a27-813">tax file number</span><span class="sxs-lookup"><span data-stu-id="b3a27-813">tax file number</span></span>
  
<span data-ttu-id="b3a27-814">세금 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-814">tax no</span></span>
  
<span data-ttu-id="b3a27-815">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-815">tax number</span></span>
  
<span data-ttu-id="b3a27-816">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-816">taxid#</span></span>
  
<span data-ttu-id="b3a27-817">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-817">taxno#</span></span>
  
<span data-ttu-id="b3a27-818">identifikacijska številka davka</span><span class="sxs-lookup"><span data-stu-id="b3a27-818">identifikacijska številka davka</span></span>
  
<span data-ttu-id="b3a27-819">davčna številka</span><span class="sxs-lookup"><span data-stu-id="b3a27-819">davčna številka</span></span>
  
<span data-ttu-id="b3a27-820">številka davčne datoteke</span><span class="sxs-lookup"><span data-stu-id="b3a27-820">številka davčne datoteke</span></span>
  
## <a name="spain"></a><span data-ttu-id="b3a27-821">스페인</span><span class="sxs-lookup"><span data-stu-id="b3a27-821">Spain</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-822">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-822">Format</span></span>

<span data-ttu-id="b3a27-823">지정 된 패턴에 7 ~ 8 자리 숫자와 한 가지 또는 두 개의 문자가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-823">Seven or eight digits and one or two letters in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-824">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-824">Pattern</span></span>

<span data-ttu-id="b3a27-825">스페인 국내 Id 카드가 있는 스페인어 (자연 사용자):</span><span class="sxs-lookup"><span data-stu-id="b3a27-825">Spanish Natural Persons with a Spain National Identity Card:</span></span>
  
-  <span data-ttu-id="b3a27-826">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-826">Eight digits</span></span> 
    
- <span data-ttu-id="b3a27-827">대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-827">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b3a27-828">스페인 국가 Id 카드가 없는 상주 하지 않는 Spaniards</span><span class="sxs-lookup"><span data-stu-id="b3a27-828">Non-resident Spaniards without a Spain National Identity Card</span></span>
  
- <span data-ttu-id="b3a27-829">1 개의 대문자 "L" (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-829">One uppercase letter "L" (case-sensitive)</span></span>
    
- <span data-ttu-id="b3a27-830">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-830">Seven digits</span></span>
    
- <span data-ttu-id="b3a27-831">대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-831">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b3a27-832">스페인 국가 Id 카드를 사용 하지 않고 14 년 동안 상주 하는 Spaniards:</span><span class="sxs-lookup"><span data-stu-id="b3a27-832">Resident Spaniards under the age of 14 years without a Spain National Identity Card :</span></span>
  
- <span data-ttu-id="b3a27-833">1 개의 대문자 "K" (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-833">One uppercase letter"K" (case-sensitive)</span></span>
    
-  <span data-ttu-id="b3a27-834">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-834">Seven digits</span></span> 
    
- <span data-ttu-id="b3a27-835">대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-835">One uppercase letter (case-sensitive)</span></span>
    
<span data-ttu-id="b3a27-836">Foreigner의 식별 번호를 사용 하는 Foreigners</span><span class="sxs-lookup"><span data-stu-id="b3a27-836">Foreigners with a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b3a27-837">"X", "Y" 또는 "Z" (대/소문자 구분)의 대문자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-837">One uppercase letter that is "X", "Y", or "Z" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b3a27-838">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-838">Seven digits</span></span>
    
- <span data-ttu-id="b3a27-839">대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-839">One uppercase letter (case-sensitive)</span></span> 
    
<span data-ttu-id="b3a27-840">Foreigner의 Id 번호가 없는 Foreigners</span><span class="sxs-lookup"><span data-stu-id="b3a27-840">Foreigners without a Foreigner's Identification Number</span></span>
  
- <span data-ttu-id="b3a27-841">"M"을 나타내는 대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-841">One uppercase letter that is "M" (case-sensitive)</span></span> 
    
- <span data-ttu-id="b3a27-842">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-842">Seven digits</span></span>
    
- <span data-ttu-id="b3a27-843">대문자 1 개 (대/소문자 구분)</span><span class="sxs-lookup"><span data-stu-id="b3a27-843">One uppercase letter (case-sensitive)</span></span> 
    
### <a name="checksum"></a><span data-ttu-id="b3a27-844">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-844">Checksum</span></span>

<span data-ttu-id="b3a27-845">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-845">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-846">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-846">Definition</span></span>

<span data-ttu-id="b3a27-847">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-847">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-848">이 함수 `Func_spain_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-848">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-849">From `Keywords_spain_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-849">A keyword from  `Keywords_spain_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-850">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-850">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-851">이 함수 `Func_spain_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-851">The function  `Func_spain_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
          <Match idRef="Keywords_spain_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_spain_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-852">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-852">Keywords</span></span>

#### <a name="keywords_spain_eu_tax_file_number"></a><span data-ttu-id="b3a27-853">Keywords_spain_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-853">Keywords_spain_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-854">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-854">tax id</span></span>
  
<span data-ttu-id="b3a27-855">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-855">tax id number</span></span>
  
<span data-ttu-id="b3a27-856">cif id</span><span class="sxs-lookup"><span data-stu-id="b3a27-856">cif id</span></span>
  
<span data-ttu-id="b3a27-857">cif 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-857">cif no</span></span>
  
<span data-ttu-id="b3a27-858">스페인어 cif id</span><span class="sxs-lookup"><span data-stu-id="b3a27-858">spanish cif id</span></span>
  
<span data-ttu-id="b3a27-859">cif</span><span class="sxs-lookup"><span data-stu-id="b3a27-859">cif</span></span>
  
<span data-ttu-id="b3a27-860">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-860">tax file no</span></span>
  
<span data-ttu-id="b3a27-861">스페인어 cif 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-861">spanish cif number</span></span>
  
<span data-ttu-id="b3a27-862">tax file number</span><span class="sxs-lookup"><span data-stu-id="b3a27-862">tax file number</span></span>
  
<span data-ttu-id="b3a27-863">스페인어 cif 아니요</span><span class="sxs-lookup"><span data-stu-id="b3a27-863">spanish cif no</span></span>
  
<span data-ttu-id="b3a27-864">세금 없음</span><span class="sxs-lookup"><span data-stu-id="b3a27-864">tax no</span></span>
  
<span data-ttu-id="b3a27-865">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-865">tax number</span></span>
  
<span data-ttu-id="b3a27-866">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-866">taxid#</span></span>
  
<span data-ttu-id="b3a27-867">taxno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-867">taxno#</span></span>
  
<span data-ttu-id="b3a27-868">cifid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-868">cifid#</span></span>
  
<span data-ttu-id="b3a27-869">spanishcifid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-869">spanishcifid#</span></span>
  
<span data-ttu-id="b3a27-870">spanishcifno #</span><span class="sxs-lookup"><span data-stu-id="b3a27-870">spanishcifno#</span></span>
  
<span data-ttu-id="b3a27-871">número de contribuyente</span><span class="sxs-lookup"><span data-stu-id="b3a27-871">número de contribuyente</span></span>
  
<span data-ttu-id="b3a27-872">número de impuesto corporativo</span><span class="sxs-lookup"><span data-stu-id="b3a27-872">número de impuesto corporativo</span></span>
  
<span data-ttu-id="b3a27-873">número de identificación 회계</span><span class="sxs-lookup"><span data-stu-id="b3a27-873">número de identificación fiscal</span></span>
  
<span data-ttu-id="b3a27-874">cif número</span><span class="sxs-lookup"><span data-stu-id="b3a27-874">cif número</span></span>
  
<span data-ttu-id="b3a27-875">cifnúmero #</span><span class="sxs-lookup"><span data-stu-id="b3a27-875">cifnúmero#</span></span>
  
## <a name="sweden"></a><span data-ttu-id="b3a27-876">스웨덴</span><span class="sxs-lookup"><span data-stu-id="b3a27-876">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-877">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-877">Format</span></span>

<span data-ttu-id="b3a27-878">지정 된 패턴의 10 자리 숫자와 기호</span><span class="sxs-lookup"><span data-stu-id="b3a27-878">Ten digits and a symbol in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-879">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-879">Pattern</span></span>

<span data-ttu-id="b3a27-880">10 자리 숫자와 기호:</span><span class="sxs-lookup"><span data-stu-id="b3a27-880">Ten digits and a symbol:</span></span>
  
-  <span data-ttu-id="b3a27-881">생년월일에 해당 하는 6 자리 숫자 (YYMMDD)</span><span class="sxs-lookup"><span data-stu-id="b3a27-881">Six digits that correspond to the birth date (YYMMDD)</span></span> 
    
- <span data-ttu-id="b3a27-882">더하기 기호, 빼기 기호 또는 백슬래시</span><span class="sxs-lookup"><span data-stu-id="b3a27-882">A plus sign, minus sign, or backslash</span></span>
    
- <span data-ttu-id="b3a27-883">다음은 식별 번호를 고유 하 게 만드는 3 자리 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-883">Three digits that make the identification number unique where:</span></span> 
    
  - <span data-ttu-id="b3a27-884">1990 이전에 실행 된 번호의 경우 일곱째 및 여덟 번째 숫자는 출생 또는 외부에서 태어난 사람의 국가를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-884">For numbers issued before 1990, the seventh and eighth digit identify the county of birth or foreign-born people</span></span>
    
  - <span data-ttu-id="b3a27-885">아홉 번째 위치의 숫자는 성별에 대 한 홀수 또는 암도를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-885">The digit in the ninth position indicates gender by either odd for male or even for female</span></span>
    
- <span data-ttu-id="b3a27-886">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="b3a27-886">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="b3a27-887">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-887">Checksum</span></span>

<span data-ttu-id="b3a27-888">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-888">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-889">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-889">Definition</span></span>

<span data-ttu-id="b3a27-890">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-890">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-891">이 함수 `Func_sweden_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-891">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-892">From `Keywords_sweden_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-892">A keyword from  `Keywords_sweden_eu_tax_file_number` is found.</span></span> 
    
<span data-ttu-id="b3a27-893">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-893">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-894">이 함수 `Func_sweden_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-894">The function  `Func_sweden_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
          <Match idRef="Keywords_sweden_eu_tax_file_number" />
        </Pattern>
<Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-895">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-895">Keywords</span></span>

#### <a name="keywords_sweden_eu_tax_file_number"></a><span data-ttu-id="b3a27-896">Keywords_sweden_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-896">Keywords_sweden_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-897">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-897">tax id</span></span>
  
<span data-ttu-id="b3a27-898">세금 번호 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-898">tax id no.</span></span>
  
<span data-ttu-id="b3a27-899">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-899">tax id number</span></span>
  
<span data-ttu-id="b3a27-900">tax identification</span><span class="sxs-lookup"><span data-stu-id="b3a27-900">tax identification</span></span>
  
<span data-ttu-id="b3a27-901">세금 식별 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-901">tax identification#</span></span>
  
<span data-ttu-id="b3a27-902">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-902">tax no.</span></span>
  
<span data-ttu-id="b3a27-903">세금 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-903">tax#</span></span>
  
<span data-ttu-id="b3a27-904">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-904">taxid#</span></span>
  
<span data-ttu-id="b3a27-905">세금 파일</span><span class="sxs-lookup"><span data-stu-id="b3a27-905">tax file</span></span>
  
<span data-ttu-id="b3a27-906">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-906">tax file no.</span></span>
  
<span data-ttu-id="b3a27-907">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-907">personal id number</span></span>
  
<span data-ttu-id="b3a27-908">(nummer at&t id)</span><span class="sxs-lookup"><span data-stu-id="b3a27-908">skatt id nummer</span></span>
  
<span data-ttu-id="b3a27-909">identifikation at&t</span><span class="sxs-lookup"><span data-stu-id="b3a27-909">skatt identifikation</span></span>
  
<span data-ttu-id="b3a27-910">personnummer</span><span class="sxs-lookup"><span data-stu-id="b3a27-910">personnummer</span></span>
  
## <a name="uk"></a><span data-ttu-id="b3a27-911">영국의</span><span class="sxs-lookup"><span data-stu-id="b3a27-911">UK</span></span>

### <a name="format"></a><span data-ttu-id="b3a27-912">형식일</span><span class="sxs-lookup"><span data-stu-id="b3a27-912">Format</span></span>

<span data-ttu-id="b3a27-913">UTR (Unique Taxpayer Reference): 공백 및 구분 기호가 없는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-913">Unique Taxpayer Reference (UTR): 10 digits without spaces and delimiters</span></span>
  
<span data-ttu-id="b3a27-914">국가 보험 번호 (NINO): 자세한 내용은 영국 섹션 "을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3a27-914">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="b3a27-915">[중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)국가 보험 번호 (NINO) "입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-915">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="pattern"></a><span data-ttu-id="b3a27-916">패턴</span><span class="sxs-lookup"><span data-stu-id="b3a27-916">Pattern</span></span>

<span data-ttu-id="b3a27-917">UTR (Unique Taxpayer Reference): 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="b3a27-917">Unique Taxpayer Reference (UTR): 10 digits</span></span>
  
<span data-ttu-id="b3a27-918">국가 보험 번호 (NINO): 자세한 내용은 영국 섹션 "을 참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="b3a27-918">National Insurance Number (NINO): For details, see the section "U.K.</span></span> <span data-ttu-id="b3a27-919">[중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)국가 보험 번호 (NINO) "입니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-919">National Insurance Number (NINO)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
### <a name="checksum"></a><span data-ttu-id="b3a27-920">제외</span><span class="sxs-lookup"><span data-stu-id="b3a27-920">Checksum</span></span>

<span data-ttu-id="b3a27-921">예</span><span class="sxs-lookup"><span data-stu-id="b3a27-921">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="b3a27-922">정의</span><span class="sxs-lookup"><span data-stu-id="b3a27-922">Definition</span></span>

<span data-ttu-id="b3a27-923">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-923">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="b3a27-924">이 함수 `Func_uk_eu_tax_file_number` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-924">The function  `Func_uk_eu_tax_file_number` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="b3a27-925">From `Keywords_uk_eu_tax_file_number` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="b3a27-925">A keyword from  `Keywords_uk_eu_tax_file_number` is found.</span></span> 
    
```
 <!-- EU Tax File Number -->
<Entity id="e09c07d3-66e5-4783-989d-49ac62748f5f" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_uk_eu_tax_file_number" />
          <Match idRef="Keywords_uk_eu_tax_file_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="b3a27-926">키워드</span><span class="sxs-lookup"><span data-stu-id="b3a27-926">Keywords</span></span>

#### <a name="keywords_uk_eu_tax_file_number"></a><span data-ttu-id="b3a27-927">Keywords_uk_eu_tax_file_number</span><span class="sxs-lookup"><span data-stu-id="b3a27-927">Keywords_uk_eu_tax_file_number</span></span>

<span data-ttu-id="b3a27-928">tax id</span><span class="sxs-lookup"><span data-stu-id="b3a27-928">tax id</span></span>
  
<span data-ttu-id="b3a27-929">세금 번호 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-929">tax id no.</span></span>
  
<span data-ttu-id="b3a27-930">세금 id 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-930">tax id number</span></span>
  
<span data-ttu-id="b3a27-931">tax identification</span><span class="sxs-lookup"><span data-stu-id="b3a27-931">tax identification</span></span>
  
<span data-ttu-id="b3a27-932">세금 식별 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-932">tax identification#</span></span>
  
<span data-ttu-id="b3a27-933">세금 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-933">tax no.</span></span>
  
<span data-ttu-id="b3a27-934">세금 #</span><span class="sxs-lookup"><span data-stu-id="b3a27-934">tax#</span></span>
  
<span data-ttu-id="b3a27-935">taxid #</span><span class="sxs-lookup"><span data-stu-id="b3a27-935">taxid#</span></span>
  
<span data-ttu-id="b3a27-936">세금 파일</span><span class="sxs-lookup"><span data-stu-id="b3a27-936">tax file</span></span>
  
<span data-ttu-id="b3a27-937">세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="b3a27-937">tax file no.</span></span>
  
## <a name="see-also"></a><span data-ttu-id="b3a27-938">참고 항목</span><span class="sxs-lookup"><span data-stu-id="b3a27-938">See also</span></span>

[<span data-ttu-id="b3a27-939">중요한 정보 유형이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="b3a27-939">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

