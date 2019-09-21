---
title: EU 주민 등록 번호 또는 동등한 ID
ms.author: stephow
author: stephow-MSFT
manager: laurawi
ms.date: 8/17/2018
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
description: 이 항목에서는 DLP (데이터 손실 방지) 정책이 EU 주민 등록 번호 또는 동등한 ID 중요 정보 유형을 검색할 때 찾는 항목을 보여 줍니다. 이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.
ms.openlocfilehash: b42a8d927e18f813eb6ef6d1d55b2de15ea9dcd5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2019
ms.locfileid: "37088069"
---
# <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="de021-104">EU 주민 등록 번호 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="de021-104">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="de021-105">이 항목에서는 DLP (데이터 손실 방지) 정책이 EU SSN (사회 보장 번호) 또는 동등한 ID 중요 정보 유형을 검색할 때 어떤 사항을 찾을 지를 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="de021-105">This topic shows what a data loss prevention (DLP) policy looks for when it detects the EU Social Security Number (SSN) or Equivalent ID sensitive information type.</span></span> <span data-ttu-id="de021-106">이 중요 한 정보 유형은 각 국가에 대 한 다양 한 패턴, 키워드 및 기타 증거를 정의 합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-106">This sensitive information type defines different patterns, keywords, and other evidence for each country.</span></span>
  
## <a name="austria"></a><span data-ttu-id="de021-107">오스트리아</span><span class="sxs-lookup"><span data-stu-id="de021-107">Austria</span></span>

### <a name="format"></a><span data-ttu-id="de021-108">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-108">Format</span></span>

<span data-ttu-id="de021-109">지정 된 형식의 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-109">10 digits in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-110">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-110">Pattern</span></span>

<span data-ttu-id="de021-111">10자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="de021-111">10 digits:</span></span>
  
-  <span data-ttu-id="de021-112">일련 번호에 해당 하는 3 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-112">Three digits that correspond to a serial number</span></span> 
    
- <span data-ttu-id="de021-113">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="de021-113">One check digit</span></span>
    
- <span data-ttu-id="de021-114">생년월일에 해당 하는 6 자리 숫자 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="de021-114">Six digits that correspond to the birth date (DDMMYY)</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-115">제외</span><span class="sxs-lookup"><span data-stu-id="de021-115">Checksum</span></span>

<span data-ttu-id="de021-116">예</span><span class="sxs-lookup"><span data-stu-id="de021-116">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-117">정의</span><span class="sxs-lookup"><span data-stu-id="de021-117">Definition</span></span>

<span data-ttu-id="de021-118">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-118">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-119">이 함수 `Func_austria_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-119">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-120">From `Keywords_austria_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-120">A keyword from  `Keywords_austria_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-121">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-121">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-122">이 함수 `Func_austria_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-122">The function  `Func_austria_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_austria_eu_ssn_or_equivalent" />
        </Pattern>
<Pattern confidenceLevel="75">
            <IdMatch idRef="Func_austria_eu_ssn_or_equivalent" />
          </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-123">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-123">Keywords</span></span>

#### <a name="keywords_austria_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-124">Keywords_austria_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-124">Keywords_austria_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-125">소셜 보안 아니요</span><span class="sxs-lookup"><span data-stu-id="de021-125">social security no</span></span>
  
<span data-ttu-id="de021-126">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-126">social security number</span></span>
  
<span data-ttu-id="de021-127">social security code</span><span class="sxs-lookup"><span data-stu-id="de021-127">social security code</span></span>
  
<span data-ttu-id="de021-128">보험 번호</span><span class="sxs-lookup"><span data-stu-id="de021-128">insurance number</span></span>
  
<span data-ttu-id="de021-129">오스트리아</span><span class="sxs-lookup"><span data-stu-id="de021-129">austrian ssn</span></span>
  
<span data-ttu-id="de021-130">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-130">ssn#</span></span>
  
<span data-ttu-id="de021-131">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-131">ssn</span></span>
  
<span data-ttu-id="de021-132">보험 코드</span><span class="sxs-lookup"><span data-stu-id="de021-132">insurance code</span></span>
  
<span data-ttu-id="de021-133">보험 코드 #</span><span class="sxs-lookup"><span data-stu-id="de021-133">insurance code#</span></span>
  
<span data-ttu-id="de021-134">사회 alsecurityno #</span><span class="sxs-lookup"><span data-stu-id="de021-134">socialsecurityno#</span></span>
  
<span data-ttu-id="de021-135">sozialversicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="de021-135">sozialversicherungsnummer</span></span>
  
<span data-ttu-id="de021-136">soziale sicherheit kein</span><span class="sxs-lookup"><span data-stu-id="de021-136">soziale sicherheit kein</span></span>
  
<span data-ttu-id="de021-137">versicherungsnummer</span><span class="sxs-lookup"><span data-stu-id="de021-137">versicherungsnummer</span></span>
  
## <a name="belgium"></a><span data-ttu-id="de021-138">벨기에</span><span class="sxs-lookup"><span data-stu-id="de021-138">Belgium</span></span>

### <a name="format"></a><span data-ttu-id="de021-139">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-139">Format</span></span>

<span data-ttu-id="de021-140">공백이 나 구분 기호가 없는 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-140">11 digits without spaces or delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-141">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-141">Pattern</span></span>

<span data-ttu-id="de021-142">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-142">11 digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de021-143">제외</span><span class="sxs-lookup"><span data-stu-id="de021-143">Checksum</span></span>

<span data-ttu-id="de021-144">예</span><span class="sxs-lookup"><span data-stu-id="de021-144">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-145">정의</span><span class="sxs-lookup"><span data-stu-id="de021-145">Definition</span></span>

<span data-ttu-id="de021-146">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-146">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-147">이 함수 `Func_belgium_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-147">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-148">From `Keywords_belgium_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-148">A keyword from  `Keywords_belgium_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-149">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-149">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-150">이 함수 `Func_belgium_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-150">The function  `Func_belgium_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_belgium_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_belgium_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-151">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-151">Keywords</span></span>

#### <a name="keywords_belgium_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-152">Keywords_belgium_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-152">Keywords_belgium_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-153">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="de021-153">belgian national number</span></span>
  
<span data-ttu-id="de021-154">국가 번호</span><span class="sxs-lookup"><span data-stu-id="de021-154">national number</span></span>
  
<span data-ttu-id="de021-155">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-155">social security number</span></span>
  
<span data-ttu-id="de021-156">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-156">nationalnumber#</span></span>
  
<span data-ttu-id="de021-157">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-157">ssn#</span></span>
  
<span data-ttu-id="de021-158">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-158">ssn</span></span>
  
<span data-ttu-id="de021-159">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="de021-159">nationalnumber</span></span>
  
<span data-ttu-id="de021-160">bnn #</span><span class="sxs-lookup"><span data-stu-id="de021-160">bnn#</span></span>
  
<span data-ttu-id="de021-161">bnn</span><span class="sxs-lookup"><span data-stu-id="de021-161">bnn</span></span>
  
<span data-ttu-id="de021-162">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-162">personal id number</span></span>
  
<span data-ttu-id="de021-163">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-163">personalidnumber#</span></span>
  
<span data-ttu-id="de021-164">numéro 국가</span><span class="sxs-lookup"><span data-stu-id="de021-164">numéro national</span></span>
  
<span data-ttu-id="de021-165">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="de021-165">numéro de sécurité</span></span>
  
<span data-ttu-id="de021-166">numéro d'assuré</span><span class="sxs-lookup"><span data-stu-id="de021-166">numéro d'assuré</span></span>
  
<span data-ttu-id="de021-167">identifiant 국가</span><span class="sxs-lookup"><span data-stu-id="de021-167">identifiant national</span></span>
  
<span data-ttu-id="de021-168">identifiantnational #</span><span class="sxs-lookup"><span data-stu-id="de021-168">identifiantnational#</span></span>
  
<span data-ttu-id="de021-169">numéronational #</span><span class="sxs-lookup"><span data-stu-id="de021-169">numéronational#</span></span>
  
## <a name="croatia"></a><span data-ttu-id="de021-170">크로아티아</span><span class="sxs-lookup"><span data-stu-id="de021-170">Croatia</span></span>

### <a name="format"></a><span data-ttu-id="de021-171">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-171">Format</span></span>

<span data-ttu-id="de021-172">공백과 구분 기호를 사용 하지 않고 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-172">11 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-173">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-173">Pattern</span></span>

 <span data-ttu-id="de021-174">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="de021-174">11 digits:</span></span> 
  
-  <span data-ttu-id="de021-175">10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-175">Ten digits</span></span> 
    
- <span data-ttu-id="de021-176">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="de021-176">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-177">제외</span><span class="sxs-lookup"><span data-stu-id="de021-177">Checksum</span></span>

<span data-ttu-id="de021-178">예</span><span class="sxs-lookup"><span data-stu-id="de021-178">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-179">정의</span><span class="sxs-lookup"><span data-stu-id="de021-179">Definition</span></span>

<span data-ttu-id="de021-180">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-180">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-181">이 함수 `Func_croatia_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-181">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-182">From `Keywords_croatia_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-182">A keyword from  `Keywords_croatia_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-183">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-183">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-184">이 함수 `Func_croatia_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-184">The function  `Func_croatia_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_croatia_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_croatia_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-185">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-185">Keywords</span></span>

#### <a name="keywords_croatia_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-186">Keywords_croatia_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-186">Keywords_croatia_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-187">개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="de021-187">personal identification number</span></span>
  
<span data-ttu-id="de021-188">마스터 시민 번호</span><span class="sxs-lookup"><span data-stu-id="de021-188">master citizen number</span></span>
  
<span data-ttu-id="de021-189">national identification number</span><span class="sxs-lookup"><span data-stu-id="de021-189">national identification number</span></span>
  
<span data-ttu-id="de021-190">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-190">social security number</span></span>
  
<span data-ttu-id="de021-191">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-191">nationalnumber#</span></span>
  
<span data-ttu-id="de021-192">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-192">ssn#</span></span>
  
<span data-ttu-id="de021-193">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-193">ssn</span></span>
  
<span data-ttu-id="de021-194">nationalnumber</span><span class="sxs-lookup"><span data-stu-id="de021-194">nationalnumber</span></span>
  
<span data-ttu-id="de021-195">bnn #</span><span class="sxs-lookup"><span data-stu-id="de021-195">bnn#</span></span>
  
<span data-ttu-id="de021-196">bnn</span><span class="sxs-lookup"><span data-stu-id="de021-196">bnn</span></span>
  
<span data-ttu-id="de021-197">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-197">personal id number</span></span>
  
<span data-ttu-id="de021-198">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-198">personalidnumber#</span></span>
  
<span data-ttu-id="de021-199">oib</span><span class="sxs-lookup"><span data-stu-id="de021-199">oib</span></span>
  
<span data-ttu-id="de021-200">osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="de021-200">osobni identifikacijski broj</span></span>
  
## <a name="czech-republic"></a><span data-ttu-id="de021-201">체코 공화국</span><span class="sxs-lookup"><span data-stu-id="de021-201">Czech Republic</span></span>

### <a name="format"></a><span data-ttu-id="de021-202">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-202">Format</span></span>

<span data-ttu-id="de021-203">지정 된 패턴의 10 자리 및 백슬래시</span><span class="sxs-lookup"><span data-stu-id="de021-203">Ten digits and a backslash in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-204">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-204">Pattern</span></span>

<span data-ttu-id="de021-205">10 자리 숫자와 백슬래시:</span><span class="sxs-lookup"><span data-stu-id="de021-205">Ten digits and a backslash:</span></span>
  
- <span data-ttu-id="de021-206">생년월일에 해당 하는 6 자리 숫자 (YYMMDD):</span><span class="sxs-lookup"><span data-stu-id="de021-206">Six digits that correspond to the birth date (YYMMDD):</span></span> 
    
- <span data-ttu-id="de021-207">백슬래시</span><span class="sxs-lookup"><span data-stu-id="de021-207">A backslash</span></span>
    
- <span data-ttu-id="de021-208">같은 날짜에 태어난 사람을 구분 하는 일련 번호에 해당 하는 3 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-208">Three digits that correspond to a serial number that separates persons born on the same date</span></span>
    
- <span data-ttu-id="de021-209">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="de021-209">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-210">제외</span><span class="sxs-lookup"><span data-stu-id="de021-210">Checksum</span></span>

<span data-ttu-id="de021-211">예</span><span class="sxs-lookup"><span data-stu-id="de021-211">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-212">정의</span><span class="sxs-lookup"><span data-stu-id="de021-212">Definition</span></span>

<span data-ttu-id="de021-213">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-213">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-214">이 함수 `Func_czech_republic_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-214">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-215">From `Keywords_czech_republic_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-215">A keyword from  `Keywords_czech_republic_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-216">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-216">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-217">이 함수 `Func_czech_republic_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-217">The function  `Func_czech_republic_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_czech_republic_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_czech_republic_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-218">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-218">Keywords</span></span>

#### <a name="keywords_czech_republic_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-219">Keywords_czech_republic_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-219">Keywords_czech_republic_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-220">돌 번호</span><span class="sxs-lookup"><span data-stu-id="de021-220">birth number</span></span>
  
<span data-ttu-id="de021-221">national identification number</span><span class="sxs-lookup"><span data-stu-id="de021-221">national identification number</span></span>
  
<span data-ttu-id="de021-222">개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="de021-222">personal identification number</span></span>
  
<span data-ttu-id="de021-223">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-223">social security number</span></span>
  
<span data-ttu-id="de021-224">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-224">nationalnumber#</span></span>
  
<span data-ttu-id="de021-225">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-225">ssn#</span></span>
  
<span data-ttu-id="de021-226">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-226">ssn</span></span>
  
<span data-ttu-id="de021-227">국가 번호</span><span class="sxs-lookup"><span data-stu-id="de021-227">national number</span></span>
  
<span data-ttu-id="de021-228">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-228">personal id number</span></span>
  
<span data-ttu-id="de021-229">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-229">personalidnumber#</span></span>
  
<span data-ttu-id="de021-230">rč</span><span class="sxs-lookup"><span data-stu-id="de021-230">rč</span></span>
  
<span data-ttu-id="de021-231">rodné číslo</span><span class="sxs-lookup"><span data-stu-id="de021-231">rodné číslo</span></span>
  
<span data-ttu-id="de021-232">rodne cislo</span><span class="sxs-lookup"><span data-stu-id="de021-232">rodne cislo</span></span>
  
## <a name="denmark"></a><span data-ttu-id="de021-233">덴마크</span><span class="sxs-lookup"><span data-stu-id="de021-233">Denmark</span></span>

### <a name="format"></a><span data-ttu-id="de021-234">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-234">Format</span></span>

<span data-ttu-id="de021-235">지정 된 패턴의 10 자리 및 하이픈</span><span class="sxs-lookup"><span data-stu-id="de021-235">Ten digits and a hyphen in the specified pattern</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-236">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-236">Pattern</span></span>

<span data-ttu-id="de021-237">10 자리 숫자와 하이픈:</span><span class="sxs-lookup"><span data-stu-id="de021-237">Ten digits and a hyphen:</span></span>
  
- <span data-ttu-id="de021-238">생년월일에 해당 하는 6 자리 숫자 (DDMMYY)</span><span class="sxs-lookup"><span data-stu-id="de021-238">Six digits that correspond to the birth date (DDMMYY)</span></span> 
    
- <span data-ttu-id="de021-239">하이픈</span><span class="sxs-lookup"><span data-stu-id="de021-239">A hyphen</span></span>
    
- <span data-ttu-id="de021-240">일련 번호에 해당 하는 4 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-240">Four digits that correspond to a sequence number</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-241">제외</span><span class="sxs-lookup"><span data-stu-id="de021-241">Checksum</span></span>

<span data-ttu-id="de021-242">예</span><span class="sxs-lookup"><span data-stu-id="de021-242">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-243">정의</span><span class="sxs-lookup"><span data-stu-id="de021-243">Definition</span></span>

<span data-ttu-id="de021-244">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-244">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-245">이 함수 `Func_denmark_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-245">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-246">From `Keywords_denmark_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-246">A keyword from  `Keywords_denmark_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-247">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-247">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-248">이 함수 `Func_denmark_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-248">The function  `Func_denmark_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_denmark_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_denmark_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-249">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-249">Keywords</span></span>

#### <a name="keywords_denmark_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-250">Keywords_denmark_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-250">Keywords_denmark_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-251">개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="de021-251">personal identification number</span></span>
  
<span data-ttu-id="de021-252">national identification number</span><span class="sxs-lookup"><span data-stu-id="de021-252">national identification number</span></span>
  
<span data-ttu-id="de021-253">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-253">social security number</span></span>
  
<span data-ttu-id="de021-254">nationalnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-254">nationalnumber#</span></span>
  
<span data-ttu-id="de021-255">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-255">ssn#</span></span>
  
<span data-ttu-id="de021-256">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-256">ssn</span></span>
  
<span data-ttu-id="de021-257">국가 번호</span><span class="sxs-lookup"><span data-stu-id="de021-257">national number</span></span>
  
<span data-ttu-id="de021-258">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-258">personal id number</span></span>
  
<span data-ttu-id="de021-259">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-259">personalidnumber#</span></span>
  
<span data-ttu-id="de021-260">cpr-nummer</span><span class="sxs-lookup"><span data-stu-id="de021-260">cpr-nummer</span></span>
  
<span data-ttu-id="de021-261">personnummer</span><span class="sxs-lookup"><span data-stu-id="de021-261">personnummer</span></span>
  
## <a name="finland"></a><span data-ttu-id="de021-262">핀란드</span><span class="sxs-lookup"><span data-stu-id="de021-262">Finland</span></span>

### <a name="format"></a><span data-ttu-id="de021-263">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-263">Format</span></span>

<span data-ttu-id="de021-264">지정 된 형식의 11 자 조합</span><span class="sxs-lookup"><span data-stu-id="de021-264">An 11-character combination in the specified format</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-265">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-265">Pattern</span></span>

<span data-ttu-id="de021-266">다음은 지정 된 형식의 11 자 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="de021-266">An 11-character combination in the specified format:</span></span>
  
-  <span data-ttu-id="de021-267">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-267">Six digits</span></span> 
    
- <span data-ttu-id="de021-268">다음 중 하나의 인스턴스에 대해 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-268">One instance of one of the following:</span></span>
    
  - <span data-ttu-id="de021-269">더하기 기호</span><span class="sxs-lookup"><span data-stu-id="de021-269">Plus symbol</span></span>
    
  - <span data-ttu-id="de021-270">빼기 기호</span><span class="sxs-lookup"><span data-stu-id="de021-270">Minus symbol</span></span>
    
  - <span data-ttu-id="de021-271">문자 "A" (대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="de021-271">The letter "A" (not case-sensitive)</span></span>
    
- <span data-ttu-id="de021-272">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-272">Three digits</span></span>
    
- <span data-ttu-id="de021-273">1 개의 문자 또는 1 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-273">One letter or one digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-274">제외</span><span class="sxs-lookup"><span data-stu-id="de021-274">Checksum</span></span>

<span data-ttu-id="de021-275">예</span><span class="sxs-lookup"><span data-stu-id="de021-275">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-276">정의</span><span class="sxs-lookup"><span data-stu-id="de021-276">Definition</span></span>

<span data-ttu-id="de021-277">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-277">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-278">이 함수 `Func_finland_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-278">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-279">From `Keywords_finland_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-279">A keyword from  `Keywords_finland_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-280">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-280">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-281">이 함수 `Func_finland_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-281">The function  `Func_finland_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_finland_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_finland_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-282">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-282">Keywords</span></span>

#### <a name="keywords_finland_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-283">Keywords_finland_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-283">Keywords_finland_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-284">identification number</span><span class="sxs-lookup"><span data-stu-id="de021-284">identification number</span></span>
  
<span data-ttu-id="de021-285">개인 id</span><span class="sxs-lookup"><span data-stu-id="de021-285">personal id</span></span>
  
<span data-ttu-id="de021-286">id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-286">identity number</span></span>
  
<span data-ttu-id="de021-287">핀란드어 국가 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-287">finnish national id number</span></span>
  
<span data-ttu-id="de021-288">personalidnumber #</span><span class="sxs-lookup"><span data-stu-id="de021-288">personalidnumber#</span></span>
  
<span data-ttu-id="de021-289">national identification number</span><span class="sxs-lookup"><span data-stu-id="de021-289">national identification number</span></span>
  
<span data-ttu-id="de021-290">id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-290">id number</span></span>
  
<span data-ttu-id="de021-291">국가 id 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="de021-291">national id no.</span></span>
  
<span data-ttu-id="de021-292">국가 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-292">national id number</span></span>
  
<span data-ttu-id="de021-293">id 없음</span><span class="sxs-lookup"><span data-stu-id="de021-293">id no</span></span>
  
<span data-ttu-id="de021-294">tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="de021-294">tunnistenumero</span></span>
  
<span data-ttu-id="de021-295">henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="de021-295">henkilötunnus</span></span>
  
<span data-ttu-id="de021-296">yksilöllinen henkilökohtainen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="de021-296">yksilöllinen henkilökohtainen tunnistenumero</span></span>
  
<span data-ttu-id="de021-297">ainutlaatuinen henkilökohtainen tunnus</span><span class="sxs-lookup"><span data-stu-id="de021-297">ainutlaatuinen henkilökohtainen tunnus</span></span>
  
<span data-ttu-id="de021-298">identiteetti numero</span><span class="sxs-lookup"><span data-stu-id="de021-298">identiteetti numero</span></span>
  
<span data-ttu-id="de021-299">suomen kansallinen henkilötunnus</span><span class="sxs-lookup"><span data-stu-id="de021-299">suomen kansallinen henkilötunnus</span></span>
  
<span data-ttu-id="de021-300">henkilötunnusnumero #</span><span class="sxs-lookup"><span data-stu-id="de021-300">henkilötunnusnumero#</span></span>
  
<span data-ttu-id="de021-301">kansallisen tunnistenumero</span><span class="sxs-lookup"><span data-stu-id="de021-301">kansallisen tunnistenumero</span></span>
  
<span data-ttu-id="de021-302">tunnusnumero</span><span class="sxs-lookup"><span data-stu-id="de021-302">tunnusnumero</span></span>
  
<span data-ttu-id="de021-303">kansallinen tunnus numero</span><span class="sxs-lookup"><span data-stu-id="de021-303">kansallinen tunnus numero</span></span>
  
<span data-ttu-id="de021-304">hetu</span><span class="sxs-lookup"><span data-stu-id="de021-304">hetu</span></span>
  
## <a name="france"></a><span data-ttu-id="de021-305">프랑스</span><span class="sxs-lookup"><span data-stu-id="de021-305">France</span></span>

<span data-ttu-id="de021-306">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"프랑스 사회 보장 번호 (INSEE)" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de021-306">For details, see the section "France Social Security Number (INSEE)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="germany"></a><span data-ttu-id="de021-307">독일</span><span class="sxs-lookup"><span data-stu-id="de021-307">Germany</span></span>

<span data-ttu-id="de021-308">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"독일 Id 카드 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de021-308">For details, see the section "Germany Identity Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="greece"></a><span data-ttu-id="de021-309">그리스</span><span class="sxs-lookup"><span data-stu-id="de021-309">Greece</span></span>

<span data-ttu-id="de021-310">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"그리스 국가 ID 카드" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de021-310">For details, see the section "Greece National ID Card" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="hungary"></a><span data-ttu-id="de021-311">헝가리</span><span class="sxs-lookup"><span data-stu-id="de021-311">Hungary</span></span>

### <a name="format"></a><span data-ttu-id="de021-312">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-312">Format</span></span>

<span data-ttu-id="de021-313">공백과 구분 기호를 사용 하지 않고 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-313">Nine digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-314">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-314">Pattern</span></span>

<span data-ttu-id="de021-315">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-315">Nine digits</span></span>
  
### <a name="checksum"></a><span data-ttu-id="de021-316">제외</span><span class="sxs-lookup"><span data-stu-id="de021-316">Checksum</span></span>

<span data-ttu-id="de021-317">예</span><span class="sxs-lookup"><span data-stu-id="de021-317">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-318">정의</span><span class="sxs-lookup"><span data-stu-id="de021-318">Definition</span></span>

<span data-ttu-id="de021-319">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-319">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-320">이 함수 `Func_hungary_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-320">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-321">From `Keywords_hungary_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-321">A keyword from  `Keywords_hungary_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-322">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-322">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-323">이 함수 `Func_hungary_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-323">The function  `Func_hungary_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_hungary_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_hungary_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-324">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-324">Keywords</span></span>

#### <a name="keywords_hungary_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-325">Keywords_hungary_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-325">Keywords_hungary_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-326">헝가리어 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="de021-326">hungarian social security number</span></span>
  
<span data-ttu-id="de021-327">social security number</span><span class="sxs-lookup"><span data-stu-id="de021-327">social security number</span></span>
  
<span data-ttu-id="de021-328">사회 alsecuritynumber #</span><span class="sxs-lookup"><span data-stu-id="de021-328">socialsecuritynumber#</span></span>
  
<span data-ttu-id="de021-329">hssn #</span><span class="sxs-lookup"><span data-stu-id="de021-329">hssn#</span></span>
  
<span data-ttu-id="de021-330">socialsecuritynno</span><span class="sxs-lookup"><span data-stu-id="de021-330">socialsecuritynno</span></span>
  
<span data-ttu-id="de021-331">hssn</span><span class="sxs-lookup"><span data-stu-id="de021-331">hssn</span></span>
  
<span data-ttu-id="de021-332">taj</span><span class="sxs-lookup"><span data-stu-id="de021-332">taj</span></span>
  
<span data-ttu-id="de021-333">taj #</span><span class="sxs-lookup"><span data-stu-id="de021-333">taj#</span></span>
  
<span data-ttu-id="de021-334">ssn</span><span class="sxs-lookup"><span data-stu-id="de021-334">ssn</span></span>
  
<span data-ttu-id="de021-335">ssn #</span><span class="sxs-lookup"><span data-stu-id="de021-335">ssn#</span></span>
  
<span data-ttu-id="de021-336">소셜 보안 아니요</span><span class="sxs-lookup"><span data-stu-id="de021-336">social security no</span></span>
  
<span data-ttu-id="de021-337">áfa</span><span class="sxs-lookup"><span data-stu-id="de021-337">áfa</span></span>
  
<span data-ttu-id="de021-338">közösségi adószám</span><span class="sxs-lookup"><span data-stu-id="de021-338">közösségi adószám</span></span>
  
<span data-ttu-id="de021-339">általános forgalmi adó</span><span class="sxs-lookup"><span data-stu-id="de021-339">általános forgalmi adó szám</span></span>
  
<span data-ttu-id="de021-340">hozzáadottérték adó</span><span class="sxs-lookup"><span data-stu-id="de021-340">hozzáadottérték adó</span></span>
  
<span data-ttu-id="de021-341">áfa szám</span><span class="sxs-lookup"><span data-stu-id="de021-341">áfa szám</span></span>
  
<span data-ttu-id="de021-342">magyar áfa szám</span><span class="sxs-lookup"><span data-stu-id="de021-342">magyar áfa szám</span></span>
  
## <a name="portugal"></a><span data-ttu-id="de021-343">포르투갈</span><span class="sxs-lookup"><span data-stu-id="de021-343">Portugal</span></span>

<span data-ttu-id="de021-344">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"포르투갈 시민이 카드 번호" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de021-344">For details, see the section "Portugal Citizen Card Number" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="spain"></a><span data-ttu-id="de021-345">스페인</span><span class="sxs-lookup"><span data-stu-id="de021-345">Spain</span></span>

<span data-ttu-id="de021-346">자세한 내용은 [중요 한 정보 유형이 찾는](what-the-sensitive-information-types-look-for.md)"스페인 SSN (사회 보장 번호)" 섹션을 참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="de021-346">For details, see the section "Spain Social Security Number (SSN)" in [What the sensitive information types look for](what-the-sensitive-information-types-look-for.md).</span></span>
  
## <a name="sweden"></a><span data-ttu-id="de021-347">스웨덴</span><span class="sxs-lookup"><span data-stu-id="de021-347">Sweden</span></span>

### <a name="format"></a><span data-ttu-id="de021-348">형식일</span><span class="sxs-lookup"><span data-stu-id="de021-348">Format</span></span>

<span data-ttu-id="de021-349">공백과 구분 기호를 사용 하지 않고 12 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="de021-349">12 digits without spaces and delimiters</span></span>
  
### <a name="pattern"></a><span data-ttu-id="de021-350">패턴</span><span class="sxs-lookup"><span data-stu-id="de021-350">Pattern</span></span>

<span data-ttu-id="de021-351">12자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="de021-351">12 digits:</span></span>
  
-  <span data-ttu-id="de021-352">출생 날짜에 해당 하는 8 자리 숫자 (YYYYMMDD)</span><span class="sxs-lookup"><span data-stu-id="de021-352">Eight digits that correspond to the birth date (YYYYMMDD)</span></span> 
    
- <span data-ttu-id="de021-353">일련 번호에 해당 하는 3 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="de021-353">Three digits that correspond to a serial number where:</span></span> 
    
  - <span data-ttu-id="de021-354">일련 번호의 마지막 숫자는 남성에 홀수를 할당 하는 성별과 암의 짝수를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="de021-354">The last digit in the serial number indicates gender by the assignment of an odd number for male and an even number for female</span></span>
    
  - <span data-ttu-id="de021-355">최대 1990의 일련 번호를 사용 하 여 전화를 corresponded 하는 국가, 즉 세금 레코드에 따라 (1947 이전에 태어난 경우)에는에 대 한 작업을 수행 하는 경우 (예를 들어 세금이 1947 기록 됨) immigrants</span><span class="sxs-lookup"><span data-stu-id="de021-355">Up to 1990, the assignment of serial number corresponded to the county where the bearer of the number was born or (if born before 1947) where he/she had been living, according to tax records, on January 1, 1947, with a special code (usually 9 as the 7th digit) for immigrants</span></span> 
    
- <span data-ttu-id="de021-356">검사 숫자 1 개</span><span class="sxs-lookup"><span data-stu-id="de021-356">One check digit</span></span>
    
### <a name="checksum"></a><span data-ttu-id="de021-357">제외</span><span class="sxs-lookup"><span data-stu-id="de021-357">Checksum</span></span>

<span data-ttu-id="de021-358">예</span><span class="sxs-lookup"><span data-stu-id="de021-358">Yes</span></span>
  
### <a name="definition"></a><span data-ttu-id="de021-359">정의</span><span class="sxs-lookup"><span data-stu-id="de021-359">Definition</span></span>

<span data-ttu-id="de021-360">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-360">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-361">이 함수 `Func_sweden_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-361">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
- <span data-ttu-id="de021-362">From `Keywords_sweden_eu_ssn_or_equivalent` 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-362">A keyword from  `Keywords_sweden_eu_ssn_or_equivalent` is found.</span></span> 
    
<span data-ttu-id="de021-363">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="de021-363">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
  
- <span data-ttu-id="de021-364">이 함수 `Func_sweden_eu_ssn_or_equivalent` 는 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="de021-364">The function  `Func_sweden_eu_ssn_or_equivalent` finds content that matches the pattern.</span></span> 
    
```
 <!-- EU SSN or Equivalent Number -->
<Entity id="d24e32a4-c0bb-4ba8-899d-6303b95742d9" patternsProximity="300" recommendedConfidence="75">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
          <Match idRef="Keywords_sweden_eu_ssn_or_equivalent" />
        </Pattern> 
       <Pattern confidenceLevel="75">
          <IdMatch idRef="Func_sweden_eu_ssn_or_equivalent" />
        </Pattern>      
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="de021-365">키워드</span><span class="sxs-lookup"><span data-stu-id="de021-365">Keywords</span></span>

#### <a name="keywords_sweden_eu_ssn_or_equivalent"></a><span data-ttu-id="de021-366">Keywords_sweden_eu_ssn_or_equivalent</span><span class="sxs-lookup"><span data-stu-id="de021-366">Keywords_sweden_eu_ssn_or_equivalent</span></span>

<span data-ttu-id="de021-367">개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="de021-367">personal id number</span></span>
  
<span data-ttu-id="de021-368">identification number</span><span class="sxs-lookup"><span data-stu-id="de021-368">identification number</span></span>
  
<span data-ttu-id="de021-369">개인 id 없음</span><span class="sxs-lookup"><span data-stu-id="de021-369">personal id no</span></span>
  
<span data-ttu-id="de021-370">identity no</span><span class="sxs-lookup"><span data-stu-id="de021-370">identity no</span></span>
  
<span data-ttu-id="de021-371">id 아니요</span><span class="sxs-lookup"><span data-stu-id="de021-371">identification no</span></span>
  
<span data-ttu-id="de021-372">개인 식별 아니요</span><span class="sxs-lookup"><span data-stu-id="de021-372">personal identification no</span></span>
  
<span data-ttu-id="de021-373">personnummer id</span><span class="sxs-lookup"><span data-stu-id="de021-373">personnummer id</span></span>
  
<span data-ttu-id="de021-374">personligt id-nummer</span><span class="sxs-lookup"><span data-stu-id="de021-374">personligt id-nummer</span></span>
  
<span data-ttu-id="de021-375">unikt id-nummer</span><span class="sxs-lookup"><span data-stu-id="de021-375">unikt id-nummer</span></span>
  
<span data-ttu-id="de021-376">personnummer</span><span class="sxs-lookup"><span data-stu-id="de021-376">personnummer</span></span>
  
<span data-ttu-id="de021-377">identifikationsnumret</span><span class="sxs-lookup"><span data-stu-id="de021-377">identifikationsnumret</span></span>
  
<span data-ttu-id="de021-378">personnummer #</span><span class="sxs-lookup"><span data-stu-id="de021-378">personnummer#</span></span>
  
<span data-ttu-id="de021-379">identifikationsnumret #</span><span class="sxs-lookup"><span data-stu-id="de021-379">identifikationsnumret#</span></span>
  
## <a name="see-also"></a><span data-ttu-id="de021-380">참고 항목</span><span class="sxs-lookup"><span data-stu-id="de021-380">See also</span></span>

[<span data-ttu-id="de021-381">중요한 정보 형식이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="de021-381">What the sensitive information types look for</span></span>](what-the-sensitive-information-types-look-for.md)

