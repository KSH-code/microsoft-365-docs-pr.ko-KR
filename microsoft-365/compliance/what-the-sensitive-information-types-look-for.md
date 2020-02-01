---
title: 중요 한 정보 형식을 찾습니다.
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
search.appverid: MET150
ms.topic: reference
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContainsSensitiveInformation
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Office 365 보안 &amp; 및 준수 센터의 dlp (데이터 손실 방지)에는 dlp 정책에서 사용할 준비가 된 80 중요 한 정보 유형이 포함 되어 있습니다. 이 항목에서는 이러한 모든 중요한 정보 유형의 목록과 DLP 정책이 이러한 각 유형을 검색할 때 찾는 내용을 보여 줍니다.
ms.openlocfilehash: efd5d2f8003bd79620118a6a058576e5593699b1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601215"
---
# <a name="what-the-sensitive-information-types-look-for"></a><span data-ttu-id="abc05-104">중요한 정보 형식이 찾는 항목</span><span class="sxs-lookup"><span data-stu-id="abc05-104">What the sensitive information types look for</span></span>

<span data-ttu-id="abc05-105">Office 365 보안 &amp; 및 준수 센터의 dlp (데이터 손실 방지)에는 dlp 정책에서 사용할 수 있는 중요 한 정보 유형이 많이 포함 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-105">Data loss prevention (DLP) in the Office 365 Security &amp; Compliance Center includes many sensitive information types that are ready for you to use in your DLP policies.</span></span> <span data-ttu-id="abc05-106">이 항목에서는 이러한 모든 중요한 정보 유형의 목록과 DLP 정책이 이러한 각 유형을 검색할 때 찾는 내용을 보여 줍니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-106">This topic lists all of these sensitive information types and shows what a DLP policy looks for when it detects each type.</span></span> <span data-ttu-id="abc05-107">중요한 정보 유형은 정규식이나 함수로 식별될 수 있는 패턴으로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-107">A sensitive information type is defined by a pattern that can be identified by a regular expression or a function.</span></span> <span data-ttu-id="abc05-108">또한 키워드 및 체크섬과 같은 확증적인 증거를 사용하여 중요한 정보 유형을 식별할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-108">In addition, corroborative evidence such as keywords and checksums can be used to identify a sensitive information type.</span></span> <span data-ttu-id="abc05-109">이러한 평가 프로세스에서 신뢰 수준 및 근접성도 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-109">Confidence level and proximity are also used in the evaluation process.</span></span>
  
## <a name="aba-routing-number"></a><span data-ttu-id="abc05-110">ABA 라우팅 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-110">ABA Routing Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-111">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-111">Format</span></span>

<span data-ttu-id="abc05-112">서식 있는 패턴 또는 서식 없는 패턴으로 표시될 수 있는 9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-112">9 digits which may be in a formatted or unformatted pattern</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-113">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-113">Pattern</span></span>

<span data-ttu-id="abc05-114">서식이</span><span class="sxs-lookup"><span data-stu-id="abc05-114">Formatted:</span></span>
- <span data-ttu-id="abc05-115">0, 1, 2, 3, 6, 7 또는 8로 시작하는 4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-115">Four digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span>
- <span data-ttu-id="abc05-116">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-116">A hyphen</span></span>
- <span data-ttu-id="abc05-117">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-117">Four digits</span></span>
- <span data-ttu-id="abc05-118">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-118">A hyphen</span></span>
- <span data-ttu-id="abc05-119">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-119">A digit</span></span>

<span data-ttu-id="abc05-120">서식 없음: 0, 1, 2, 3, 6, 7 또는 8로 시작 하는 9 개의 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-120">Unformatted: 9 consecutive digits beginning with 0, 1, 2, 3, 6, 7, or 8</span></span> 

### <a name="checksum"></a><span data-ttu-id="abc05-121">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-121">Checksum</span></span>

<span data-ttu-id="abc05-122">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-122">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-123">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-123">Definition</span></span>

<span data-ttu-id="abc05-124">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-124">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-125">Func_aba_routing 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-125">The function Func_aba_routing finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-126">Keyword_ABA_Routing의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-126">A keyword from Keyword_ABA_Routing is found.</span></span>

```xml
<!-- ABA Routing Number -->
<Entity id="cb353f78-2b72-4c3c-8827-92ebe4f69fdf" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_aba_routing" />
        <Match idRef="Keyword_ABA_Routing" />
      </Pattern>
 </Entity>
```


### <a name="keywords"></a><span data-ttu-id="abc05-127">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-127">Keywords</span></span>

#### <a name="keyword_aba_routing"></a><span data-ttu-id="abc05-128">Keyword_ABA_Routing</span><span class="sxs-lookup"><span data-stu-id="abc05-128">Keyword_ABA_Routing</span></span>

- <span data-ttu-id="abc05-129">aba</span><span class="sxs-lookup"><span data-stu-id="abc05-129">aba</span></span>
- <span data-ttu-id="abc05-130">aba #</span><span class="sxs-lookup"><span data-stu-id="abc05-130">aba #</span></span>
- <span data-ttu-id="abc05-131">aba routing #</span><span class="sxs-lookup"><span data-stu-id="abc05-131">aba routing #</span></span>
- <span data-ttu-id="abc05-132">aba routing number</span><span class="sxs-lookup"><span data-stu-id="abc05-132">aba routing number</span></span>
- <span data-ttu-id="abc05-133">aba #</span><span class="sxs-lookup"><span data-stu-id="abc05-133">aba#</span></span>
- <span data-ttu-id="abc05-134">abarouting #</span><span class="sxs-lookup"><span data-stu-id="abc05-134">abarouting#</span></span>
- <span data-ttu-id="abc05-135">aba number</span><span class="sxs-lookup"><span data-stu-id="abc05-135">aba number</span></span>
- <span data-ttu-id="abc05-136">abaroutingnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-136">abaroutingnumber</span></span>
- <span data-ttu-id="abc05-137">american bank association routing #</span><span class="sxs-lookup"><span data-stu-id="abc05-137">american bank association routing #</span></span>
- <span data-ttu-id="abc05-138">american bank association routing number</span><span class="sxs-lookup"><span data-stu-id="abc05-138">american bank association routing number</span></span>
- <span data-ttu-id="abc05-139">americanbankassociationrouting #</span><span class="sxs-lookup"><span data-stu-id="abc05-139">americanbankassociationrouting#</span></span>
- <span data-ttu-id="abc05-140">americanbankassociationroutingnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-140">americanbankassociationroutingnumber</span></span>
- <span data-ttu-id="abc05-141">bank routing number</span><span class="sxs-lookup"><span data-stu-id="abc05-141">bank routing number</span></span>
- <span data-ttu-id="abc05-142">bankrouting #</span><span class="sxs-lookup"><span data-stu-id="abc05-142">bankrouting#</span></span>
- <span data-ttu-id="abc05-143">bankroutingnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-143">bankroutingnumber</span></span>
- <span data-ttu-id="abc05-144">routing transit number</span><span class="sxs-lookup"><span data-stu-id="abc05-144">routing transit number</span></span>
- <span data-ttu-id="abc05-145">RTN</span><span class="sxs-lookup"><span data-stu-id="abc05-145">RTN</span></span> 
   
## <a name="argentina-national-identity-dni-number"></a><span data-ttu-id="abc05-146">아르헨티나 국가 ID(DNI) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-146">Argentina National Identity (DNI) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-147">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-147">Format</span></span>

<span data-ttu-id="abc05-148">마침표로 구분된 8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-148">Eight digits separated by periods</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-149">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-149">Pattern</span></span>

<span data-ttu-id="abc05-150">8자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-150">Eight digits:</span></span>
- <span data-ttu-id="abc05-151">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-151">Two digits</span></span>
- <span data-ttu-id="abc05-152">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-152">A period</span></span>
- <span data-ttu-id="abc05-153">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-153">Three digits</span></span>
- <span data-ttu-id="abc05-154">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-154">A period</span></span>
- <span data-ttu-id="abc05-155">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-155">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-156">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-156">Checksum</span></span>

<span data-ttu-id="abc05-157">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-157">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-158">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-158">Definition</span></span>

<span data-ttu-id="abc05-159">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-159">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-160">정규식 Regex_argentina_national_id 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-160">The regular expression Regex_argentina_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-161">Keyword_argentina_national_id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-161">A keyword from Keyword_argentina_national_id is found.</span></span>

```xml
<!-- Argentina National Identity (DNI) Number -->
<Entity id="eefbb00e-8282-433c-8620-8f1da3bffdb2" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_argentina_national_id"/>
      <Match idRef="Keyword_argentina_national_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-162">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-162">Keywords</span></span>

#### <a name="keyword_argentina_national_id"></a><span data-ttu-id="abc05-163">Keyword_argentina_national_id</span><span class="sxs-lookup"><span data-stu-id="abc05-163">Keyword_argentina_national_id</span></span>

- <span data-ttu-id="abc05-164">Argentina National Identity number</span><span class="sxs-lookup"><span data-stu-id="abc05-164">Argentina National Identity number</span></span> 
- <span data-ttu-id="abc05-165">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-165">Identity</span></span> 
- <span data-ttu-id="abc05-166">식별 국가 Id 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-166">Identification National Identity Card</span></span> 
- <span data-ttu-id="abc05-167">DNI</span><span class="sxs-lookup"><span data-stu-id="abc05-167">DNI</span></span> 
- <span data-ttu-id="abc05-168">개인의 NIC 국내 레지스트리</span><span class="sxs-lookup"><span data-stu-id="abc05-168">NIC National Registry of Persons</span></span> 
- <span data-ttu-id="abc05-169">Documento Nacional de Identidad</span><span class="sxs-lookup"><span data-stu-id="abc05-169">Documento Nacional de Identidad</span></span> 
- <span data-ttu-id="abc05-170">Registro Nacional de las Personas</span><span class="sxs-lookup"><span data-stu-id="abc05-170">Registro Nacional de las Personas</span></span> 
- <span data-ttu-id="abc05-171">Identidad</span><span class="sxs-lookup"><span data-stu-id="abc05-171">Identidad</span></span> 
- <span data-ttu-id="abc05-172">Identificación</span><span class="sxs-lookup"><span data-stu-id="abc05-172">Identificación</span></span> 
   
## <a name="australia-bank-account-number"></a><span data-ttu-id="abc05-173">호주 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-173">Australia Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-174">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-174">Format</span></span>

<span data-ttu-id="abc05-175">6-10자리 숫자(은행 지점 번호 포함 또는 제외)</span><span class="sxs-lookup"><span data-stu-id="abc05-175">6-10 digits with or without a bank state branch number</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-176">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-176">Pattern</span></span>

<span data-ttu-id="abc05-177">계좌 번호는 6-10자리 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-177">Account number is 6-10 digits.</span></span>
<span data-ttu-id="abc05-178">호주 은행 지점 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-178">Australia bank state branch number:</span></span>
- <span data-ttu-id="abc05-179">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-179">Three digits</span></span> 
- <span data-ttu-id="abc05-180">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-180">A hyphen</span></span> 
- <span data-ttu-id="abc05-181">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-181">Three digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-182">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-182">Checksum</span></span>

<span data-ttu-id="abc05-183">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-183">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-184">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-184">Definition</span></span>

<span data-ttu-id="abc05-185">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-185">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-186">Regex_australia_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-186">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="abc05-187">Keyword_australia_bank_account_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-187">A keyword from Keyword_australia_bank_account_number is found.</span></span>
- <span data-ttu-id="abc05-188">Regex_australia_bank_account_number_bsb 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-188">The regular expression Regex_australia_bank_account_number_bsb finds content that matches the pattern.</span></span>

<span data-ttu-id="abc05-189">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-189">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-190">Regex_australia_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-190">The regular expression Regex_australia_bank_account_number finds content that matches the pattern..</span></span>
- <span data-ttu-id="abc05-191">Keyword_australia_bank_account_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-191">A keyword from Keyword_australia_bank_account_number is found.</span></span>

```xml
<!-- Australia Bank Account Number -->
<Entity id="74a54de9-2a30-4aa0-a8aa-3d9327fc07c7" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
        <Match idRef="Regex_australia_bank_account_number_bsb" />
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_bank_account_number" />
        <Match idRef="Keyword_australia_bank_account_number" />
  </Pattern>
 </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-192">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-192">Keywords</span></span>

#### <a name="keyword_australia_bank_account_number"></a><span data-ttu-id="abc05-193">Keyword_australia_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="abc05-193">Keyword_australia_bank_account_number</span></span>

- <span data-ttu-id="abc05-194">swift bank code</span><span class="sxs-lookup"><span data-stu-id="abc05-194">swift bank code</span></span>
- <span data-ttu-id="abc05-195">correspondent bank</span><span class="sxs-lookup"><span data-stu-id="abc05-195">correspondent bank</span></span>
- <span data-ttu-id="abc05-196">base currency</span><span class="sxs-lookup"><span data-stu-id="abc05-196">base currency</span></span>
- <span data-ttu-id="abc05-197">usa account</span><span class="sxs-lookup"><span data-stu-id="abc05-197">usa account</span></span>
- <span data-ttu-id="abc05-198">holder address</span><span class="sxs-lookup"><span data-stu-id="abc05-198">holder address</span></span>
- <span data-ttu-id="abc05-199">bank address</span><span class="sxs-lookup"><span data-stu-id="abc05-199">bank address</span></span>
- <span data-ttu-id="abc05-200">information account</span><span class="sxs-lookup"><span data-stu-id="abc05-200">information account</span></span>
- <span data-ttu-id="abc05-201">fund transfers</span><span class="sxs-lookup"><span data-stu-id="abc05-201">fund transfers</span></span>
- <span data-ttu-id="abc05-202">bank charges</span><span class="sxs-lookup"><span data-stu-id="abc05-202">bank charges</span></span>
- <span data-ttu-id="abc05-203">bank details</span><span class="sxs-lookup"><span data-stu-id="abc05-203">bank details</span></span>
- <span data-ttu-id="abc05-204">banking information</span><span class="sxs-lookup"><span data-stu-id="abc05-204">banking information</span></span>
- <span data-ttu-id="abc05-205">full names</span><span class="sxs-lookup"><span data-stu-id="abc05-205">full names</span></span>
- <span data-ttu-id="abc05-206">iaea</span><span class="sxs-lookup"><span data-stu-id="abc05-206">iaea</span></span>

   
## <a name="australia-drivers-license-number"></a><span data-ttu-id="abc05-207">호주 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-207">Australia Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-208">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-208">Format</span></span>

<span data-ttu-id="abc05-209">9개의 문자 및 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-209">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-210">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-210">Pattern</span></span>

<span data-ttu-id="abc05-211">9개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-211">Nine letters and digits:</span></span> 

- <span data-ttu-id="abc05-212">2자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-212">Two digits or letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-213">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-213">Two digits</span></span> 
- <span data-ttu-id="abc05-214">5자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-214">Five digits or letters (not case sensitive)</span></span>

<span data-ttu-id="abc05-215">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-215">OR</span></span>

- <span data-ttu-id="abc05-216">1-2개의 선택적 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-216">1-2 optional letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-217">4-9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-217">4-9 digits</span></span>

<span data-ttu-id="abc05-218">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-218">OR</span></span>

- <span data-ttu-id="abc05-219">9자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-219">Nine digits or letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-220">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-220">Checksum</span></span>

<span data-ttu-id="abc05-221">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-221">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-222">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-222">Definition</span></span>

<span data-ttu-id="abc05-223">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-223">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-224">Regex_australia_drivers_license_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-224">The regular expression Regex_australia_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-225">Keyword_australia_drivers_license_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-225">A keyword from Keyword_australia_drivers_license_number is found.</span></span>
- <span data-ttu-id="abc05-226">Keyword_australia_drivers_license_number_exclusions의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-226">No keyword from Keyword_australia_drivers_license_number_exclusions is found.</span></span>

```xml
<!-- Australia Drivers License Number -->
<Entity id="1cbbc8f5-9216-4392-9eb5-5ac2298d1356" patternsProximity="300" recommendedConfidence="75">
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_drivers_license_number" />
        <Match idRef="Keyword_australia_drivers_license_number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_australia_drivers_license_number_exclusions" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-227">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-227">Keywords</span></span>

#### <a name="keyword_australia_drivers_license_number"></a><span data-ttu-id="abc05-228">Keyword_australia_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="abc05-228">Keyword_australia_drivers_license_number</span></span>

- <span data-ttu-id="abc05-229">international driving permits</span><span class="sxs-lookup"><span data-stu-id="abc05-229">international driving permits</span></span>
- <span data-ttu-id="abc05-230">australian automobile association</span><span class="sxs-lookup"><span data-stu-id="abc05-230">australian automobile association</span></span>
- <span data-ttu-id="abc05-231">international driving permit</span><span class="sxs-lookup"><span data-stu-id="abc05-231">international driving permit</span></span>
- <span data-ttu-id="abc05-232">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="abc05-232">DriverLicence</span></span>
- <span data-ttu-id="abc05-233">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-233">DriverLicences</span></span>
- <span data-ttu-id="abc05-234">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-234">Driver Lic</span></span>
- <span data-ttu-id="abc05-235">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-235">Driver Licence</span></span>
- <span data-ttu-id="abc05-236">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-236">Driver Licences</span></span>
- <span data-ttu-id="abc05-237">DriversLic</span><span class="sxs-lookup"><span data-stu-id="abc05-237">DriversLic</span></span>
- <span data-ttu-id="abc05-238">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-238">DriversLicence</span></span>
- <span data-ttu-id="abc05-239">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-239">DriversLicences</span></span>
- <span data-ttu-id="abc05-240">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-240">Drivers Lic</span></span>
- <span data-ttu-id="abc05-241">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-241">Drivers Lics</span></span>
- <span data-ttu-id="abc05-242">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-242">Drivers Licence</span></span>
- <span data-ttu-id="abc05-243">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-243">Drivers Licences</span></span>
- <span data-ttu-id="abc05-244">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-244">Driver'Lic</span></span>
- <span data-ttu-id="abc05-245">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-245">Driver'Lics</span></span>
- <span data-ttu-id="abc05-246">Driver' 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-246">Driver'Licence</span></span>
- <span data-ttu-id="abc05-247">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-247">Driver'Licences</span></span>
- <span data-ttu-id="abc05-248">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-248">Driver' Lic</span></span>
- <span data-ttu-id="abc05-249">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-249">Driver' Lics</span></span>
- <span data-ttu-id="abc05-250">Driver' Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-250">Driver' Licence</span></span>
- <span data-ttu-id="abc05-251">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-251">Driver' Licences</span></span>
- <span data-ttu-id="abc05-252">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="abc05-252">Driver'sLic</span></span>
- <span data-ttu-id="abc05-253">Drivers (Slics)</span><span class="sxs-lookup"><span data-stu-id="abc05-253">Driver'sLics</span></span>
- <span data-ttu-id="abc05-254">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="abc05-254">Driver'sLicence</span></span>
- <span data-ttu-id="abc05-255">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-255">Driver'sLicences</span></span>
- <span data-ttu-id="abc05-256">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-256">Driver's Lic</span></span>
- <span data-ttu-id="abc05-257">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-257">Driver's Lics</span></span>
- <span data-ttu-id="abc05-258">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-258">Driver's Licence</span></span>
- <span data-ttu-id="abc05-259">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-259">Driver's Licences</span></span>
- <span data-ttu-id="abc05-260">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-260">DriverLic#</span></span>
- <span data-ttu-id="abc05-261">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-261">DriverLics#</span></span>
- <span data-ttu-id="abc05-262">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="abc05-262">DriverLicence#</span></span>
- <span data-ttu-id="abc05-263">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-263">DriverLicences#</span></span>
- <span data-ttu-id="abc05-264">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-264">Driver Lic#</span></span>
- <span data-ttu-id="abc05-265">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-265">Driver Lics#</span></span>
- <span data-ttu-id="abc05-266">Driver Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-266">Driver Licence#</span></span>
- <span data-ttu-id="abc05-267">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-267">Driver Licences#</span></span>
- <span data-ttu-id="abc05-268">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-268">DriversLic#</span></span>
- <span data-ttu-id="abc05-269">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-269">DriversLics#</span></span>
- <span data-ttu-id="abc05-270">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-270">DriversLicence#</span></span>
- <span data-ttu-id="abc05-271">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-271">DriversLicences#</span></span>
- <span data-ttu-id="abc05-272">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-272">Drivers Lic#</span></span>
- <span data-ttu-id="abc05-273">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-273">Drivers Lics#</span></span>
- <span data-ttu-id="abc05-274">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-274">Drivers Licence#</span></span>
- <span data-ttu-id="abc05-275">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-275">Drivers Licences#</span></span>
- <span data-ttu-id="abc05-276">Driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="abc05-276">Driver'Lic#</span></span>
- <span data-ttu-id="abc05-277">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="abc05-277">Driver'Lics#</span></span>
- <span data-ttu-id="abc05-278">Driver' 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-278">Driver'Licence#</span></span>
- <span data-ttu-id="abc05-279">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="abc05-279">Driver'Licences#</span></span>
- <span data-ttu-id="abc05-280">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-280">Driver' Lic#</span></span>
- <span data-ttu-id="abc05-281">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-281">Driver' Lics#</span></span>
- <span data-ttu-id="abc05-282">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-282">Driver' Licence#</span></span>
- <span data-ttu-id="abc05-283">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-283">Driver' Licences#</span></span>
- <span data-ttu-id="abc05-284">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-284">Driver'sLic#</span></span>
- <span data-ttu-id="abc05-285">Drivers (Slics) #</span><span class="sxs-lookup"><span data-stu-id="abc05-285">Driver'sLics#</span></span>
- <span data-ttu-id="abc05-286">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="abc05-286">Driver'sLicence#</span></span>
- <span data-ttu-id="abc05-287">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-287">Driver'sLicences#</span></span>
- <span data-ttu-id="abc05-288">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-288">Driver's Lic#</span></span>
- <span data-ttu-id="abc05-289">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-289">Driver's Lics#</span></span>
- <span data-ttu-id="abc05-290">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-290">Driver's Licence#</span></span>
- <span data-ttu-id="abc05-291">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-291">Driver's Licences#</span></span> 

#### <a name="keyword_australia_drivers_license_number_exclusions"></a><span data-ttu-id="abc05-292">Keyword_australia_drivers_license_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="abc05-292">Keyword_australia_drivers_license_number_exclusions</span></span>

- <span data-ttu-id="abc05-293">aaa</span><span class="sxs-lookup"><span data-stu-id="abc05-293">aaa</span></span>
- <span data-ttu-id="abc05-294">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-294">DriverLicense</span></span>
- <span data-ttu-id="abc05-295">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-295">DriverLicenses</span></span>
- <span data-ttu-id="abc05-296">Driver License</span><span class="sxs-lookup"><span data-stu-id="abc05-296">Driver License</span></span>
- <span data-ttu-id="abc05-297">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-297">Driver Licenses</span></span>
- <span data-ttu-id="abc05-298">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-298">DriversLicense</span></span>
- <span data-ttu-id="abc05-299">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-299">DriversLicenses</span></span>
- <span data-ttu-id="abc05-300">Drivers License</span><span class="sxs-lookup"><span data-stu-id="abc05-300">Drivers License</span></span>
- <span data-ttu-id="abc05-301">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-301">Drivers Licenses</span></span>
- <span data-ttu-id="abc05-302">Driver' 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-302">Driver'License</span></span>
- <span data-ttu-id="abc05-303">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-303">Driver'Licenses</span></span>
- <span data-ttu-id="abc05-304">Driver' License</span><span class="sxs-lookup"><span data-stu-id="abc05-304">Driver' License</span></span>
- <span data-ttu-id="abc05-305">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-305">Driver' Licenses</span></span>
- <span data-ttu-id="abc05-306">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-306">Driver'sLicense</span></span>
- <span data-ttu-id="abc05-307">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-307">Driver'sLicenses</span></span>
- <span data-ttu-id="abc05-308">Driver's License</span><span class="sxs-lookup"><span data-stu-id="abc05-308">Driver's License</span></span>
- <span data-ttu-id="abc05-309">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-309">Driver's Licenses</span></span>
- <span data-ttu-id="abc05-310">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-310">DriverLicense#</span></span>
- <span data-ttu-id="abc05-311">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-311">DriverLicenses#</span></span>
- <span data-ttu-id="abc05-312">Driver License#</span><span class="sxs-lookup"><span data-stu-id="abc05-312">Driver License#</span></span>
- <span data-ttu-id="abc05-313">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-313">Driver Licenses#</span></span>
- <span data-ttu-id="abc05-314">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-314">DriversLicense#</span></span>
- <span data-ttu-id="abc05-315">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-315">DriversLicenses#</span></span>
- <span data-ttu-id="abc05-316">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="abc05-316">Drivers License#</span></span>
- <span data-ttu-id="abc05-317">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-317">Drivers Licenses#</span></span>
- <span data-ttu-id="abc05-318">Driver' 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-318">Driver'License#</span></span>
- <span data-ttu-id="abc05-319">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-319">Driver'Licenses#</span></span>
- <span data-ttu-id="abc05-320">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="abc05-320">Driver' License#</span></span>
- <span data-ttu-id="abc05-321">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-321">Driver' Licenses#</span></span>
- <span data-ttu-id="abc05-322">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-322">Driver'sLicense#</span></span>
- <span data-ttu-id="abc05-323">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-323">Driver'sLicenses#</span></span>
- <span data-ttu-id="abc05-324">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="abc05-324">Driver's License#</span></span>
- <span data-ttu-id="abc05-325">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-325">Driver's Licenses#</span></span>
   
## <a name="australia-medical-account-number"></a><span data-ttu-id="abc05-326">호주 의료 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-326">Australia Medical Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-327">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-327">Format</span></span>

<span data-ttu-id="abc05-328">10-11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-328">10-11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-329">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-329">Pattern</span></span>

<span data-ttu-id="abc05-330">10-11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-330">10-11 digits:</span></span>
- <span data-ttu-id="abc05-331">첫 번째 숫자는 2-6 범위에 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-331">First digit is in the range 2-6</span></span>
- <span data-ttu-id="abc05-332">9번째 숫자는 검사 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-332">Ninth digit is a check digit</span></span>
- <span data-ttu-id="abc05-333">10번째 숫자는 문제 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-333">Tenth digit is the issue digit</span></span>
- <span data-ttu-id="abc05-334">11번째 숫자(선택 사항)는 개인 번호입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-334">Eleventh digit (optional) is the individual number</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-335">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-335">Checksum</span></span>

<span data-ttu-id="abc05-336">예</span><span class="sxs-lookup"><span data-stu-id="abc05-336">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-337">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-337">Definition</span></span>

<span data-ttu-id="abc05-338">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-338">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-339">Func_australian_medical_account_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-339">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-340">Keyword_Australia_Medical_Account_Number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-340">A keyword from Keyword_Australia_Medical_Account_Number is found.</span></span>
- <span data-ttu-id="abc05-341">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-341">The checksum passes.</span></span>

<span data-ttu-id="abc05-342">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-342">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-343">Func_australian_medical_account_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-343">The function Func_australian_medical_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-344">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-344">The checksum passes.</span></span>

```xml
  <!-- Australia Medical Account Number -->
<Entity id="104a99a0-3d3b-4542-a40d-ab0b9e1efe63" recommendedConfidence="85" patternsProximity="300">
    <Pattern confidenceLevel="95">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="1">
     <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
<Pattern confidenceLevel="85">
     <IdMatch idRef="Func_australian_medical_account_number"/>
     <Any minMatches="0" maxMatches="0">
  <Match idRef="Keyword_Australia_Medical_Account_Number"/>
     </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-345">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-345">Keywords</span></span>

#### <a name="keyword_australia_medical_account_number"></a><span data-ttu-id="abc05-346">Keyword_Australia_Medical_Account_Number</span><span class="sxs-lookup"><span data-stu-id="abc05-346">Keyword_Australia_Medical_Account_Number</span></span>

- <span data-ttu-id="abc05-347">bank account details</span><span class="sxs-lookup"><span data-stu-id="abc05-347">bank account details</span></span>
- <span data-ttu-id="abc05-348">medicare payments</span><span class="sxs-lookup"><span data-stu-id="abc05-348">medicare payments</span></span>
- <span data-ttu-id="abc05-349">mortgage account</span><span class="sxs-lookup"><span data-stu-id="abc05-349">mortgage account</span></span>
- <span data-ttu-id="abc05-350">bank payments</span><span class="sxs-lookup"><span data-stu-id="abc05-350">bank payments</span></span>
- <span data-ttu-id="abc05-351">information branch</span><span class="sxs-lookup"><span data-stu-id="abc05-351">information branch</span></span>
- <span data-ttu-id="abc05-352">credit card loan</span><span class="sxs-lookup"><span data-stu-id="abc05-352">credit card loan</span></span>
- <span data-ttu-id="abc05-353">department of human services</span><span class="sxs-lookup"><span data-stu-id="abc05-353">department of human services</span></span>
- <span data-ttu-id="abc05-354">local service</span><span class="sxs-lookup"><span data-stu-id="abc05-354">local service</span></span>
- <span data-ttu-id="abc05-355">medicare</span><span class="sxs-lookup"><span data-stu-id="abc05-355">medicare</span></span>

   
## <a name="australia-passport-number"></a><span data-ttu-id="abc05-356">호주 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-356">Australia Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-357">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-357">Format</span></span>

<span data-ttu-id="abc05-358">문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-358">A letter followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-359">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-359">Pattern</span></span>

<span data-ttu-id="abc05-360">1개의 문자(대/소문자 구분 안 함)와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-360">A letter (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-361">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-361">Checksum</span></span>

<span data-ttu-id="abc05-362">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-362">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-363">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-363">Definition</span></span>

<span data-ttu-id="abc05-364">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-364">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-365">Regex_australia_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-365">The regular expression Regex_australia_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-366">Keyword_passport 또는 Keyword_australia_passport_number의 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-366">A keyword from Keyword_passport or Keyword_australia_passport_number is found.</span></span>

```xml
<!-- Australia Passport Number -->
<Entity id="29869db6-602d-4853-ab93-3484f905df50" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_australia_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_australia_passport_number" />
        </Any>
   </Pattern>
</Entity>   
```

### <a name="keywords"></a><span data-ttu-id="abc05-367">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-367">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="abc05-368">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-368">Keyword_passport</span></span>

- <span data-ttu-id="abc05-369">Passport Number</span><span class="sxs-lookup"><span data-stu-id="abc05-369">Passport Number</span></span>
- <span data-ttu-id="abc05-370">Passport No</span><span class="sxs-lookup"><span data-stu-id="abc05-370">Passport No</span></span>
- <span data-ttu-id="abc05-371">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-371">Passport #</span></span>
- <span data-ttu-id="abc05-372">여권 #</span><span class="sxs-lookup"><span data-stu-id="abc05-372">Passport#</span></span>
- <span data-ttu-id="abc05-373">PassportID</span><span class="sxs-lookup"><span data-stu-id="abc05-373">PassportID</span></span>
- <span data-ttu-id="abc05-374">Passportno</span><span class="sxs-lookup"><span data-stu-id="abc05-374">Passportno</span></span>
- <span data-ttu-id="abc05-375">passportnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-375">passportnumber</span></span>
- <span data-ttu-id="abc05-376">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-376">パスポート</span></span>
- <span data-ttu-id="abc05-377">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-377">パスポート番号</span></span>
- <span data-ttu-id="abc05-378">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-378">パスポートのNum</span></span>
- <span data-ttu-id="abc05-379">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="abc05-379">パスポート ＃</span></span> 
- <span data-ttu-id="abc05-380">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="abc05-380">Numéro de passeport</span></span>
- <span data-ttu-id="abc05-381">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="abc05-381">Passeport n °</span></span>
- <span data-ttu-id="abc05-382">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="abc05-382">Passeport Non</span></span>
- <span data-ttu-id="abc05-383">Passeport #</span><span class="sxs-lookup"><span data-stu-id="abc05-383">Passeport #</span></span>
- <span data-ttu-id="abc05-384">포트 #</span><span class="sxs-lookup"><span data-stu-id="abc05-384">Passeport#</span></span>
- <span data-ttu-id="abc05-385">지/포트 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-385">PasseportNon</span></span>
- <span data-ttu-id="abc05-386">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="abc05-386">Passeportn °</span></span>

#### <a name="keyword_australia_passport_number"></a><span data-ttu-id="abc05-387">Keyword_australia_passport_number</span><span class="sxs-lookup"><span data-stu-id="abc05-387">Keyword_australia_passport_number</span></span>

- <span data-ttu-id="abc05-388">여권</span><span class="sxs-lookup"><span data-stu-id="abc05-388">passport</span></span>
- <span data-ttu-id="abc05-389">passport details</span><span class="sxs-lookup"><span data-stu-id="abc05-389">passport details</span></span>
- <span data-ttu-id="abc05-390">immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="abc05-390">immigration and citizenship</span></span>
- <span data-ttu-id="abc05-391">commonwealth of australia</span><span class="sxs-lookup"><span data-stu-id="abc05-391">commonwealth of australia</span></span>
- <span data-ttu-id="abc05-392">department of immigration</span><span class="sxs-lookup"><span data-stu-id="abc05-392">department of immigration</span></span>
- <span data-ttu-id="abc05-393">residential address</span><span class="sxs-lookup"><span data-stu-id="abc05-393">residential address</span></span>
- <span data-ttu-id="abc05-394">department of immigration and citizenship</span><span class="sxs-lookup"><span data-stu-id="abc05-394">department of immigration and citizenship</span></span>
- <span data-ttu-id="abc05-395">visa</span><span class="sxs-lookup"><span data-stu-id="abc05-395">visa</span></span>
- <span data-ttu-id="abc05-396">national identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-396">national identity card</span></span>
- <span data-ttu-id="abc05-397">passport number</span><span class="sxs-lookup"><span data-stu-id="abc05-397">passport number</span></span>
- <span data-ttu-id="abc05-398">travel document</span><span class="sxs-lookup"><span data-stu-id="abc05-398">travel document</span></span>
- <span data-ttu-id="abc05-399">issuing authority</span><span class="sxs-lookup"><span data-stu-id="abc05-399">issuing authority</span></span>
   
## <a name="australia-tax-file-number"></a><span data-ttu-id="abc05-400">호주 세금 파일 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-400">Australia Tax File Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-401">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-401">Format</span></span>

<span data-ttu-id="abc05-402">8-9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-402">8-9 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-403">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-403">Pattern</span></span>

<span data-ttu-id="abc05-404">일반적으로 다음과 같이 공백과 함께 표시되는 8-9자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-404">8-9 digits typically presented with spaces as follows:</span></span>
- <span data-ttu-id="abc05-405">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-405">Three digits</span></span> 
- <span data-ttu-id="abc05-406">선택적 공백 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-406">An optional space</span></span> 
- <span data-ttu-id="abc05-407">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-407">Three digits</span></span> 
- <span data-ttu-id="abc05-408">선택적 공백 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-408">An optional space</span></span> 
- <span data-ttu-id="abc05-409">마지막 숫자가 검사 숫자인 2-3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-409">2-3 digits where the last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-410">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-410">Checksum</span></span>

<span data-ttu-id="abc05-411">예</span><span class="sxs-lookup"><span data-stu-id="abc05-411">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-412">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-412">Definition</span></span>

<span data-ttu-id="abc05-413">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-413">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-414">Func_australian_tax_file_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-414">The function Func_australian_tax_file_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-415">Keyword_Australia_Tax_File_Number 또는 Keyword_number_exclusions의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-415">No keyword from Keyword_Australia_Tax_File_Number or Keyword_number_exclusions is found.</span></span>
- <span data-ttu-id="abc05-416">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-416">The checksum passes.</span></span>

```xml
   <!-- Australia Tax File Number -->
    <Entity id="e29bc95f-ff70-4a37-aa01-04d17360a4c5" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_australian_tax_file_number" />
        <Match idRef="Keyword_Australia_Tax_File_Number" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_number_exclusions" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-417">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-417">Keywords</span></span>

#### <a name="keyword_australia_tax_file_number"></a><span data-ttu-id="abc05-418">Keyword_Australia_Tax_File_Number</span><span class="sxs-lookup"><span data-stu-id="abc05-418">Keyword_Australia_Tax_File_Number</span></span>

- <span data-ttu-id="abc05-419">australian business number</span><span class="sxs-lookup"><span data-stu-id="abc05-419">australian business number</span></span>
- <span data-ttu-id="abc05-420">marginal tax rate</span><span class="sxs-lookup"><span data-stu-id="abc05-420">marginal tax rate</span></span>
- <span data-ttu-id="abc05-421">medicare levy</span><span class="sxs-lookup"><span data-stu-id="abc05-421">medicare levy</span></span>
- <span data-ttu-id="abc05-422">portfolio number</span><span class="sxs-lookup"><span data-stu-id="abc05-422">portfolio number</span></span>
- <span data-ttu-id="abc05-423">service veterans</span><span class="sxs-lookup"><span data-stu-id="abc05-423">service veterans</span></span>
- <span data-ttu-id="abc05-424">withholding tax</span><span class="sxs-lookup"><span data-stu-id="abc05-424">withholding tax</span></span>
- <span data-ttu-id="abc05-425">individual tax return</span><span class="sxs-lookup"><span data-stu-id="abc05-425">individual tax return</span></span>
- <span data-ttu-id="abc05-426">tax file number</span><span class="sxs-lookup"><span data-stu-id="abc05-426">tax file number</span></span>

#### <a name="keyword_number_exclusions"></a><span data-ttu-id="abc05-427">Keyword_number_exclusions</span><span class="sxs-lookup"><span data-stu-id="abc05-427">Keyword_number_exclusions</span></span>

- <span data-ttu-id="abc05-428">00000000</span><span class="sxs-lookup"><span data-stu-id="abc05-428">00000000</span></span>
- <span data-ttu-id="abc05-429">11111111</span><span class="sxs-lookup"><span data-stu-id="abc05-429">11111111</span></span>
- <span data-ttu-id="abc05-430">22222222</span><span class="sxs-lookup"><span data-stu-id="abc05-430">22222222</span></span>
- <span data-ttu-id="abc05-431">33333333</span><span class="sxs-lookup"><span data-stu-id="abc05-431">33333333</span></span>
- <span data-ttu-id="abc05-432">44444444</span><span class="sxs-lookup"><span data-stu-id="abc05-432">44444444</span></span>
- <span data-ttu-id="abc05-433">55555555</span><span class="sxs-lookup"><span data-stu-id="abc05-433">55555555</span></span>
- <span data-ttu-id="abc05-434">66666666</span><span class="sxs-lookup"><span data-stu-id="abc05-434">66666666</span></span>
- <span data-ttu-id="abc05-435">77777777</span><span class="sxs-lookup"><span data-stu-id="abc05-435">77777777</span></span>
- <span data-ttu-id="abc05-436">88888888</span><span class="sxs-lookup"><span data-stu-id="abc05-436">88888888</span></span>
- <span data-ttu-id="abc05-437">99999999</span><span class="sxs-lookup"><span data-stu-id="abc05-437">99999999</span></span>
- <span data-ttu-id="abc05-438">000000000</span><span class="sxs-lookup"><span data-stu-id="abc05-438">000000000</span></span>
- <span data-ttu-id="abc05-439">111111111</span><span class="sxs-lookup"><span data-stu-id="abc05-439">111111111</span></span>
- <span data-ttu-id="abc05-440">222222222</span><span class="sxs-lookup"><span data-stu-id="abc05-440">222222222</span></span>
- <span data-ttu-id="abc05-441">333333333</span><span class="sxs-lookup"><span data-stu-id="abc05-441">333333333</span></span>
- <span data-ttu-id="abc05-442">444444444</span><span class="sxs-lookup"><span data-stu-id="abc05-442">444444444</span></span>
- <span data-ttu-id="abc05-443">555555555</span><span class="sxs-lookup"><span data-stu-id="abc05-443">555555555</span></span>
- <span data-ttu-id="abc05-444">666666666</span><span class="sxs-lookup"><span data-stu-id="abc05-444">666666666</span></span>
- <span data-ttu-id="abc05-445">777777777</span><span class="sxs-lookup"><span data-stu-id="abc05-445">777777777</span></span>
- <span data-ttu-id="abc05-446">888888888</span><span class="sxs-lookup"><span data-stu-id="abc05-446">888888888</span></span>
- <span data-ttu-id="abc05-447">999999999</span><span class="sxs-lookup"><span data-stu-id="abc05-447">999999999</span></span>
- <span data-ttu-id="abc05-448">0000000000</span><span class="sxs-lookup"><span data-stu-id="abc05-448">0000000000</span></span>
- <span data-ttu-id="abc05-449">1111111111</span><span class="sxs-lookup"><span data-stu-id="abc05-449">1111111111</span></span>
- <span data-ttu-id="abc05-450">2222222222</span><span class="sxs-lookup"><span data-stu-id="abc05-450">2222222222</span></span>
- <span data-ttu-id="abc05-451">3333333333</span><span class="sxs-lookup"><span data-stu-id="abc05-451">3333333333</span></span>
- <span data-ttu-id="abc05-452">4444444444</span><span class="sxs-lookup"><span data-stu-id="abc05-452">4444444444</span></span>
- <span data-ttu-id="abc05-453">5555555555</span><span class="sxs-lookup"><span data-stu-id="abc05-453">5555555555</span></span>
- <span data-ttu-id="abc05-454">6666666666</span><span class="sxs-lookup"><span data-stu-id="abc05-454">6666666666</span></span>
- <span data-ttu-id="abc05-455">7777777777</span><span class="sxs-lookup"><span data-stu-id="abc05-455">7777777777</span></span>
- <span data-ttu-id="abc05-456">8888888888</span><span class="sxs-lookup"><span data-stu-id="abc05-456">8888888888</span></span>
- <span data-ttu-id="abc05-457">9999999999</span><span class="sxs-lookup"><span data-stu-id="abc05-457">9999999999</span></span>

## <a name="azure-documentdb-auth-key"></a><span data-ttu-id="abc05-458">Azure DocumentDB 인증 키</span><span class="sxs-lookup"><span data-stu-id="abc05-458">Azure DocumentDB Auth Key</span></span>

### <a name="format"></a><span data-ttu-id="abc05-459">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-459">Format</span></span>

<span data-ttu-id="abc05-460">아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 "DocumentDb" 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-460">The string "DocumentDb" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-461">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-461">Pattern</span></span>

- <span data-ttu-id="abc05-462">"DocumentDb" 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-462">The string "DocumentDb"</span></span>
- <span data-ttu-id="abc05-463">3-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-463">Any combination of between 3-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-464">보다 큼 기호 (>), 등호 (=), 따옴표 (") 또는 아포스트로피 (')</span><span class="sxs-lookup"><span data-stu-id="abc05-464">A greater than symbol (>), an equal sign (=), a quotation mark ("), or an apostrophe (')</span></span>
- <span data-ttu-id="abc05-465">86의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-465">Any combination of 86 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-466">두 개의 등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-466">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-467">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-467">Checksum</span></span>

<span data-ttu-id="abc05-468">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-468">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-469">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-469">Definition</span></span>

<span data-ttu-id="abc05-470">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-470">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-471">정규식 CEP_Regex_AzureDocumentDBAuthKey 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-471">The regular expression CEP_Regex_AzureDocumentDBAuthKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-472">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-472">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!-- Azure Document DB Auth Key -->
<Entity id="0f587d92-eb28-44a9-bd1c-90f2892b47aa" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureDocumentDBAuthKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
          </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-473">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-473">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-474">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-474">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-475">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-475">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-476">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-476">contoso</span></span>
- <span data-ttu-id="abc05-477">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-477">fabrikam</span></span>
- <span data-ttu-id="abc05-478">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-478">northwind</span></span>
- <span data-ttu-id="abc05-479">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-479">sandbox</span></span>
- <span data-ttu-id="abc05-480">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-480">onebox</span></span>
- <span data-ttu-id="abc05-481">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-481">localhost</span></span>
- <span data-ttu-id="abc05-482">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-482">127.0.0.1</span></span>
- <span data-ttu-id="abc05-483">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-483">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-484">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-484">com</span></span>
- <span data-ttu-id="abc05-485">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-485">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-486">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-486">net</span></span>

## <a name="azure-iaas-database-connection-string-and-azure-sql-connection-string"></a><span data-ttu-id="abc05-487">Azure IAAS 데이터베이스 연결 문자열 및 Azure SQL 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-487">Azure IAAS Database Connection String and Azure SQL Connection String</span></span>

### <a name="format"></a><span data-ttu-id="abc05-488">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-488">Format</span></span>

<span data-ttu-id="abc05-489">"Server", "server" 또는 "data source" 라는 문자열은 "cloudapp. azure"를 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-489">The string "Server", "server", or "data source" followed by the characters and strings outlined in the pattern below, including the string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-490">com "또는" cloudapp.</span><span class="sxs-lookup"><span data-stu-id="abc05-490">com" or "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-491">net "또는" 데이터베이스.</span><span class="sxs-lookup"><span data-stu-id="abc05-491">net" or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-492">net "과 문자열" Password "또는" password "또는" pwd "가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-492">net", and the string "Password" or "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-493">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-493">Pattern</span></span>

- <span data-ttu-id="abc05-494">문자열 "Server", "Server" 또는 "data source"</span><span class="sxs-lookup"><span data-stu-id="abc05-494">The string "Server", "server", or "data source"</span></span>
- <span data-ttu-id="abc05-495">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-495">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-496">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-496">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-497">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-497">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-498">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-498">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-499">문자열 "cloudapp.</span><span class="sxs-lookup"><span data-stu-id="abc05-499">The string "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-500">com "," cloudapp.</span><span class="sxs-lookup"><span data-stu-id="abc05-500">com", "cloudapp.azure.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-501">net "또는" database.</span><span class="sxs-lookup"><span data-stu-id="abc05-501">net", or "database.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-502">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-502">net"</span></span>
- <span data-ttu-id="abc05-503">1-300에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-503">Any combination of between 1-300 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-504">문자열 "Password", "password" 또는 "pwd"</span><span class="sxs-lookup"><span data-stu-id="abc05-504">The string "Password", "password", or "pwd"</span></span>
- <span data-ttu-id="abc05-505">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-505">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-506">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-506">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-507">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-507">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-508">세미콜론 (;), 따옴표 (") 또는 아포스트로피 (')가 아닌 하나 이상의 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-508">One or more characters that is not a semicolon (;), quotation mark ("), or apostrophe (')</span></span>
- <span data-ttu-id="abc05-509">세미콜론 (;), 따옴표 (") 또는 아포스트로피 (')</span><span class="sxs-lookup"><span data-stu-id="abc05-509">A semicolon (;), quotation mark ("), or apostrophe (')</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-510">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-510">Checksum</span></span>

<span data-ttu-id="abc05-511">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-511">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-512">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-512">Definition</span></span>

<span data-ttu-id="abc05-513">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-513">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-514">정규식 CEP_Regex_AzureConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-514">The regular expression CEP_Regex_AzureConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-515">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-515">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IAAS Database Connection String and Azure SQL Connection String-->
<Entity id="ce1a126d-186f-4700-8c0c-486157b953fd" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-516">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-516">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-517">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-517">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-518">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-518">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-519">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-519">contoso</span></span>
- <span data-ttu-id="abc05-520">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-520">fabrikam</span></span>
- <span data-ttu-id="abc05-521">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-521">northwind</span></span>
- <span data-ttu-id="abc05-522">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-522">sandbox</span></span>
- <span data-ttu-id="abc05-523">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-523">onebox</span></span>
- <span data-ttu-id="abc05-524">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-524">localhost</span></span>
- <span data-ttu-id="abc05-525">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-525">127.0.0.1</span></span>
- <span data-ttu-id="abc05-526">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-526">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-527">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-527">com</span></span>
- <span data-ttu-id="abc05-528">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-528">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-529">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-529">net</span></span>

## <a name="azure-iot-connection-string"></a><span data-ttu-id="abc05-530">Azure IoT Connection 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-530">Azure IoT Connection String</span></span>

### <a name="format"></a><span data-ttu-id="abc05-531">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-531">Format</span></span>

<span data-ttu-id="abc05-532">문자열 "HostName" 뒤에 "azure-devices" 라는 문자열을 포함 하 여 아래 패턴에 설명 된 문자 및 문자열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-532">The string "HostName" followed by the characters and strings outlined in the pattern below, including the strings "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-533">net "및" SharedAccessKey "</span><span class="sxs-lookup"><span data-stu-id="abc05-533">net" and "SharedAccessKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-534">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-534">Pattern</span></span>

- <span data-ttu-id="abc05-535">문자열 "HostName"</span><span class="sxs-lookup"><span data-stu-id="abc05-535">The string "HostName"</span></span>
- <span data-ttu-id="abc05-536">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-536">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-537">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-537">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-538">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-538">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-539">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-539">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-540">문자열 "azure-장치</span><span class="sxs-lookup"><span data-stu-id="abc05-540">The string "azure-devices.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-541">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-541">net"</span></span>
- <span data-ttu-id="abc05-542">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-542">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-543">"SharedAccessKey" 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-543">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="abc05-544">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-544">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-545">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-545">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-546">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-546">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-547">43의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-547">Any combination of 43 lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-548">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-548">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-549">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-549">Checksum</span></span>

<span data-ttu-id="abc05-550">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-550">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-551">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-551">Definition</span></span>

<span data-ttu-id="abc05-552">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-552">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-553">정규식 CEP_Regex_AzureIoTConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-553">The regular expression CEP_Regex_AzureIoTConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-554">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-554">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure IoT Connection String-->
<Entity id="0b34bec3-d5d6-4974-b7b0-dcdb5c90c29d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureIoTConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-555">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-555">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-556">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-556">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-557">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-557">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-558">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-558">contoso</span></span>
- <span data-ttu-id="abc05-559">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-559">fabrikam</span></span>
- <span data-ttu-id="abc05-560">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-560">northwind</span></span>
- <span data-ttu-id="abc05-561">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-561">sandbox</span></span>
- <span data-ttu-id="abc05-562">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-562">onebox</span></span>
- <span data-ttu-id="abc05-563">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-563">localhost</span></span>
- <span data-ttu-id="abc05-564">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-564">127.0.0.1</span></span>
- <span data-ttu-id="abc05-565">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-565">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-566">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-566">com</span></span>
- <span data-ttu-id="abc05-567">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-567">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-568">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-568">net</span></span>

## <a name="azure-publish-setting-password"></a><span data-ttu-id="abc05-569">Azure 게시 설정 암호</span><span class="sxs-lookup"><span data-stu-id="abc05-569">Azure Publish Setting Password</span></span>

### <a name="format"></a><span data-ttu-id="abc05-570">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-570">Format</span></span>

<span data-ttu-id="abc05-571">문자열 "userpwd =" 다음에 영숫자 문자열이 나옵니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-571">The string "userpwd=" followed by an alphanumeric string.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-572">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-572">Pattern</span></span>

- <span data-ttu-id="abc05-573">문자열 "userpwd ="</span><span class="sxs-lookup"><span data-stu-id="abc05-573">The string "userpwd="</span></span>
- <span data-ttu-id="abc05-574">60 대 문자와 숫자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-574">Any combination of 60 lowercase letters or digits</span></span>
- <span data-ttu-id="abc05-575">큰따옴표 (")</span><span class="sxs-lookup"><span data-stu-id="abc05-575">A quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-576">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-576">Checksum</span></span>

<span data-ttu-id="abc05-577">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-577">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-578">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-578">Definition</span></span>

<span data-ttu-id="abc05-579">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-579">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-580">정규식 CEP_Regex_AzurePublishSettingPasswords 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-580">The regular expression CEP_Regex_AzurePublishSettingPasswords finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-581">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-581">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>


```xml
<!--Azure Publish Setting Password-->
<Entity id="75f4cc8a-a68e-49e5-89ce-fa8f03d286a5" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="CEP_Regex_AzurePublishSettingPasswords" />
       <Any minMatches="0" maxMatches="0">
           <Match idRef="CEP_CommonExampleKeywords" />
       </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-582">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-582">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-583">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-583">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-584">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-584">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-585">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-585">contoso</span></span>
- <span data-ttu-id="abc05-586">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-586">fabrikam</span></span>
- <span data-ttu-id="abc05-587">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-587">northwind</span></span>
- <span data-ttu-id="abc05-588">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-588">sandbox</span></span>
- <span data-ttu-id="abc05-589">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-589">onebox</span></span>
- <span data-ttu-id="abc05-590">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-590">localhost</span></span>
- <span data-ttu-id="abc05-591">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-591">127.0.0.1</span></span>
- <span data-ttu-id="abc05-592">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-592">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-593">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-593">com</span></span>
- <span data-ttu-id="abc05-594">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-594">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-595">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-595">net</span></span>

## <a name="azure-redis-cache-connection-string"></a><span data-ttu-id="abc05-596">Azure Redis 캐시 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-596">Azure Redis Cache Connection String</span></span>

### <a name="format"></a><span data-ttu-id="abc05-597">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-597">Format</span></span>

<span data-ttu-id="abc05-598">문자열 "redis.</span><span class="sxs-lookup"><span data-stu-id="abc05-598">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-599">net "문자열" password "또는" pwd "를 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 입력 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-599">net" followed by the characters and strings outlined in the pattern below, including the string "password" or "pwd".</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-600">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-600">Pattern</span></span>

- <span data-ttu-id="abc05-601">문자열 "redis.</span><span class="sxs-lookup"><span data-stu-id="abc05-601">The string "redis.cache.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-602">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-602">net"</span></span>
- <span data-ttu-id="abc05-603">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-603">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-604">문자열 "password" 또는 "pwd"</span><span class="sxs-lookup"><span data-stu-id="abc05-604">The string "password" or "pwd"</span></span>
- <span data-ttu-id="abc05-605">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-605">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-606">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-606">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-607">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-607">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-608">대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 43 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-608">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-609">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-609">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-610">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-610">Checksum</span></span>

<span data-ttu-id="abc05-611">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-611">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-612">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-612">Definition</span></span>

<span data-ttu-id="abc05-613">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-614">정규식 CEP_Regex_AzureRedisCacheConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-614">The regular expression CEP_Regex_AzureRedisCacheConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="abc05-615">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-615">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Redis Cache Connection String-->
<Entity id="095a7e6c-efd8-46d5-af7b-5298d53a49fc" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureRedisCacheConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-616">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-616">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-617">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-617">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-618">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-618">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-619">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-619">contoso</span></span>
- <span data-ttu-id="abc05-620">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-620">fabrikam</span></span>
- <span data-ttu-id="abc05-621">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-621">northwind</span></span>
- <span data-ttu-id="abc05-622">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-622">sandbox</span></span>
- <span data-ttu-id="abc05-623">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-623">onebox</span></span>
- <span data-ttu-id="abc05-624">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-624">localhost</span></span>
- <span data-ttu-id="abc05-625">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-625">127.0.0.1</span></span>
- <span data-ttu-id="abc05-626">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-626">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-627">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-627">com</span></span>
- <span data-ttu-id="abc05-628">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-628">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-629">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-629">net</span></span>

## <a name="azure-sas"></a><span data-ttu-id="abc05-630">Azure SAS</span><span class="sxs-lookup"><span data-stu-id="abc05-630">Azure SAS</span></span>

### <a name="format"></a><span data-ttu-id="abc05-631">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-631">Format</span></span>

<span data-ttu-id="abc05-632">아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 문자열 "sig"</span><span class="sxs-lookup"><span data-stu-id="abc05-632">The string "sig" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-633">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-633">Pattern</span></span>

- <span data-ttu-id="abc05-634">문자열 "sig"</span><span class="sxs-lookup"><span data-stu-id="abc05-634">The string "sig"</span></span>
- <span data-ttu-id="abc05-635">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-635">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-636">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-636">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-637">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-637">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-638">대/소문자, 숫자 또는 백분율 기호 (%)가 43-53 자 사이의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-638">Any combination of between 43-53 characters that are lower- or uppercase letters, digits, or the percent sign (%)</span></span>
- <span data-ttu-id="abc05-639">문자열 "% 3d"</span><span class="sxs-lookup"><span data-stu-id="abc05-639">The string "%3d"</span></span>
- <span data-ttu-id="abc05-640">소문자 또는 대문자, 숫자 또는 백분율 기호 (%)가 아닌 모든 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-640">Any character that is not a lower- or uppercase letter, digit, or percent sign (%)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-641">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-641">Checksum</span></span>

<span data-ttu-id="abc05-642">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-642">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-643">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-643">Definition</span></span>

<span data-ttu-id="abc05-644">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-644">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-645">정규식 CEP_Regex_AzureSAS 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-645">The regular expression CEP_Regex_AzureSAS finds content that matches the pattern.</span></span>

```xml
<!--Azure SAS-->
<Entity id="4d235014-e564-47f4-a6fb-6ebb4a826834" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureSAS" />
  </Pattern>
</Entity>
```

## <a name="azure-service-bus-connection-string"></a><span data-ttu-id="abc05-646">Azure Service Bus 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-646">Azure Service Bus Connection String</span></span>

### <a name="format"></a><span data-ttu-id="abc05-647">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-647">Format</span></span>

<span data-ttu-id="abc05-648">문자열 "끝점" 뒤에 "servicebus" 라는 문자열을 포함 하 여 아래 패턴에 나와 있는 문자 및 문자열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-648">The string "EndPoint" followed by the characters and strings outlined in the pattern below, including the strings "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-649">net "및" SharedAccesKey "을 차례로 누릅니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-649">net" and "SharedAccesKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-650">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-650">Pattern</span></span>

- <span data-ttu-id="abc05-651">문자열 "끝점"</span><span class="sxs-lookup"><span data-stu-id="abc05-651">The string "EndPoint"</span></span>
- <span data-ttu-id="abc05-652">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-652">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-653">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-653">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-654">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-654">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-655">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-655">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-656">문자열 "servicebus.</span><span class="sxs-lookup"><span data-stu-id="abc05-656">The string "servicebus.windows.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-657">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-657">net"</span></span>
- <span data-ttu-id="abc05-658">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-658">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-659">"SharedAccessKey" 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-659">The string "SharedAccessKey"</span></span>
- <span data-ttu-id="abc05-660">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-660">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-661">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-661">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-662">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-662">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-663">대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 43 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-663">Any combination of 43 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-664">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-664">An equal sign (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-665">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-665">Checksum</span></span>

<span data-ttu-id="abc05-666">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-666">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-667">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-667">Definition</span></span>

<span data-ttu-id="abc05-668">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-668">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-669">정규식 CEP_Regex_AzureServiceBusConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-669">The regular expression CEP_Regex_AzureServiceBusConnectionString finds content that matches the pattern..</span></span>
- <span data-ttu-id="abc05-670">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-670">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Service Bus Connection String-->
<Entity id="b9a6578f-a83f-4fcd-bf44-2130bae49a6f" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureServiceBusConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-671">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-671">Keywords</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-672">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-672">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-673">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-673">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-674">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-674">contoso</span></span>
- <span data-ttu-id="abc05-675">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-675">fabrikam</span></span>
- <span data-ttu-id="abc05-676">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-676">northwind</span></span>
- <span data-ttu-id="abc05-677">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-677">sandbox</span></span>
- <span data-ttu-id="abc05-678">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-678">onebox</span></span>
- <span data-ttu-id="abc05-679">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-679">localhost</span></span>
- <span data-ttu-id="abc05-680">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-680">127.0.0.1</span></span>
- <span data-ttu-id="abc05-681">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-681">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-682">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-682">com</span></span>
- <span data-ttu-id="abc05-683">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-683">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-684">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-684">net</span></span>

## <a name="azure-storage-account-key"></a><span data-ttu-id="abc05-685">Azure 저장소 계정 키</span><span class="sxs-lookup"><span data-stu-id="abc05-685">Azure Storage Account Key</span></span>

### <a name="format"></a><span data-ttu-id="abc05-686">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-686">Format</span></span>

<span data-ttu-id="abc05-687">"DefaultEndpointsProtocol" 문자열은 "AccountKey" 문자열을 포함 하 여 아래 패턴에 설명 된 문자 및 문자열을 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-687">The string "DefaultEndpointsProtocol" followed by the characters and strings outlined in the pattern below, including the string "AccountKey".</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-688">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-688">Pattern</span></span>

- <span data-ttu-id="abc05-689">문자열 "DefaultEndpointsProtocol"</span><span class="sxs-lookup"><span data-stu-id="abc05-689">The string "DefaultEndpointsProtocol"</span></span>
- <span data-ttu-id="abc05-690">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-690">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-691">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-691">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-692">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-692">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-693">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-693">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-694">문자열 "AccountKey"</span><span class="sxs-lookup"><span data-stu-id="abc05-694">The string "AccountKey"</span></span>
- <span data-ttu-id="abc05-695">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-695">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-696">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-696">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-697">0-2 공백 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-697">0-2 whitespace characters</span></span>
- <span data-ttu-id="abc05-698">대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 86 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-698">Any combination of 86 characters that are lower- or uppercase letters, digits, forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-699">두 개의 등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-699">Two equal signs (=)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-700">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-700">Checksum</span></span>

<span data-ttu-id="abc05-701">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-701">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-702">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-702">Definition</span></span>

<span data-ttu-id="abc05-703">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-703">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-704">정규식 CEP_Regex_AzureStorageAccountKey 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-704">The regular expression CEP_Regex_AzureStorageAccountKey finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-705">정규식 CEP_AzureEmulatorStorageAccountFilter에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-705">The regular expression CEP_AzureEmulatorStorageAccountFilter does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-706">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-706">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key-->
<Entity id="c7bc98e8-551a-4c35-a92d-d2c8cda714a7" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKey" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_AzureEmulatorStorageAccountFilter" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-707">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-707">Keywords</span></span>

#### <a name="cep_azureemulatorstorageaccountfilter"></a><span data-ttu-id="abc05-708">CEP_AzureEmulatorStorageAccountFilter</span><span class="sxs-lookup"><span data-stu-id="abc05-708">CEP_AzureEmulatorStorageAccountFilter</span></span>

<span data-ttu-id="abc05-709">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-709">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw = =</span><span class="sxs-lookup"><span data-stu-id="abc05-710">Eby8vdM02xNOcqFlqUwJPLlmEtlCDXJ1OUzFT50uSRZ6IFsuFq2UVErCz4I6tq/K1SZFPTOtr/KBHBeksoGMGw==</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-711">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-711">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-712">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-712">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-713">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-713">contoso</span></span>
- <span data-ttu-id="abc05-714">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-714">fabrikam</span></span>
- <span data-ttu-id="abc05-715">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-715">northwind</span></span>
- <span data-ttu-id="abc05-716">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-716">sandbox</span></span>
- <span data-ttu-id="abc05-717">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-717">onebox</span></span>
- <span data-ttu-id="abc05-718">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-718">localhost</span></span>
- <span data-ttu-id="abc05-719">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-719">127.0.0.1</span></span>
- <span data-ttu-id="abc05-720">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-720">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-721">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-721">com</span></span>
- <span data-ttu-id="abc05-722">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-722">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-723">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-723">net</span></span>

## <a name="azure-storage-account-key-generic"></a><span data-ttu-id="abc05-724">Azure 저장소 계정 키 (일반)</span><span class="sxs-lookup"><span data-stu-id="abc05-724">Azure Storage Account Key (Generic)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-725">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-725">Format</span></span>

<span data-ttu-id="abc05-726">아래 패턴에 윤곽선이 있는 문자 앞 이나 뒤에 오는 86 문자의 대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)의 조합입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-726">Any combination of 86 lower- or uppercase letters, digits, the forward slash (/), or plus sign (+), preceded or followed by the characters outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-727">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-727">Pattern</span></span>

- <span data-ttu-id="abc05-728">보다 큼 기호 (>), 아포스트로피 ('), 등호 (=), 따옴표 (") 또는 숫자 기호 (#) 0-1</span><span class="sxs-lookup"><span data-stu-id="abc05-728">0-1 of the greater than symbol (>), apostrophe ('), equal sign (=), quotation mark ("), or number sign (#)</span></span>
- <span data-ttu-id="abc05-729">대/소문자, 숫자, 슬래시 (/) 또는 더하기 기호 (+)가 있는 86 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-729">Any combination of 86 characters that are lower- or uppercase letters, digits, the forward slash (/), or plus sign (+)</span></span>
- <span data-ttu-id="abc05-730">두 개의 등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-730">Two equal signs (=)</span></span>


### <a name="checksum"></a><span data-ttu-id="abc05-731">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-731">Checksum</span></span>

<span data-ttu-id="abc05-732">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-732">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-733">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-733">Definition</span></span>

<span data-ttu-id="abc05-734">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-734">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-735">정규식 CEP_Regex_AzureStorageAccountKeyGeneric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-735">The regular expression CEP_Regex_AzureStorageAccountKeyGeneric finds content that matches the pattern.</span></span>

```xml
<!--Azure Storage Account Key (Generic)-->
<Entity id="7ff41bd0-5419-4523-91d6-383b3a37f084" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_AzureStorageAccountKeyGeneric" />
  </Pattern>
</Entity>
```

## <a name="belgium-national-number"></a><span data-ttu-id="abc05-736">벨기에 국가 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-736">Belgium National Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-737">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-737">Format</span></span>

<span data-ttu-id="abc05-738">11자리 숫자와 구분 기호</span><span class="sxs-lookup"><span data-stu-id="abc05-738">11 digits plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-739">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-739">Pattern</span></span>

<span data-ttu-id="abc05-740">11자리 숫자와 구분 기호:</span><span class="sxs-lookup"><span data-stu-id="abc05-740">11 digits plus delimiters:</span></span>
- <span data-ttu-id="abc05-741">생년월일을 나타내는 YY.MM.DD 형식의 6자리 숫자와 마침표 2개 </span><span class="sxs-lookup"><span data-stu-id="abc05-741">Six digits and two periods in the format YY.MM.DD for date of birth</span></span> 
- <span data-ttu-id="abc05-742">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-742">A hyphen</span></span> 
- <span data-ttu-id="abc05-743">세 개의 순차적 숫자(남성의 경우 홀수, 여성의 경우 짝수) </span><span class="sxs-lookup"><span data-stu-id="abc05-743">Three sequential digits (odd for males, even for females)</span></span> 
- <span data-ttu-id="abc05-744">마침표</span><span class="sxs-lookup"><span data-stu-id="abc05-744">A period</span></span> 
- <span data-ttu-id="abc05-745">검사 숫자에 해당하는 두 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-745">Two digits that are a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-746">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-746">Checksum</span></span>

<span data-ttu-id="abc05-747">예</span><span class="sxs-lookup"><span data-stu-id="abc05-747">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-748">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-748">Definition</span></span>

<span data-ttu-id="abc05-749">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-749">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-750">Func_belgium_national_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-750">The function Func_belgium_national_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-751">Keyword_belgium_national_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-751">A keyword from Keyword_belgium_national_number is found.</span></span>
- <span data-ttu-id="abc05-752">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-752">The checksum passes.</span></span>

```xml
<!-- Belgium National Number -->
  <Entity id="fb969c9e-0fd1-4b18-8091-a2123c5e6a54" recommendedConfidence="75" patternsProximity="300">
   <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_belgium_national_number"/>
     <Match idRef="Keyword_belgium_national_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-753">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-753">Keywords</span></span>

#### <a name="keyword_belgium_national_number"></a><span data-ttu-id="abc05-754">Keyword_belgium_national_number</span><span class="sxs-lookup"><span data-stu-id="abc05-754">Keyword_belgium_national_number</span></span>

- <span data-ttu-id="abc05-755">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-755">Identity</span></span>
- <span data-ttu-id="abc05-756">등록</span><span class="sxs-lookup"><span data-stu-id="abc05-756">Registration</span></span>
- <span data-ttu-id="abc05-757">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-757">Identification</span></span> 
- <span data-ttu-id="abc05-758">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-758">ID</span></span> 
- <span data-ttu-id="abc05-759">Identiteitskaart</span><span class="sxs-lookup"><span data-stu-id="abc05-759">Identiteitskaart</span></span>
- <span data-ttu-id="abc05-760">Registratie nummer</span><span class="sxs-lookup"><span data-stu-id="abc05-760">Registratie nummer</span></span> 
- <span data-ttu-id="abc05-761">Identificatie nummer</span><span class="sxs-lookup"><span data-stu-id="abc05-761">Identificatie nummer</span></span> 
- <span data-ttu-id="abc05-762">Identiteit</span><span class="sxs-lookup"><span data-stu-id="abc05-762">Identiteit</span></span>
- <span data-ttu-id="abc05-763">Registratie</span><span class="sxs-lookup"><span data-stu-id="abc05-763">Registratie</span></span>
- <span data-ttu-id="abc05-764">Identificatie</span><span class="sxs-lookup"><span data-stu-id="abc05-764">Identificatie</span></span> 
- <span data-ttu-id="abc05-765">Carte d’identité</span><span class="sxs-lookup"><span data-stu-id="abc05-765">Carte d’identité</span></span> 
- <span data-ttu-id="abc05-766">numéro d'immatriculation</span><span class="sxs-lookup"><span data-stu-id="abc05-766">numéro d'immatriculation</span></span>
- <span data-ttu-id="abc05-767">numéro d'identification</span><span class="sxs-lookup"><span data-stu-id="abc05-767">numéro d'identification</span></span>
- <span data-ttu-id="abc05-768">identité</span><span class="sxs-lookup"><span data-stu-id="abc05-768">identité</span></span> 
- <span data-ttu-id="abc05-769">inscription</span><span class="sxs-lookup"><span data-stu-id="abc05-769">inscription</span></span> 
- <span data-ttu-id="abc05-770">Identifikation</span><span class="sxs-lookup"><span data-stu-id="abc05-770">Identifikation</span></span>
- <span data-ttu-id="abc05-771">Identifizierung</span><span class="sxs-lookup"><span data-stu-id="abc05-771">Identifizierung</span></span>
- <span data-ttu-id="abc05-772">Identifikationsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-772">Identifikationsnummer</span></span>
- <span data-ttu-id="abc05-773">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="abc05-773">Personalausweis</span></span>
- <span data-ttu-id="abc05-774">Registrierung</span><span class="sxs-lookup"><span data-stu-id="abc05-774">Registrierung</span></span>
- <span data-ttu-id="abc05-775">Registrationsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-775">Registrationsnummer</span></span>

   
## <a name="brazil-cpf-number"></a><span data-ttu-id="abc05-776">브라질 CPF 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-776">Brazil CPF Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-777">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-777">Format</span></span>

<span data-ttu-id="abc05-778">서식이 있거나 서식이 없을 수 있는 검사 숫자를 포함하는 11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-778">11 digits that include a check digit and can be formatted or unformatted</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-779">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-779">Pattern</span></span>

<span data-ttu-id="abc05-780">서식이</span><span class="sxs-lookup"><span data-stu-id="abc05-780">Formatted:</span></span>
- <span data-ttu-id="abc05-781">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-781">Three digits</span></span> 
- <span data-ttu-id="abc05-782">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-782">A period</span></span> 
- <span data-ttu-id="abc05-783">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-783">Three digits</span></span> 
- <span data-ttu-id="abc05-784">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-784">A period</span></span> 
- <span data-ttu-id="abc05-785">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-785">Three digits</span></span> 
- <span data-ttu-id="abc05-786">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-786">A hyphen</span></span> 
- <span data-ttu-id="abc05-787">검사 숫자에 해당하는 2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-787">Two digits which are check digits</span></span>

<span data-ttu-id="abc05-788">서식</span><span class="sxs-lookup"><span data-stu-id="abc05-788">Unformatted:</span></span>
- <span data-ttu-id="abc05-789">마지막 2자리 숫자가 검사 숫자인 11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-789">11 digits where the last two digits are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-790">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-790">Checksum</span></span>

<span data-ttu-id="abc05-791">예</span><span class="sxs-lookup"><span data-stu-id="abc05-791">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-792">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-792">Definition</span></span>

<span data-ttu-id="abc05-793">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-794">Func_brazil_cpf 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-794">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-795">Keyword_brazil_cpf에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-795">A keyword from Keyword_brazil_cpf is found.</span></span>
- <span data-ttu-id="abc05-796">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-796">The checksum passes.</span></span>

<span data-ttu-id="abc05-797">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-797">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-798">Func_brazil_cpf 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-798">The function Func_brazil_cpf finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-799">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-799">The checksum passes.</span></span>

```xml
<!-- Brazil CPF Number -->
<Entity id="78e09124-f2c3-4656-b32a-c1a132cd2711" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cpf"/>
     <Match idRef="Keyword_brazil_cpf"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cpf"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-800">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-800">Keywords</span></span>

#### <a name="keyword_brazil_cpf"></a><span data-ttu-id="abc05-801">Keyword_brazil_cpf</span><span class="sxs-lookup"><span data-stu-id="abc05-801">Keyword_brazil_cpf</span></span>

- <span data-ttu-id="abc05-802">CPF</span><span class="sxs-lookup"><span data-stu-id="abc05-802">CPF</span></span>
- <span data-ttu-id="abc05-803">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-803">Identification</span></span>
- <span data-ttu-id="abc05-804">등록</span><span class="sxs-lookup"><span data-stu-id="abc05-804">Registration</span></span>
- <span data-ttu-id="abc05-805">별</span><span class="sxs-lookup"><span data-stu-id="abc05-805">Revenue</span></span>
- <span data-ttu-id="abc05-806">Cadastro de Pessoas Físicas</span><span class="sxs-lookup"><span data-stu-id="abc05-806">Cadastro de Pessoas Físicas</span></span> 
- <span data-ttu-id="abc05-807">Imposto</span><span class="sxs-lookup"><span data-stu-id="abc05-807">Imposto</span></span> 
- <span data-ttu-id="abc05-808">Identificação</span><span class="sxs-lookup"><span data-stu-id="abc05-808">Identificação</span></span> 
- <span data-ttu-id="abc05-809">Inscrição</span><span class="sxs-lookup"><span data-stu-id="abc05-809">Inscrição</span></span> 
- <span data-ttu-id="abc05-810">고 eita</span><span class="sxs-lookup"><span data-stu-id="abc05-810">Receita</span></span> 
   
## <a name="brazil-legal-entity-number-cnpj"></a><span data-ttu-id="abc05-811">브라질 법인 번호(CNPJ)</span><span class="sxs-lookup"><span data-stu-id="abc05-811">Brazil Legal Entity Number (CNPJ)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-812">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-812">Format</span></span>

<span data-ttu-id="abc05-813">등록 번호, 지점 번호, 검사 숫자 및 구분 기호를 포함하는 14자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-813">14 digits that include a registration number, branch number, and check digits, plus delimiters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-814">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-814">Pattern</span></span>
<span data-ttu-id="abc05-815">14자리 숫자와 구분 기호:</span><span class="sxs-lookup"><span data-stu-id="abc05-815">14 digits, plus delimiters:</span></span>
- <span data-ttu-id="abc05-816">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-816">Two digits</span></span> 
- <span data-ttu-id="abc05-817">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-817">A period</span></span> 
- <span data-ttu-id="abc05-818">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-818">Three digits</span></span> 
- <span data-ttu-id="abc05-819">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-819">A period</span></span> 
- <span data-ttu-id="abc05-820">3자리 숫자(처음 8자리 숫자는 등록 번호임) </span><span class="sxs-lookup"><span data-stu-id="abc05-820">Three digits (these first eight digits are the registration number)</span></span> 
- <span data-ttu-id="abc05-821">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="abc05-821">A forward slash</span></span> 
- <span data-ttu-id="abc05-822">4자리 지점 번호 </span><span class="sxs-lookup"><span data-stu-id="abc05-822">Four-digit branch number</span></span> 
- <span data-ttu-id="abc05-823">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-823">A hyphen</span></span> 
- <span data-ttu-id="abc05-824">검사 숫자에 해당하는 2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-824">Two digits which are check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-825">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-825">Checksum</span></span>

<span data-ttu-id="abc05-826">예</span><span class="sxs-lookup"><span data-stu-id="abc05-826">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-827">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-827">Definition</span></span>

<span data-ttu-id="abc05-828">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-828">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-829">Func_brazil_cnpj 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-829">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-830">Keyword_brazil_cnpj에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-830">A keyword from Keyword_brazil_cnpj is found.</span></span>
- <span data-ttu-id="abc05-831">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-831">The checksum passes.</span></span>

<span data-ttu-id="abc05-832">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-832">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-833">Func_brazil_cnpj 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-833">The function Func_brazil_cnpj finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-834">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-834">The checksum passes.</span></span>

```xml
<!-- Brazil Legal Entity Number (CNPJ) -->
<Entity id="9b58b5cd-5e90-4df6-b34f-1ebcc88ceae4" recommendedConfidence="85" patternsProximity="300">
   <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_cnpj"/>
     <Match idRef="Keyword_brazil_cnpj"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_cnpj"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-835">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-835">Keywords</span></span>

#### <a name="keyword_brazil_cnpj"></a><span data-ttu-id="abc05-836">Keyword_brazil_cnpj</span><span class="sxs-lookup"><span data-stu-id="abc05-836">Keyword_brazil_cnpj</span></span>

- <span data-ttu-id="abc05-837">CNPJ</span><span class="sxs-lookup"><span data-stu-id="abc05-837">CNPJ</span></span> 
- <span data-ttu-id="abc05-838">CNPJ/MF</span><span class="sxs-lookup"><span data-stu-id="abc05-838">CNPJ/MF</span></span> 
- <span data-ttu-id="abc05-839">CNPJ-MF</span><span class="sxs-lookup"><span data-stu-id="abc05-839">CNPJ-MF</span></span> 
- <span data-ttu-id="abc05-840">National Registry of Legal Entities</span><span class="sxs-lookup"><span data-stu-id="abc05-840">National Registry of Legal Entities</span></span> 
- <span data-ttu-id="abc05-841">Taxpayers Registry</span><span class="sxs-lookup"><span data-stu-id="abc05-841">Taxpayers Registry</span></span> 
- <span data-ttu-id="abc05-842">Legal entity</span><span class="sxs-lookup"><span data-stu-id="abc05-842">Legal entity</span></span> 
- <span data-ttu-id="abc05-843">Legal entities</span><span class="sxs-lookup"><span data-stu-id="abc05-843">Legal entities</span></span> 
- <span data-ttu-id="abc05-844">Registration Status</span><span class="sxs-lookup"><span data-stu-id="abc05-844">Registration Status</span></span> 
- <span data-ttu-id="abc05-845">비즈니스</span><span class="sxs-lookup"><span data-stu-id="abc05-845">Business</span></span> 
- <span data-ttu-id="abc05-846">Company</span><span class="sxs-lookup"><span data-stu-id="abc05-846">Company</span></span>
- <span data-ttu-id="abc05-847">CNPJ</span><span class="sxs-lookup"><span data-stu-id="abc05-847">CNPJ</span></span> 
- <span data-ttu-id="abc05-848">Cadastro Nacional da Pessoa Jurídica</span><span class="sxs-lookup"><span data-stu-id="abc05-848">Cadastro Nacional da Pessoa Jurídica</span></span> 
- <span data-ttu-id="abc05-849">Cadastro Geral de Contribuintes</span><span class="sxs-lookup"><span data-stu-id="abc05-849">Cadastro Geral de Contribuintes</span></span> 
- <span data-ttu-id="abc05-850">CGC</span><span class="sxs-lookup"><span data-stu-id="abc05-850">CGC</span></span> 
- <span data-ttu-id="abc05-851">Pessoa jurídica</span><span class="sxs-lookup"><span data-stu-id="abc05-851">Pessoa jurídica</span></span> 
- <span data-ttu-id="abc05-852">Pessoas jurídicas</span><span class="sxs-lookup"><span data-stu-id="abc05-852">Pessoas jurídicas</span></span> 
- <span data-ttu-id="abc05-853">Situação cadastral</span><span class="sxs-lookup"><span data-stu-id="abc05-853">Situação cadastral</span></span> 
- <span data-ttu-id="abc05-854">Inscrição</span><span class="sxs-lookup"><span data-stu-id="abc05-854">Inscrição</span></span> 
- <span data-ttu-id="abc05-855">포털</span><span class="sxs-lookup"><span data-stu-id="abc05-855">Empresa</span></span> 
   
## <a name="brazil-national-id-card-rg"></a><span data-ttu-id="abc05-856">	브라질 국가 ID 카드(RG)</span><span class="sxs-lookup"><span data-stu-id="abc05-856">Brazil National ID Card (RG)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-857">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-857">Format</span></span>

<span data-ttu-id="abc05-858">Registro Geral (이전 형식): 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-858">Registro Geral (old format): Nine digits</span></span>

<span data-ttu-id="abc05-859">Registro de Identidade (RIC) (새 형식): 11 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-859">Registro de Identidade (RIC) (new format): 11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-860">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-860">Pattern</span></span>

<span data-ttu-id="abc05-861">Registro Geral(이전 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-861">Registro Geral (old format):</span></span>
- <span data-ttu-id="abc05-862">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-862">Two digits</span></span> 
- <span data-ttu-id="abc05-863">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-863">A period</span></span> 
- <span data-ttu-id="abc05-864">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-864">Three digits</span></span> 
- <span data-ttu-id="abc05-865">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-865">A period</span></span> 
- <span data-ttu-id="abc05-866">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-866">Three digits</span></span> 
- <span data-ttu-id="abc05-867">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-867">A hyphen</span></span> 
- <span data-ttu-id="abc05-868">검사 숫자에 해당하는 1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-868">One digit which is a check digit</span></span>

<span data-ttu-id="abc05-869">Registro de Identidade (RIC) (새 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-869">Registro de Identidade (RIC) (new format):</span></span>
- <span data-ttu-id="abc05-870">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-870">10 digits</span></span> 
- <span data-ttu-id="abc05-871">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-871">A hyphen</span></span> 
- <span data-ttu-id="abc05-872">검사 숫자에 해당하는 1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-872">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-873">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-873">Checksum</span></span>

<span data-ttu-id="abc05-874">예</span><span class="sxs-lookup"><span data-stu-id="abc05-874">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-875">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-875">Definition</span></span>

<span data-ttu-id="abc05-876">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-876">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-877">Func_brazil_rg 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-877">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-878">Keyword_brazil_rg에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-878">A keyword from Keyword_brazil_rg is found.</span></span>
- <span data-ttu-id="abc05-879">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-879">The checksum passes.</span></span>

<span data-ttu-id="abc05-880">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-880">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-881">Func_brazil_rg 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-881">The function Func_brazil_rg finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-882">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-882">The checksum passes.</span></span>

```xml
<!-- Brazil National ID Card (RG) -->
<Entity id="486de900-db70-41b3-a886-abdf25af119c" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_brazil_rg"/>
     <Match idRef="Keyword_brazil_rg"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_brazil_rg"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-883">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-883">Keywords</span></span>

#### <a name="keyword_brazil_rg"></a><span data-ttu-id="abc05-884">Keyword_brazil_rg</span><span class="sxs-lookup"><span data-stu-id="abc05-884">Keyword_brazil_rg</span></span>

<span data-ttu-id="abc05-885">Cédula de identidade identity card 국립 id número de rregistro registro de Iidentidade registro geral RG (이 키워드는 대/소문자를 구분 함) RIC (이 키워드는 대/소문자를 구분 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-885">Cédula de identidade identity card national id número de rregistro registro de Iidentidade registro geral RG (this keyword is case sensitive) RIC (this keyword is case sensitive)</span></span> 
   
## <a name="canada-bank-account-number"></a><span data-ttu-id="abc05-886">캐나다 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-886">Canada Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-887">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-887">Format</span></span>

<span data-ttu-id="abc05-888">7 또는 12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-888">Seven or twelve digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-889">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-889">Pattern</span></span>

<span data-ttu-id="abc05-890">캐나다 은행 계좌 번호는 7 또는 12자리 숫자입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-890">A Canada Bank Account Number is seven or twelve digits.</span></span>

<span data-ttu-id="abc05-891">캐나다 은행 계좌 송금 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-891">A Canada bank account transit number is:</span></span>
- <span data-ttu-id="abc05-892">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-892">Five digits</span></span> 
- <span data-ttu-id="abc05-893">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-893">A hyphen</span></span> 
- <span data-ttu-id="abc05-894">3 자리 숫자 또는</span><span class="sxs-lookup"><span data-stu-id="abc05-894">Three digits OR</span></span>
- <span data-ttu-id="abc05-895">"0"</span><span class="sxs-lookup"><span data-stu-id="abc05-895">A zero "0"</span></span> 
- <span data-ttu-id="abc05-896">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-896">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-897">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-897">Checksum</span></span>

<span data-ttu-id="abc05-898">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-898">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-899">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-899">Definition</span></span>

<span data-ttu-id="abc05-900">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-900">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-901">Regex_canada_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-901">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-902">Keyword_canada_bank_account_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-902">A keyword from Keyword_canada_bank_account_number is found.</span></span>
- <span data-ttu-id="abc05-903">Regex_canada_bank_account_transit_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-903">The regular expression Regex_canada_bank_account_transit_number finds content that matches the pattern.</span></span>

<span data-ttu-id="abc05-904">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-904">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-905">Regex_canada_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-905">The regular expression Regex_canada_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-906">Keyword_canada_bank_account_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-906">A keyword from Keyword_canada_bank_account_number is found.</span></span>

```xml
<!-- Canada Bank Account Number -->
<Entity id="552e814c-cb50-4d94-bbaa-bb1d1ffb34de" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
        <Match idRef="Regex_canada_bank_account_transit_number" />
   </Pattern>
   <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_bank_account_number" />
        <Match idRef="Keyword_canada_bank_account_number" />
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-907">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-907">Keywords</span></span>

#### <a name="keyword_canada_bank_account_number"></a><span data-ttu-id="abc05-908">Keyword_canada_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="abc05-908">Keyword_canada_bank_account_number</span></span>

- <span data-ttu-id="abc05-909">canada savings bonds</span><span class="sxs-lookup"><span data-stu-id="abc05-909">canada savings bonds</span></span>
- <span data-ttu-id="abc05-910">canada revenue agency</span><span class="sxs-lookup"><span data-stu-id="abc05-910">canada revenue agency</span></span>
- <span data-ttu-id="abc05-911">canadian financial institution</span><span class="sxs-lookup"><span data-stu-id="abc05-911">canadian financial institution</span></span>
- <span data-ttu-id="abc05-912">direct deposit form</span><span class="sxs-lookup"><span data-stu-id="abc05-912">direct deposit form</span></span>
- <span data-ttu-id="abc05-913">canadian citizen</span><span class="sxs-lookup"><span data-stu-id="abc05-913">canadian citizen</span></span>
- <span data-ttu-id="abc05-914">legal representative</span><span class="sxs-lookup"><span data-stu-id="abc05-914">legal representative</span></span>
- <span data-ttu-id="abc05-915">notary public</span><span class="sxs-lookup"><span data-stu-id="abc05-915">notary public</span></span>
- <span data-ttu-id="abc05-916">commissioner for oaths</span><span class="sxs-lookup"><span data-stu-id="abc05-916">commissioner for oaths</span></span>
- <span data-ttu-id="abc05-917">child care benefit</span><span class="sxs-lookup"><span data-stu-id="abc05-917">child care benefit</span></span>
- <span data-ttu-id="abc05-918">universal child care</span><span class="sxs-lookup"><span data-stu-id="abc05-918">universal child care</span></span>
- <span data-ttu-id="abc05-919">canada child tax benefit</span><span class="sxs-lookup"><span data-stu-id="abc05-919">canada child tax benefit</span></span>
- <span data-ttu-id="abc05-920">income tax benefit</span><span class="sxs-lookup"><span data-stu-id="abc05-920">income tax benefit</span></span>
- <span data-ttu-id="abc05-921">harmonized sales tax</span><span class="sxs-lookup"><span data-stu-id="abc05-921">harmonized sales tax</span></span>
- <span data-ttu-id="abc05-922">social insurance number</span><span class="sxs-lookup"><span data-stu-id="abc05-922">social insurance number</span></span>
- <span data-ttu-id="abc05-923">income tax refund</span><span class="sxs-lookup"><span data-stu-id="abc05-923">income tax refund</span></span>
- <span data-ttu-id="abc05-924">child tax benefit</span><span class="sxs-lookup"><span data-stu-id="abc05-924">child tax benefit</span></span>
- <span data-ttu-id="abc05-925">territorial payments</span><span class="sxs-lookup"><span data-stu-id="abc05-925">territorial payments</span></span>
- <span data-ttu-id="abc05-926">institution number</span><span class="sxs-lookup"><span data-stu-id="abc05-926">institution number</span></span>
- <span data-ttu-id="abc05-927">deposit request</span><span class="sxs-lookup"><span data-stu-id="abc05-927">deposit request</span></span>
- <span data-ttu-id="abc05-928">banking information</span><span class="sxs-lookup"><span data-stu-id="abc05-928">banking information</span></span>
- <span data-ttu-id="abc05-929">direct deposit</span><span class="sxs-lookup"><span data-stu-id="abc05-929">direct deposit</span></span>
   
## <a name="canada-drivers-license-number"></a><span data-ttu-id="abc05-930">캐나다 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-930">Canada Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-931">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-931">Format</span></span>

<span data-ttu-id="abc05-932">지역마다 다름</span><span class="sxs-lookup"><span data-stu-id="abc05-932">Varies by province</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-933">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-933">Pattern</span></span>

<span data-ttu-id="abc05-934">앨버타, 브리티시 콜롬비아, 매니토바, 뉴브런즈윅, 뉴펀들랜드/래브라도, 노바스코샤, 온타리오, 프린스에드워드아일랜드, 퀘벡 및 서스캐처원을 포함하는 다양한 패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-934">Various patterns covering Alberta, British Columbia, Manitoba, New Brunswick, Newfoundland/Labrador, Nova Scotia, Ontario, Prince Edward Island, Quebec, and Saskatchewan</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-935">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-935">Checksum</span></span>

<span data-ttu-id="abc05-936">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-936">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-937">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-937">Definition</span></span>

<span data-ttu-id="abc05-938">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-938">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-939">Func_[province_name]_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-939">The function Func_[province_name]_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-940">Keyword_[province_name]_drivers_license_name의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-940">A keyword from Keyword_[province_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="abc05-941">Keyword_canada_drivers_license의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-941">A keyword from Keyword_canada_drivers_license is found.</span></span>

```xml
<!-- Canada Driver's License Number -->
    <Entity id="37186abb-8e48-4800-ad3c-e3d1610b3db0" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_alberta_drivers_license_number" />
        <Match idRef="Keyword_alberta_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_british_columbia_drivers_license_number" />
        <Match idRef="Keyword_british_columbia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_manitoba_drivers_license_number" />
        <Match idRef="Keyword_manitoba_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_brunswick_drivers_license_number" />
        <Match idRef="Keyword_new_brunswick_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_newfoundland_labrador_drivers_license_number" />
        <Match idRef="Keyword_newfoundland_labrador_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_nova_scotia_drivers_license_number" />
        <Match idRef="Keyword_nova_scotia_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_ontario_drivers_license_number" />
        <Match idRef="Keyword_ontario_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_prince_edward_island_drivers_license_number" />
        <Match idRef="Keyword_prince_edward_island_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_quebec_drivers_license_number" />
        <Match idRef="Keyword_quebec_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_saskatchewan_drivers_license_number" />
        <Match idRef="Keyword_saskatchewan_drivers_license_name" />
        <Match idRef="Keyword_canada_drivers_license" />
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-942">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-942">Keywords</span></span>

#### <a name="keyword_province_name_drivers_license_name"></a><span data-ttu-id="abc05-943">Keyword_ [province_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="abc05-943">Keyword_[province_name]_drivers_license_name</span></span>

- <span data-ttu-id="abc05-944">시/도 약어(예: AB)</span><span class="sxs-lookup"><span data-stu-id="abc05-944">The province abbreviation, for example AB</span></span>
- <span data-ttu-id="abc05-945">시/도 이름(예: 앨버타)</span><span class="sxs-lookup"><span data-stu-id="abc05-945">The province name, for example Alberta</span></span>

#### <a name="keyword_canada_drivers_license"></a><span data-ttu-id="abc05-946">Keyword_canada_drivers_license</span><span class="sxs-lookup"><span data-stu-id="abc05-946">Keyword_canada_drivers_license</span></span>

- <span data-ttu-id="abc05-947">DL</span><span class="sxs-lookup"><span data-stu-id="abc05-947">DL</span></span>
- <span data-ttu-id="abc05-948">된다</span><span class="sxs-lookup"><span data-stu-id="abc05-948">DLS</span></span>
- <span data-ttu-id="abc05-949">CDL</span><span class="sxs-lookup"><span data-stu-id="abc05-949">CDL</span></span>
- <span data-ttu-id="abc05-950">CDLS</span><span class="sxs-lookup"><span data-stu-id="abc05-950">CDLS</span></span>
- <span data-ttu-id="abc05-951">DriverLic</span><span class="sxs-lookup"><span data-stu-id="abc05-951">DriverLic</span></span>
- <span data-ttu-id="abc05-952">DriverLics</span><span class="sxs-lookup"><span data-stu-id="abc05-952">DriverLics</span></span>
- <span data-ttu-id="abc05-953">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-953">DriverLicense</span></span>
- <span data-ttu-id="abc05-954">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-954">DriverLicenses</span></span>
- <span data-ttu-id="abc05-955">DriverLicence</span><span class="sxs-lookup"><span data-stu-id="abc05-955">DriverLicence</span></span>
- <span data-ttu-id="abc05-956">DriverLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-956">DriverLicences</span></span>
- <span data-ttu-id="abc05-957">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-957">Driver Lic</span></span>
- <span data-ttu-id="abc05-958">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-958">Driver Lics</span></span>
- <span data-ttu-id="abc05-959">Driver License</span><span class="sxs-lookup"><span data-stu-id="abc05-959">Driver License</span></span>
- <span data-ttu-id="abc05-960">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-960">Driver Licenses</span></span>
- <span data-ttu-id="abc05-961">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-961">Driver Licence</span></span>
- <span data-ttu-id="abc05-962">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-962">Driver Licences</span></span>
- <span data-ttu-id="abc05-963">DriversLic</span><span class="sxs-lookup"><span data-stu-id="abc05-963">DriversLic</span></span>
- <span data-ttu-id="abc05-964">DriversLics</span><span class="sxs-lookup"><span data-stu-id="abc05-964">DriversLics</span></span>
- <span data-ttu-id="abc05-965">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-965">DriversLicence</span></span>
- <span data-ttu-id="abc05-966">DriversLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-966">DriversLicences</span></span>
- <span data-ttu-id="abc05-967">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-967">DriversLicense</span></span>
- <span data-ttu-id="abc05-968">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-968">DriversLicenses</span></span>
- <span data-ttu-id="abc05-969">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-969">Drivers Lic</span></span>
- <span data-ttu-id="abc05-970">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-970">Drivers Lics</span></span>
- <span data-ttu-id="abc05-971">Drivers License</span><span class="sxs-lookup"><span data-stu-id="abc05-971">Drivers License</span></span>
- <span data-ttu-id="abc05-972">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-972">Drivers Licenses</span></span>
- <span data-ttu-id="abc05-973">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-973">Drivers Licence</span></span>
- <span data-ttu-id="abc05-974">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-974">Drivers Licences</span></span>
- <span data-ttu-id="abc05-975">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-975">Driver'Lic</span></span>
- <span data-ttu-id="abc05-976">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-976">Driver'Lics</span></span>
- <span data-ttu-id="abc05-977">Driver' 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-977">Driver'License</span></span>
- <span data-ttu-id="abc05-978">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-978">Driver'Licenses</span></span>
- <span data-ttu-id="abc05-979">Driver' 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-979">Driver'Licence</span></span>
- <span data-ttu-id="abc05-980">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-980">Driver'Licences</span></span>
- <span data-ttu-id="abc05-981">Driver'Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-981">Driver' Lic</span></span>
- <span data-ttu-id="abc05-982">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-982">Driver' Lics</span></span>
- <span data-ttu-id="abc05-983">Driver' License</span><span class="sxs-lookup"><span data-stu-id="abc05-983">Driver' License</span></span>
- <span data-ttu-id="abc05-984">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-984">Driver' Licenses</span></span>
- <span data-ttu-id="abc05-985">Driver'Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-985">Driver' Licence</span></span>
- <span data-ttu-id="abc05-986">Driver'Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-986">Driver' Licences</span></span>
- <span data-ttu-id="abc05-987">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="abc05-987">Driver'sLic</span></span>
- <span data-ttu-id="abc05-988">Drivers (Slics)</span><span class="sxs-lookup"><span data-stu-id="abc05-988">Driver'sLics</span></span>
- <span data-ttu-id="abc05-989">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-989">Driver'sLicense</span></span>
- <span data-ttu-id="abc05-990">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-990">Driver'sLicenses</span></span>
- <span data-ttu-id="abc05-991">Driver'sLicence</span><span class="sxs-lookup"><span data-stu-id="abc05-991">Driver'sLicence</span></span>
- <span data-ttu-id="abc05-992">Driver'sLicences</span><span class="sxs-lookup"><span data-stu-id="abc05-992">Driver'sLicences</span></span>
- <span data-ttu-id="abc05-993">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-993">Driver's Lic</span></span>
- <span data-ttu-id="abc05-994">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-994">Driver's Lics</span></span>
- <span data-ttu-id="abc05-995">Driver's License</span><span class="sxs-lookup"><span data-stu-id="abc05-995">Driver's License</span></span>
- <span data-ttu-id="abc05-996">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-996">Driver's Licenses</span></span>
- <span data-ttu-id="abc05-997">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-997">Driver's Licence</span></span>
- <span data-ttu-id="abc05-998">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-998">Driver's Licences</span></span>
- <span data-ttu-id="abc05-999">Permis de Conduire</span><span class="sxs-lookup"><span data-stu-id="abc05-999">Permis de Conduire</span></span>
- <span data-ttu-id="abc05-1000">id</span><span class="sxs-lookup"><span data-stu-id="abc05-1000">id</span></span>
- <span data-ttu-id="abc05-1001">번호가</span><span class="sxs-lookup"><span data-stu-id="abc05-1001">ids</span></span>
- <span data-ttu-id="abc05-1002">idcard number</span><span class="sxs-lookup"><span data-stu-id="abc05-1002">idcard number</span></span>
- <span data-ttu-id="abc05-1003">idcard numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-1003">idcard numbers</span></span>
- <span data-ttu-id="abc05-1004">idcard #</span><span class="sxs-lookup"><span data-stu-id="abc05-1004">idcard #</span></span>
- <span data-ttu-id="abc05-1005">idcard #s</span><span class="sxs-lookup"><span data-stu-id="abc05-1005">idcard #s</span></span>
- <span data-ttu-id="abc05-1006">idcard card</span><span class="sxs-lookup"><span data-stu-id="abc05-1006">idcard card</span></span>
- <span data-ttu-id="abc05-1007">idcard cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1007">idcard cards</span></span>
- <span data-ttu-id="abc05-1008">idcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1008">idcard</span></span>
- <span data-ttu-id="abc05-1009">identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-1009">identification number</span></span>
- <span data-ttu-id="abc05-1010">identification numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-1010">identification numbers</span></span>
- <span data-ttu-id="abc05-1011">identification #</span><span class="sxs-lookup"><span data-stu-id="abc05-1011">identification #</span></span>
- <span data-ttu-id="abc05-1012">identification #s</span><span class="sxs-lookup"><span data-stu-id="abc05-1012">identification #s</span></span>
- <span data-ttu-id="abc05-1013">identification card</span><span class="sxs-lookup"><span data-stu-id="abc05-1013">identification card</span></span>
- <span data-ttu-id="abc05-1014">identification cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1014">identification cards</span></span>
- <span data-ttu-id="abc05-1015">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-1015">identification</span></span> 
- <span data-ttu-id="abc05-1016">DL #</span><span class="sxs-lookup"><span data-stu-id="abc05-1016">DL#</span></span>
- <span data-ttu-id="abc05-1017">된다 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1017">DLS#</span></span> 
- <span data-ttu-id="abc05-1018">CDL #</span><span class="sxs-lookup"><span data-stu-id="abc05-1018">CDL#</span></span> 
- <span data-ttu-id="abc05-1019">CDLS #</span><span class="sxs-lookup"><span data-stu-id="abc05-1019">CDLS#</span></span> 
- <span data-ttu-id="abc05-1020">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-1020">DriverLic#</span></span> 
- <span data-ttu-id="abc05-1021">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-1021">DriverLics#</span></span> 
- <span data-ttu-id="abc05-1022">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-1022">DriverLicense#</span></span> 
- <span data-ttu-id="abc05-1023">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-1023">DriverLicenses#</span></span> 
- <span data-ttu-id="abc05-1024">DriverLicence #</span><span class="sxs-lookup"><span data-stu-id="abc05-1024">DriverLicence#</span></span> 
- <span data-ttu-id="abc05-1025">DriverLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-1025">DriverLicences#</span></span> 
- <span data-ttu-id="abc05-1026">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-1026">Driver Lic#</span></span>
- <span data-ttu-id="abc05-1027">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-1027">Driver Lics#</span></span> 
- <span data-ttu-id="abc05-1028">Driver License#</span><span class="sxs-lookup"><span data-stu-id="abc05-1028">Driver License#</span></span> 
- <span data-ttu-id="abc05-1029">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-1029">Driver Licenses#</span></span> 
- <span data-ttu-id="abc05-1030">Driver License#</span><span class="sxs-lookup"><span data-stu-id="abc05-1030">Driver License#</span></span> 
- <span data-ttu-id="abc05-1031">Driver Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-1031">Driver Licences#</span></span> 
- <span data-ttu-id="abc05-1032">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-1032">DriversLic#</span></span> 
- <span data-ttu-id="abc05-1033">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-1033">DriversLics#</span></span> 
- <span data-ttu-id="abc05-1034">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1034">DriversLicense#</span></span> 
- <span data-ttu-id="abc05-1035">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1035">DriversLicenses#</span></span> 
- <span data-ttu-id="abc05-1036">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1036">DriversLicence#</span></span> 
- <span data-ttu-id="abc05-1037">DriversLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-1037">DriversLicences#</span></span> 
- <span data-ttu-id="abc05-1038">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-1038">Drivers Lic#</span></span> 
- <span data-ttu-id="abc05-1039">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-1039">Drivers Lics#</span></span> 
- <span data-ttu-id="abc05-1040">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="abc05-1040">Drivers License#</span></span> 
- <span data-ttu-id="abc05-1041">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-1041">Drivers Licenses#</span></span> 
- <span data-ttu-id="abc05-1042">Drivers Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-1042">Drivers Licence#</span></span> 
- <span data-ttu-id="abc05-1043">Drivers Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-1043">Drivers Licences#</span></span> 
- <span data-ttu-id="abc05-1044">Driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="abc05-1044">Driver'Lic#</span></span> 
- <span data-ttu-id="abc05-1045">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="abc05-1045">Driver'Lics#</span></span> 
- <span data-ttu-id="abc05-1046">Driver' 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1046">Driver'License#</span></span> 
- <span data-ttu-id="abc05-1047">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-1047">Driver'Licenses#</span></span> 
- <span data-ttu-id="abc05-1048">Driver' 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1048">Driver'Licence#</span></span> 
- <span data-ttu-id="abc05-1049">Driver'Licences #</span><span class="sxs-lookup"><span data-stu-id="abc05-1049">Driver'Licences#</span></span> 
- <span data-ttu-id="abc05-1050">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-1050">Driver' Lic#</span></span> 
- <span data-ttu-id="abc05-1051">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-1051">Driver' Lics#</span></span> 
- <span data-ttu-id="abc05-1052">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="abc05-1052">Driver' License#</span></span> 
- <span data-ttu-id="abc05-1053">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-1053">Driver' Licenses#</span></span> 
- <span data-ttu-id="abc05-1054">Driver' Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-1054">Driver' Licence#</span></span> 
- <span data-ttu-id="abc05-1055">Driver' Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-1055">Driver' Licences#</span></span> 
- <span data-ttu-id="abc05-1056">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-1056">Driver'sLic#</span></span> 
- <span data-ttu-id="abc05-1057">Drivers (Slics) #</span><span class="sxs-lookup"><span data-stu-id="abc05-1057">Driver'sLics#</span></span> 
- <span data-ttu-id="abc05-1058">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-1058">Driver'sLicense#</span></span> 
- <span data-ttu-id="abc05-1059">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-1059">Driver'sLicenses#</span></span> 
- <span data-ttu-id="abc05-1060">Driver'sLicence #</span><span class="sxs-lookup"><span data-stu-id="abc05-1060">Driver'sLicence#</span></span> 
- <span data-ttu-id="abc05-1061">Driver'sLicences #</span><span class="sxs-lookup"><span data-stu-id="abc05-1061">Driver'sLicences#</span></span> 
- <span data-ttu-id="abc05-1062">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-1062">Driver's Lic#</span></span> 
- <span data-ttu-id="abc05-1063">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-1063">Driver's Lics#</span></span> 
- <span data-ttu-id="abc05-1064">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="abc05-1064">Driver's License#</span></span> 
- <span data-ttu-id="abc05-1065">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-1065">Driver's Licenses#</span></span> 
- <span data-ttu-id="abc05-1066">Driver's Licence#</span><span class="sxs-lookup"><span data-stu-id="abc05-1066">Driver's Licence#</span></span> 
- <span data-ttu-id="abc05-1067">Driver's Licences#</span><span class="sxs-lookup"><span data-stu-id="abc05-1067">Driver's Licences#</span></span> 
- <span data-ttu-id="abc05-1068">Permis de Conduire#</span><span class="sxs-lookup"><span data-stu-id="abc05-1068">Permis de Conduire#</span></span> 
- <span data-ttu-id="abc05-1069">i #</span><span class="sxs-lookup"><span data-stu-id="abc05-1069">id#</span></span> 
- <span data-ttu-id="abc05-1070">번호가 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1070">ids#</span></span> 
- <span data-ttu-id="abc05-1071">idcard card#</span><span class="sxs-lookup"><span data-stu-id="abc05-1071">idcard card#</span></span> 
- <span data-ttu-id="abc05-1072">idcard cards#</span><span class="sxs-lookup"><span data-stu-id="abc05-1072">idcard cards#</span></span> 
- <span data-ttu-id="abc05-1073">idcard #</span><span class="sxs-lookup"><span data-stu-id="abc05-1073">idcard#</span></span> 
- <span data-ttu-id="abc05-1074">identification card#</span><span class="sxs-lookup"><span data-stu-id="abc05-1074">identification card#</span></span> 
- <span data-ttu-id="abc05-1075">identification cards#</span><span class="sxs-lookup"><span data-stu-id="abc05-1075">identification cards#</span></span> 
- <span data-ttu-id="abc05-1076">확인과 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1076">identification#</span></span> 
   
## <a name="canada-health-service-number"></a><span data-ttu-id="abc05-1077">캐나다 건강 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1077">Canada Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1078">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1078">Format</span></span>

<span data-ttu-id="abc05-1079">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1079">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1080">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1080">Pattern</span></span>

<span data-ttu-id="abc05-1081">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1081">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1082">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1082">Checksum</span></span>

<span data-ttu-id="abc05-1083">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-1083">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1084">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1084">Definition</span></span>

<span data-ttu-id="abc05-1085">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1085">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1086">Regex_canada_health_service_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1086">The regular expression Regex_canada_health_service_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1087">Keyword_canada_health_service_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1087">A keyword from Keyword_canada_health_service_number is found.</span></span>

```xml
<!-- Canada Health Service Number -->
<Entity id="59c0bf39-7fab-482c-af25-00faa4384c94" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_health_service_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_health_service_number" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1088">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1088">Keywords</span></span>

#### <a name="keyword_canada_health_service_number"></a><span data-ttu-id="abc05-1089">Keyword_canada_health_service_number</span><span class="sxs-lookup"><span data-stu-id="abc05-1089">Keyword_canada_health_service_number</span></span>

- <span data-ttu-id="abc05-1090">personal health number</span><span class="sxs-lookup"><span data-stu-id="abc05-1090">personal health number</span></span>
- <span data-ttu-id="abc05-1091">patient information</span><span class="sxs-lookup"><span data-stu-id="abc05-1091">patient information</span></span>
- <span data-ttu-id="abc05-1092">health services</span><span class="sxs-lookup"><span data-stu-id="abc05-1092">health services</span></span>
- <span data-ttu-id="abc05-1093">speciality services</span><span class="sxs-lookup"><span data-stu-id="abc05-1093">speciality services</span></span>
- <span data-ttu-id="abc05-1094">automobile accident</span><span class="sxs-lookup"><span data-stu-id="abc05-1094">automobile accident</span></span>
- <span data-ttu-id="abc05-1095">patient hospital</span><span class="sxs-lookup"><span data-stu-id="abc05-1095">patient hospital</span></span>
- <span data-ttu-id="abc05-1096">psychiatrist</span><span class="sxs-lookup"><span data-stu-id="abc05-1096">psychiatrist</span></span>
- <span data-ttu-id="abc05-1097">workers compensation</span><span class="sxs-lookup"><span data-stu-id="abc05-1097">workers compensation</span></span>
- <span data-ttu-id="abc05-1098">종류</span><span class="sxs-lookup"><span data-stu-id="abc05-1098">disability</span></span>
      
## <a name="canada-passport-number"></a><span data-ttu-id="abc05-1099">캐나다 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1099">Canada Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1100">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1100">Format</span></span>

<span data-ttu-id="abc05-1101">2개의 대문자와 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1101">Two uppercase letters followed by six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1102">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1102">Pattern</span></span>

<span data-ttu-id="abc05-1103">2개의 대문자와 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1103">Two uppercase letters followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1104">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1104">Checksum</span></span>

<span data-ttu-id="abc05-1105">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-1105">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1106">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1106">Definition</span></span>

<span data-ttu-id="abc05-1107">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1107">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1108">Regex_canada_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1108">The regular expression Regex_canada_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1109">Keyword_canada_passport_number 또는 Keyword_passport의 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1109">A keyword from Keyword_canada_passport_number or Keyword_passport is found.</span></span>

```xml 
<!-- Canada Passport Number -->
<Entity id="14d0db8b-498a-43ed-9fca-f6097ae687eb" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_canada_passport_number" />
          <Match idRef="Keyword_passport" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1110">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1110">Keywords</span></span>

#### <a name="keyword_canada_passport_number"></a><span data-ttu-id="abc05-1111">Keyword_canada_passport_number</span><span class="sxs-lookup"><span data-stu-id="abc05-1111">Keyword_canada_passport_number</span></span>

- <span data-ttu-id="abc05-1112">canadian citizenship</span><span class="sxs-lookup"><span data-stu-id="abc05-1112">canadian citizenship</span></span>
- <span data-ttu-id="abc05-1113">canadian passport</span><span class="sxs-lookup"><span data-stu-id="abc05-1113">canadian passport</span></span>
- <span data-ttu-id="abc05-1114">passport application</span><span class="sxs-lookup"><span data-stu-id="abc05-1114">passport application</span></span>
- <span data-ttu-id="abc05-1115">passport photos</span><span class="sxs-lookup"><span data-stu-id="abc05-1115">passport photos</span></span>
- <span data-ttu-id="abc05-1116">certified translator</span><span class="sxs-lookup"><span data-stu-id="abc05-1116">certified translator</span></span>
- <span data-ttu-id="abc05-1117">canadian citizens</span><span class="sxs-lookup"><span data-stu-id="abc05-1117">canadian citizens</span></span>
- <span data-ttu-id="abc05-1118">processing times</span><span class="sxs-lookup"><span data-stu-id="abc05-1118">processing times</span></span>
- <span data-ttu-id="abc05-1119">renewal application</span><span class="sxs-lookup"><span data-stu-id="abc05-1119">renewal application</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="abc05-1120">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-1120">Keyword_passport</span></span>

- <span data-ttu-id="abc05-1121">Passport Number</span><span class="sxs-lookup"><span data-stu-id="abc05-1121">Passport Number</span></span>
- <span data-ttu-id="abc05-1122">Passport No</span><span class="sxs-lookup"><span data-stu-id="abc05-1122">Passport No</span></span>
- <span data-ttu-id="abc05-1123">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-1123">Passport #</span></span>
- <span data-ttu-id="abc05-1124">여권 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1124">Passport#</span></span>
- <span data-ttu-id="abc05-1125">PassportID</span><span class="sxs-lookup"><span data-stu-id="abc05-1125">PassportID</span></span>
- <span data-ttu-id="abc05-1126">Passportno</span><span class="sxs-lookup"><span data-stu-id="abc05-1126">Passportno</span></span>
- <span data-ttu-id="abc05-1127">passportnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-1127">passportnumber</span></span>
- <span data-ttu-id="abc05-1128">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-1128">パスポート</span></span>
- <span data-ttu-id="abc05-1129">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-1129">パスポート番号</span></span>
- <span data-ttu-id="abc05-1130">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-1130">パスポートのNum</span></span>
- <span data-ttu-id="abc05-1131">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="abc05-1131">パスポート＃</span></span>
- <span data-ttu-id="abc05-1132">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="abc05-1132">Numéro de passeport</span></span>
- <span data-ttu-id="abc05-1133">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="abc05-1133">Passeport n °</span></span>
- <span data-ttu-id="abc05-1134">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="abc05-1134">Passeport Non</span></span>
- <span data-ttu-id="abc05-1135">Passeport #</span><span class="sxs-lookup"><span data-stu-id="abc05-1135">Passeport #</span></span>
- <span data-ttu-id="abc05-1136">포트 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1136">Passeport#</span></span>
- <span data-ttu-id="abc05-1137">지/포트 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-1137">PasseportNon</span></span>
- <span data-ttu-id="abc05-1138">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="abc05-1138">Passeportn °</span></span>
   
## <a name="canada-personal-health-identification-number-phin"></a><span data-ttu-id="abc05-1139">캐나다 PHIN(개인 건강 식별 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-1139">Canada Personal Health Identification Number (PHIN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1140">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1140">Format</span></span>

<span data-ttu-id="abc05-1141">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1141">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1142">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1142">Pattern</span></span>

<span data-ttu-id="abc05-1143">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1143">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1144">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1144">Checksum</span></span>

<span data-ttu-id="abc05-1145">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-1145">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1146">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1146">Definition</span></span>

<span data-ttu-id="abc05-1147">DLP 정책은 300 Regex_canada_phin 문자 근사에서 해당 패턴과 일치 하는 콘텐츠를 찾는 경우이 유형의 중요 한 정보를 검색 한다는 것을 75% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1147">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_canada_phin finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-1148">Keyword_canada_phin 또는 Keyword_canada_provinces에서 키워드가 두 개 이상 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1148">At least two keywords from Keyword_canada_phin or Keyword_canada_provinces are found..</span></span>

```xml
<!-- Canada PHIN -->
<Entity id="722e12ac-c89a-4ec8-a1b7-fea3469f89db" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_canada_phin" />
        <Any minMatches="2">
          <Match idRef="Keyword_canada_phin" />
          <Match idRef="Keyword_canada_provinces" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1149">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1149">Keywords</span></span>

#### <a name="keyword_canada_phin"></a><span data-ttu-id="abc05-1150">Keyword_canada_phin</span><span class="sxs-lookup"><span data-stu-id="abc05-1150">Keyword_canada_phin</span></span>

- <span data-ttu-id="abc05-1151">social insurance number</span><span class="sxs-lookup"><span data-stu-id="abc05-1151">social insurance number</span></span>
- <span data-ttu-id="abc05-1152">health information act</span><span class="sxs-lookup"><span data-stu-id="abc05-1152">health information act</span></span>
- <span data-ttu-id="abc05-1153">income tax information</span><span class="sxs-lookup"><span data-stu-id="abc05-1153">income tax information</span></span>
- <span data-ttu-id="abc05-1154">manitoba health</span><span class="sxs-lookup"><span data-stu-id="abc05-1154">manitoba health</span></span>
- <span data-ttu-id="abc05-1155">health registration</span><span class="sxs-lookup"><span data-stu-id="abc05-1155">health registration</span></span>
- <span data-ttu-id="abc05-1156">prescription purchases</span><span class="sxs-lookup"><span data-stu-id="abc05-1156">prescription purchases</span></span>
- <span data-ttu-id="abc05-1157">benefit eligibility</span><span class="sxs-lookup"><span data-stu-id="abc05-1157">benefit eligibility</span></span>
- <span data-ttu-id="abc05-1158">personal health</span><span class="sxs-lookup"><span data-stu-id="abc05-1158">personal health</span></span>
- <span data-ttu-id="abc05-1159">power of attorney</span><span class="sxs-lookup"><span data-stu-id="abc05-1159">power of attorney</span></span>
- <span data-ttu-id="abc05-1160">registration number</span><span class="sxs-lookup"><span data-stu-id="abc05-1160">registration number</span></span>
- <span data-ttu-id="abc05-1161">personal health number</span><span class="sxs-lookup"><span data-stu-id="abc05-1161">personal health number</span></span>
- <span data-ttu-id="abc05-1162">practitioner referral</span><span class="sxs-lookup"><span data-stu-id="abc05-1162">practitioner referral</span></span>
- <span data-ttu-id="abc05-1163">wellness professional</span><span class="sxs-lookup"><span data-stu-id="abc05-1163">wellness professional</span></span>
- <span data-ttu-id="abc05-1164">patient referral</span><span class="sxs-lookup"><span data-stu-id="abc05-1164">patient referral</span></span>
- <span data-ttu-id="abc05-1165">health and wellness</span><span class="sxs-lookup"><span data-stu-id="abc05-1165">health and wellness</span></span>

#### <a name="keyword_canada_provinces"></a><span data-ttu-id="abc05-1166">Keyword_canada_provinces</span><span class="sxs-lookup"><span data-stu-id="abc05-1166">Keyword_canada_provinces</span></span>

- <span data-ttu-id="abc05-1167">Nunavut</span><span class="sxs-lookup"><span data-stu-id="abc05-1167">Nunavut</span></span>
- <span data-ttu-id="abc05-1168">퀘벡</span><span class="sxs-lookup"><span data-stu-id="abc05-1168">Quebec</span></span>
- <span data-ttu-id="abc05-1169">Northwest Territories</span><span class="sxs-lookup"><span data-stu-id="abc05-1169">Northwest Territories</span></span>
- <span data-ttu-id="abc05-1170">온타리오</span><span class="sxs-lookup"><span data-stu-id="abc05-1170">Ontario</span></span>
- <span data-ttu-id="abc05-1171">British Columbia</span><span class="sxs-lookup"><span data-stu-id="abc05-1171">British Columbia</span></span>
- <span data-ttu-id="abc05-1172">앨버타</span><span class="sxs-lookup"><span data-stu-id="abc05-1172">Alberta</span></span>
- <span data-ttu-id="abc05-1173">서스캐처원</span><span class="sxs-lookup"><span data-stu-id="abc05-1173">Saskatchewan</span></span>
- <span data-ttu-id="abc05-1174">매니토바</span><span class="sxs-lookup"><span data-stu-id="abc05-1174">Manitoba</span></span>
- <span data-ttu-id="abc05-1175">Yukon</span><span class="sxs-lookup"><span data-stu-id="abc05-1175">Yukon</span></span>
- <span data-ttu-id="abc05-1176">Newfoundland and Labrador</span><span class="sxs-lookup"><span data-stu-id="abc05-1176">Newfoundland and Labrador</span></span>
- <span data-ttu-id="abc05-1177">New Brunswick</span><span class="sxs-lookup"><span data-stu-id="abc05-1177">New Brunswick</span></span>
- <span data-ttu-id="abc05-1178">Nova Scotia</span><span class="sxs-lookup"><span data-stu-id="abc05-1178">Nova Scotia</span></span>
- <span data-ttu-id="abc05-1179">Prince Edward Island</span><span class="sxs-lookup"><span data-stu-id="abc05-1179">Prince Edward Island</span></span>
- <span data-ttu-id="abc05-1180">캐나다</span><span class="sxs-lookup"><span data-stu-id="abc05-1180">Canada</span></span>
   
## <a name="canada-social-insurance-number"></a><span data-ttu-id="abc05-1181">캐나다 사회 보험 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1181">Canada Social Insurance Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1182">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1182">Format</span></span>

<span data-ttu-id="abc05-1183">선택적 하이픈 또는 공백을 포함하는 9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1183">Nine digits with optional hyphens or spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1184">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1184">Pattern</span></span>

<span data-ttu-id="abc05-1185">서식이</span><span class="sxs-lookup"><span data-stu-id="abc05-1185">Formatted:</span></span>
- <span data-ttu-id="abc05-1186">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1186">Three digits</span></span> 
- <span data-ttu-id="abc05-1187">하이픈 또는 공백</span><span class="sxs-lookup"><span data-stu-id="abc05-1187">A hyphen or space</span></span> 
- <span data-ttu-id="abc05-1188">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1188">Three digits</span></span> 
- <span data-ttu-id="abc05-1189">하이픈 또는 공백</span><span class="sxs-lookup"><span data-stu-id="abc05-1189">A hyphen or space</span></span> 
- <span data-ttu-id="abc05-1190">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1190">Three digits</span></span>

<span data-ttu-id="abc05-1191">서식 없음: 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1191">Unformatted: Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1192">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1192">Checksum</span></span>

<span data-ttu-id="abc05-1193">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1193">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1194">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1194">Definition</span></span>

<span data-ttu-id="abc05-1195">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1195">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1196">Func_canadian_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1196">The function Func_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1197">2개 이상의 다음 항목 조합:</span><span class="sxs-lookup"><span data-stu-id="abc05-1197">At least two of any combination of the following:</span></span>
    - <span data-ttu-id="abc05-1198">Keyword_sin의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1198">A keyword from Keyword_sin is found.</span></span>
    - <span data-ttu-id="abc05-1199">Keyword_sin_collaborative의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1199">A keyword from Keyword_sin_collaborative is found.</span></span>
    - <span data-ttu-id="abc05-1200">Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1200">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-1201">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1201">The checksum passes.</span></span>

<span data-ttu-id="abc05-1202">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1202">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1203">Func_unformatted_canadian_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1203">The function Func_unformatted_canadian_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1204">Keyword_sin의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1204">A keyword from Keyword_sin is found.</span></span>
- <span data-ttu-id="abc05-1205">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1205">The checksum passes.</span></span>

```xml
<!-- Canada Social Insurance Number -->
<Entity id="a2f29c85-ecb8-4514-a610-364790c0773e" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_canadian_sin" />
        <Any minMatches="2">
          <Match idRef="Keyword_sin" />
          <Match idRef="Keyword_sin_collaborative" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_canadian_sin" />
        <Match idRef="Keyword_sin" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1206">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1206">Keywords</span></span>

#### <a name="keyword_sin"></a><span data-ttu-id="abc05-1207">Keyword_sin</span><span class="sxs-lookup"><span data-stu-id="abc05-1207">Keyword_sin</span></span>

- <span data-ttu-id="abc05-1208">sin</span><span class="sxs-lookup"><span data-stu-id="abc05-1208">sin</span></span> 
- <span data-ttu-id="abc05-1209">social insurance</span><span class="sxs-lookup"><span data-stu-id="abc05-1209">social insurance</span></span> 
- <span data-ttu-id="abc05-1210">numero d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-1210">numero d'assurance sociale</span></span> 
- <span data-ttu-id="abc05-1211">죄</span><span class="sxs-lookup"><span data-stu-id="abc05-1211">sins</span></span> 
- <span data-ttu-id="abc05-1212">ssn</span><span class="sxs-lookup"><span data-stu-id="abc05-1212">ssn</span></span> 
- <span data-ttu-id="abc05-1213">있는 ssn</span><span class="sxs-lookup"><span data-stu-id="abc05-1213">ssns</span></span> 
- <span data-ttu-id="abc05-1214">social security</span><span class="sxs-lookup"><span data-stu-id="abc05-1214">social security</span></span> 
- <span data-ttu-id="abc05-1215">numero d'assurance social</span><span class="sxs-lookup"><span data-stu-id="abc05-1215">numero d'assurance social</span></span> 
- <span data-ttu-id="abc05-1216">national identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-1216">national identification number</span></span> 
- <span data-ttu-id="abc05-1217">national id</span><span class="sxs-lookup"><span data-stu-id="abc05-1217">national id</span></span> 
- <span data-ttu-id="abc05-1218">sin #</span><span class="sxs-lookup"><span data-stu-id="abc05-1218">sin#</span></span> 
- <span data-ttu-id="abc05-1219">soc ins</span><span class="sxs-lookup"><span data-stu-id="abc05-1219">soc ins</span></span> 
- <span data-ttu-id="abc05-1220">social ins</span><span class="sxs-lookup"><span data-stu-id="abc05-1220">social ins</span></span> 

#### <a name="keyword_sin_collaborative"></a><span data-ttu-id="abc05-1221">Keyword_sin_collaborative</span><span class="sxs-lookup"><span data-stu-id="abc05-1221">Keyword_sin_collaborative</span></span>

- <span data-ttu-id="abc05-1222">driver's license</span><span class="sxs-lookup"><span data-stu-id="abc05-1222">driver's license</span></span> 
- <span data-ttu-id="abc05-1223">drivers license</span><span class="sxs-lookup"><span data-stu-id="abc05-1223">drivers license</span></span> 
- <span data-ttu-id="abc05-1224">driver's licence</span><span class="sxs-lookup"><span data-stu-id="abc05-1224">driver's licence</span></span> 
- <span data-ttu-id="abc05-1225">drivers licence</span><span class="sxs-lookup"><span data-stu-id="abc05-1225">drivers licence</span></span> 
- <span data-ttu-id="abc05-1226">DOB</span><span class="sxs-lookup"><span data-stu-id="abc05-1226">DOB</span></span> 
- <span data-ttu-id="abc05-1227">생년월일</span><span class="sxs-lookup"><span data-stu-id="abc05-1227">Birthdate</span></span> 
- <span data-ttu-id="abc05-1228">생일</span><span class="sxs-lookup"><span data-stu-id="abc05-1228">Birthday</span></span> 
- <span data-ttu-id="abc05-1229">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="abc05-1229">Date of Birth</span></span> 
   
## <a name="chile-identity-card-number"></a><span data-ttu-id="abc05-1230">	칠레 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1230">Chile Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1231">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1231">Format</span></span>

<span data-ttu-id="abc05-1232">7-8 자리 숫자와 구분 기호 확인 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-1232">7-8 digits plus delimiters a check digit or letter</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1233">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1233">Pattern</span></span>

<span data-ttu-id="abc05-1234">7-8자리 숫자와 구분 기호:</span><span class="sxs-lookup"><span data-stu-id="abc05-1234">7-8 digits plus delimiters:</span></span>
- <span data-ttu-id="abc05-1235">1-2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1235">1-2 digits</span></span> 
- <span data-ttu-id="abc05-1236">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-1236">A period</span></span> 
- <span data-ttu-id="abc05-1237">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1237">Three digits</span></span> 
- <span data-ttu-id="abc05-1238">마침표 </span><span class="sxs-lookup"><span data-stu-id="abc05-1238">A period</span></span> 
- <span data-ttu-id="abc05-1239">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1239">Three digits</span></span> 
- <span data-ttu-id="abc05-1240">대시 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-1240">A dash</span></span> 
- <span data-ttu-id="abc05-1241">검사 숫자에 해당하는 1자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-1241">One digit or letter (not case sensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1242">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1242">Checksum</span></span>

<span data-ttu-id="abc05-1243">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1243">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1244">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1244">Definition</span></span>

<span data-ttu-id="abc05-1245">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1245">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1246">Func_chile_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1246">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1247">Keyword_chile_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1247">A keyword from Keyword_chile_id_card is found.</span></span>
- <span data-ttu-id="abc05-1248">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1248">The checksum passes.</span></span>

<span data-ttu-id="abc05-1249">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1249">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1250">Func_chile_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1250">The function Func_chile_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1251">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1251">The checksum passes.</span></span>

```xml
<!-- Chile Identity Card Number -->
<Entity id="4e979794-49a0-407e-a0b9-2c536937b925" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_chile_id_card"/>
     <Match idRef="Keyword_chile_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_chile_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1252">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1252">Keywords</span></span>

#### <a name="keyword_chile_id_card"></a><span data-ttu-id="abc05-1253">Keyword_chile_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-1253">Keyword_chile_id_card</span></span>

- <span data-ttu-id="abc05-1254">National Identification Number</span><span class="sxs-lookup"><span data-stu-id="abc05-1254">National Identification Number</span></span> 
- <span data-ttu-id="abc05-1255">Identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-1255">Identity card</span></span> 
- <span data-ttu-id="abc05-1256">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-1256">ID</span></span> 
- <span data-ttu-id="abc05-1257">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-1257">Identification</span></span> 
- <span data-ttu-id="abc05-1258">Rol Único Nacional</span><span class="sxs-lookup"><span data-stu-id="abc05-1258">Rol Único Nacional</span></span> 
- <span data-ttu-id="abc05-1259">실행</span><span class="sxs-lookup"><span data-stu-id="abc05-1259">RUN</span></span> 
- <span data-ttu-id="abc05-1260">Rol Único Tributario</span><span class="sxs-lookup"><span data-stu-id="abc05-1260">Rol Único Tributario</span></span> 
- <span data-ttu-id="abc05-1261">RUT</span><span class="sxs-lookup"><span data-stu-id="abc05-1261">RUT</span></span> 
- <span data-ttu-id="abc05-1262">Cédula de Identidad</span><span class="sxs-lookup"><span data-stu-id="abc05-1262">Cédula de Identidad</span></span> 
- <span data-ttu-id="abc05-1263">Número De Identificación Nacional</span><span class="sxs-lookup"><span data-stu-id="abc05-1263">Número De Identificación Nacional</span></span> 
- <span data-ttu-id="abc05-1264">Tarjeta de identificación</span><span class="sxs-lookup"><span data-stu-id="abc05-1264">Tarjeta de identificación</span></span> 
- <span data-ttu-id="abc05-1265">Identificación</span><span class="sxs-lookup"><span data-stu-id="abc05-1265">Identificación</span></span> 
   
## <a name="china-resident-identity-card-prc-number"></a><span data-ttu-id="abc05-1266">	중국 주민 ID 카드(PRC) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1266">China Resident Identity Card (PRC) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1267">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1267">Format</span></span>

<span data-ttu-id="abc05-1268">18자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1268">18 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1269">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1269">Pattern</span></span>

<span data-ttu-id="abc05-1270">18자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-1270">18 digits:</span></span>
- <span data-ttu-id="abc05-1271">주소 코드에 해당하는 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-1271">Six digits which are an address code</span></span> 
- <span data-ttu-id="abc05-1272">생년월일에 해당하는 YYYYMMDD 형식의 8자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-1272">Eight digits in the form YYYYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="abc05-1273">주문 코드에 해당하는 3자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-1273">Three digits which are an order code</span></span> 
- <span data-ttu-id="abc05-1274">검사 숫자에 해당하는 1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1274">One digit which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1275">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1275">Checksum</span></span>

<span data-ttu-id="abc05-1276">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1276">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1277">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1277">Definition</span></span>

<span data-ttu-id="abc05-1278">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1278">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1279">Func_china_resident_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1279">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1280">Keyword_china_resident_id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1280">A keyword from Keyword_china_resident_id is found.</span></span>
- <span data-ttu-id="abc05-1281">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1281">The checksum passes.</span></span>

<span data-ttu-id="abc05-1282">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1282">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1283">Func_china_resident_id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1283">The function Func_china_resident_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1284">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1284">The checksum passes.</span></span>

```xml
<!-- China Resident Identity Card (PRC) Number -->
<Entity id="c92daa86-2d16-4871-901f-816b3f554fc1" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_china_resident_id"/>
     <Match idRef="Keyword_china_resident_id"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_china_resident_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1285">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1285">Keywords</span></span>

### <a name="keyword_china_resident_id"></a><span data-ttu-id="abc05-1286">Keyword_china_resident_id</span><span class="sxs-lookup"><span data-stu-id="abc05-1286">Keyword_china_resident_id</span></span>

- <span data-ttu-id="abc05-1287">Resident Identity Card</span><span class="sxs-lookup"><span data-stu-id="abc05-1287">Resident Identity Card</span></span> 
- <span data-ttu-id="abc05-1288">중국</span><span class="sxs-lookup"><span data-stu-id="abc05-1288">PRC</span></span> 
- <span data-ttu-id="abc05-1289">National Identification Card</span><span class="sxs-lookup"><span data-stu-id="abc05-1289">National Identification Card</span></span> 
- <span data-ttu-id="abc05-1290">身份证</span><span class="sxs-lookup"><span data-stu-id="abc05-1290">身份证</span></span> 
- <span data-ttu-id="abc05-1291">居民 身份证</span><span class="sxs-lookup"><span data-stu-id="abc05-1291">居民 身份证</span></span> 
- <span data-ttu-id="abc05-1292">居民身份证</span><span class="sxs-lookup"><span data-stu-id="abc05-1292">居民身份证</span></span> 
- <span data-ttu-id="abc05-1293">鉴定</span><span class="sxs-lookup"><span data-stu-id="abc05-1293">鉴定</span></span> 
- <span data-ttu-id="abc05-1294">身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-1294">身分證</span></span> 
- <span data-ttu-id="abc05-1295">居民 身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-1295">居民 身份證</span></span>
- <span data-ttu-id="abc05-1296">鑑定</span><span class="sxs-lookup"><span data-stu-id="abc05-1296">鑑定</span></span> 
   
## <a name="credit-card-number"></a><span data-ttu-id="abc05-1297">신용 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1297">Credit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1298">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1298">Format</span></span>

<span data-ttu-id="abc05-1299">서식이 있거나 서식이 없을 수 있는 16 자리 (dddddddddddddddd), Luhn 테스트를 통과 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1299">16 digits which can be formatted or unformatted (dddddddddddddddd) and must pass the Luhn test.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1300">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1300">Pattern</span></span>

<span data-ttu-id="abc05-1301">Visa, MasterCard, Discover Card, JCB, American Express, 상품권 및 식사권을 비롯하여 전 세계 모든 주요 브랜드 카드를 검색하는 매우 복잡하고 강력한 패턴입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1301">Very complex and robust pattern that detects cards from all major brands worldwide, including Visa, MasterCard, Discover Card, JCB, American Express, gift cards, and diner cards.</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1302">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1302">Checksum</span></span>

<span data-ttu-id="abc05-1303">있음(Luhn 체크섬)</span><span class="sxs-lookup"><span data-stu-id="abc05-1303">Yes, the Luhn checksum</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1304">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1304">Definition</span></span>

<span data-ttu-id="abc05-1305">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1305">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1306">Func_credit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1306">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1307">다음 중 하나가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1307">One of the following is true:</span></span>
    - <span data-ttu-id="abc05-1308">Keyword_cc_verification의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1308">A keyword from Keyword_cc_verification is found.</span></span>
    - <span data-ttu-id="abc05-1309">Keyword_cc_name의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1309">A keyword from Keyword_cc_name is found.</span></span>
    - <span data-ttu-id="abc05-1310">Func_expiration_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1310">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-1311">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1311">The checksum passes.</span></span>

<span data-ttu-id="abc05-1312">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1312">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1313">Func_credit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1313">The function Func_credit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1314">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1314">The checksum passes.</span></span>

```xml
<!-- Credit Card Number -->
<Entity id="50842eb7-edc8-4019-85dd-5a5c1f2bb085" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_credit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_cc_verification" />
          <Match idRef="Keyword_cc_name" />
          <Match idRef="Func_expiration_date" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_credit_card" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1315">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1315">Keywords</span></span>

#### <a name="keyword_cc_verification"></a><span data-ttu-id="abc05-1316">Keyword_cc_verification</span><span class="sxs-lookup"><span data-stu-id="abc05-1316">Keyword_cc_verification</span></span>

- <span data-ttu-id="abc05-1317">card verification</span><span class="sxs-lookup"><span data-stu-id="abc05-1317">card verification</span></span>
- <span data-ttu-id="abc05-1318">card identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-1318">card identification number</span></span>
- <span data-ttu-id="abc05-1319">cvn</span><span class="sxs-lookup"><span data-stu-id="abc05-1319">cvn</span></span>
- <span data-ttu-id="abc05-1320">cid</span><span class="sxs-lookup"><span data-stu-id="abc05-1320">cid</span></span>
- <span data-ttu-id="abc05-1321">cvc2</span><span class="sxs-lookup"><span data-stu-id="abc05-1321">cvc2</span></span>
- <span data-ttu-id="abc05-1322">cvv2</span><span class="sxs-lookup"><span data-stu-id="abc05-1322">cvv2</span></span>
- <span data-ttu-id="abc05-1323">pin block</span><span class="sxs-lookup"><span data-stu-id="abc05-1323">pin block</span></span>
- <span data-ttu-id="abc05-1324">security code</span><span class="sxs-lookup"><span data-stu-id="abc05-1324">security code</span></span>
- <span data-ttu-id="abc05-1325">security number</span><span class="sxs-lookup"><span data-stu-id="abc05-1325">security number</span></span>
- <span data-ttu-id="abc05-1326">security no</span><span class="sxs-lookup"><span data-stu-id="abc05-1326">security no</span></span>
- <span data-ttu-id="abc05-1327">issue number</span><span class="sxs-lookup"><span data-stu-id="abc05-1327">issue number</span></span>
- <span data-ttu-id="abc05-1328">issue no</span><span class="sxs-lookup"><span data-stu-id="abc05-1328">issue no</span></span>
- <span data-ttu-id="abc05-1329">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="abc05-1329">cryptogramme</span></span>
- <span data-ttu-id="abc05-1330">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="abc05-1330">numéro de sécurité</span></span>
- <span data-ttu-id="abc05-1331">numero de securite</span><span class="sxs-lookup"><span data-stu-id="abc05-1331">numero de securite</span></span>
- <span data-ttu-id="abc05-1332">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1332">kreditkartenprüfnummer</span></span>
- <span data-ttu-id="abc05-1333">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1333">kreditkartenprufnummer</span></span>
- <span data-ttu-id="abc05-1334">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="abc05-1334">prüfziffer</span></span>
- <span data-ttu-id="abc05-1335">prufziffer</span><span class="sxs-lookup"><span data-stu-id="abc05-1335">prufziffer</span></span>
- <span data-ttu-id="abc05-1336">sicherheits Kode</span><span class="sxs-lookup"><span data-stu-id="abc05-1336">sicherheits Kode</span></span>
- <span data-ttu-id="abc05-1337">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="abc05-1337">sicherheitscode</span></span>
- <span data-ttu-id="abc05-1338">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1338">sicherheitsnummer</span></span>
- <span data-ttu-id="abc05-1339">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1339">verfalldatum</span></span>
- <span data-ttu-id="abc05-1340">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="abc05-1340">codice di verifica</span></span>
- <span data-ttu-id="abc05-1341">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1341">cod.</span></span> <span data-ttu-id="abc05-1342">sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1342">sicurezza</span></span>
- <span data-ttu-id="abc05-1343">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1343">cod sicurezza</span></span>
- <span data-ttu-id="abc05-1344">n autorizzazione</span><span class="sxs-lookup"><span data-stu-id="abc05-1344">n autorizzazione</span></span>
- <span data-ttu-id="abc05-1345">código</span><span class="sxs-lookup"><span data-stu-id="abc05-1345">código</span></span>
- <span data-ttu-id="abc05-1346">codigo</span><span class="sxs-lookup"><span data-stu-id="abc05-1346">codigo</span></span>
- <span data-ttu-id="abc05-1347">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1347">cod.</span></span> <span data-ttu-id="abc05-1348">seg</span><span class="sxs-lookup"><span data-stu-id="abc05-1348">seg</span></span>
- <span data-ttu-id="abc05-1349">cod seg</span><span class="sxs-lookup"><span data-stu-id="abc05-1349">cod seg</span></span>
- <span data-ttu-id="abc05-1350">código de segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1350">código de segurança</span></span>
- <span data-ttu-id="abc05-1351">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1351">codigo de seguranca</span></span>
- <span data-ttu-id="abc05-1352">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1352">codigo de segurança</span></span>
- <span data-ttu-id="abc05-1353">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1353">código de seguranca</span></span>
- <span data-ttu-id="abc05-1354">cód.</span><span class="sxs-lookup"><span data-stu-id="abc05-1354">cód.</span></span> <span data-ttu-id="abc05-1355">segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1355">segurança</span></span>
- <span data-ttu-id="abc05-1356">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1356">cod.</span></span> <span data-ttu-id="abc05-1357">seguranca cod</span><span class="sxs-lookup"><span data-stu-id="abc05-1357">seguranca cod.</span></span> <span data-ttu-id="abc05-1358">segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1358">segurança</span></span>
- <span data-ttu-id="abc05-1359">cód.</span><span class="sxs-lookup"><span data-stu-id="abc05-1359">cód.</span></span> <span data-ttu-id="abc05-1360">seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1360">seguranca</span></span>
- <span data-ttu-id="abc05-1361">cód segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1361">cód segurança</span></span>
- <span data-ttu-id="abc05-1362">cod seguranca cod segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1362">cod seguranca cod segurança</span></span>
- <span data-ttu-id="abc05-1363">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1363">cód seguranca</span></span>
- <span data-ttu-id="abc05-1364">número de verificação</span><span class="sxs-lookup"><span data-stu-id="abc05-1364">número de verificação</span></span>
- <span data-ttu-id="abc05-1365">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="abc05-1365">numero de verificacao</span></span>
- <span data-ttu-id="abc05-1366">ablauf</span><span class="sxs-lookup"><span data-stu-id="abc05-1366">ablauf</span></span>
- <span data-ttu-id="abc05-1367">gültig bis</span><span class="sxs-lookup"><span data-stu-id="abc05-1367">gültig bis</span></span>
- <span data-ttu-id="abc05-1368">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1368">gültigkeitsdatum</span></span>
- <span data-ttu-id="abc05-1369">gultig bis</span><span class="sxs-lookup"><span data-stu-id="abc05-1369">gultig bis</span></span>
- <span data-ttu-id="abc05-1370">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1370">gultigkeitsdatum</span></span>
- <span data-ttu-id="abc05-1371">scadenza</span><span class="sxs-lookup"><span data-stu-id="abc05-1371">scadenza</span></span>
- <span data-ttu-id="abc05-1372">data scad</span><span class="sxs-lookup"><span data-stu-id="abc05-1372">data scad</span></span>
- <span data-ttu-id="abc05-1373">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="abc05-1373">fecha de expiracion</span></span>
- <span data-ttu-id="abc05-1374">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="abc05-1374">fecha de venc</span></span>
- <span data-ttu-id="abc05-1375">vencimiento</span><span class="sxs-lookup"><span data-stu-id="abc05-1375">vencimiento</span></span>
- <span data-ttu-id="abc05-1376">válido hasta</span><span class="sxs-lookup"><span data-stu-id="abc05-1376">válido hasta</span></span>
- <span data-ttu-id="abc05-1377">valido hasta</span><span class="sxs-lookup"><span data-stu-id="abc05-1377">valido hasta</span></span>
- <span data-ttu-id="abc05-1378">vto</span><span class="sxs-lookup"><span data-stu-id="abc05-1378">vto</span></span>
- <span data-ttu-id="abc05-1379">data de expiração</span><span class="sxs-lookup"><span data-stu-id="abc05-1379">data de expiração</span></span>
- <span data-ttu-id="abc05-1380">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="abc05-1380">data de expiracao</span></span>
- <span data-ttu-id="abc05-1381">data em que expira</span><span class="sxs-lookup"><span data-stu-id="abc05-1381">data em que expira</span></span>
- <span data-ttu-id="abc05-1382">유효한 ade</span><span class="sxs-lookup"><span data-stu-id="abc05-1382">validade</span></span>
- <span data-ttu-id="abc05-1383">valor</span><span class="sxs-lookup"><span data-stu-id="abc05-1383">valor</span></span>
- <span data-ttu-id="abc05-1384">vencimento</span><span class="sxs-lookup"><span data-stu-id="abc05-1384">vencimento</span></span>
- <span data-ttu-id="abc05-1385">Venc</span><span class="sxs-lookup"><span data-stu-id="abc05-1385">Venc</span></span> 

#### <a name="keyword_cc_name"></a><span data-ttu-id="abc05-1386">Keyword_cc_name</span><span class="sxs-lookup"><span data-stu-id="abc05-1386">Keyword_cc_name</span></span>

- <span data-ttu-id="abc05-1387">amex</span><span class="sxs-lookup"><span data-stu-id="abc05-1387">amex</span></span>
- <span data-ttu-id="abc05-1388">american express</span><span class="sxs-lookup"><span data-stu-id="abc05-1388">american express</span></span>
- <span data-ttu-id="abc05-1389">americanexpress</span><span class="sxs-lookup"><span data-stu-id="abc05-1389">americanexpress</span></span>
- <span data-ttu-id="abc05-1390">Visa</span><span class="sxs-lookup"><span data-stu-id="abc05-1390">Visa</span></span>
- <span data-ttu-id="abc05-1391">mastercard</span><span class="sxs-lookup"><span data-stu-id="abc05-1391">mastercard</span></span>
- <span data-ttu-id="abc05-1392">master card</span><span class="sxs-lookup"><span data-stu-id="abc05-1392">master card</span></span>
- <span data-ttu-id="abc05-1393">mc</span><span class="sxs-lookup"><span data-stu-id="abc05-1393">mc</span></span> 
- <span data-ttu-id="abc05-1394">mastercards</span><span class="sxs-lookup"><span data-stu-id="abc05-1394">mastercards</span></span>
- <span data-ttu-id="abc05-1395">master cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1395">master cards</span></span>
- <span data-ttu-id="abc05-1396">diner's Club</span><span class="sxs-lookup"><span data-stu-id="abc05-1396">diner's Club</span></span>
- <span data-ttu-id="abc05-1397">diners club</span><span class="sxs-lookup"><span data-stu-id="abc05-1397">diners club</span></span>
- <span data-ttu-id="abc05-1398">dinersclub</span><span class="sxs-lookup"><span data-stu-id="abc05-1398">dinersclub</span></span>
- <span data-ttu-id="abc05-1399">discover card</span><span class="sxs-lookup"><span data-stu-id="abc05-1399">discover card</span></span>
- <span data-ttu-id="abc05-1400">discovercard</span><span class="sxs-lookup"><span data-stu-id="abc05-1400">discovercard</span></span>
- <span data-ttu-id="abc05-1401">discover cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1401">discover cards</span></span>
- <span data-ttu-id="abc05-1402">JCB</span><span class="sxs-lookup"><span data-stu-id="abc05-1402">JCB</span></span>
- <span data-ttu-id="abc05-1403">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="abc05-1403">japanese card bureau</span></span>
- <span data-ttu-id="abc05-1404">carte blanche</span><span class="sxs-lookup"><span data-stu-id="abc05-1404">carte blanche</span></span>
- <span data-ttu-id="abc05-1405">carteblanche</span><span class="sxs-lookup"><span data-stu-id="abc05-1405">carteblanche</span></span>
- <span data-ttu-id="abc05-1406">credit card</span><span class="sxs-lookup"><span data-stu-id="abc05-1406">credit card</span></span>
- <span data-ttu-id="abc05-1407">참조란 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1407">cc#</span></span>
- <span data-ttu-id="abc05-1408">참조 #:</span><span class="sxs-lookup"><span data-stu-id="abc05-1408">cc#:</span></span>
- <span data-ttu-id="abc05-1409">expiration date</span><span class="sxs-lookup"><span data-stu-id="abc05-1409">expiration date</span></span>
- <span data-ttu-id="abc05-1410">exp date</span><span class="sxs-lookup"><span data-stu-id="abc05-1410">exp date</span></span>
- <span data-ttu-id="abc05-1411">expiry date</span><span class="sxs-lookup"><span data-stu-id="abc05-1411">expiry date</span></span>
- <span data-ttu-id="abc05-1412">date d’expiration</span><span class="sxs-lookup"><span data-stu-id="abc05-1412">date d’expiration</span></span>
- <span data-ttu-id="abc05-1413">date d'exp</span><span class="sxs-lookup"><span data-stu-id="abc05-1413">date d'exp</span></span>
- <span data-ttu-id="abc05-1414">date expiration</span><span class="sxs-lookup"><span data-stu-id="abc05-1414">date expiration</span></span>
- <span data-ttu-id="abc05-1415">bank card</span><span class="sxs-lookup"><span data-stu-id="abc05-1415">bank card</span></span>
- <span data-ttu-id="abc05-1416">bankcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1416">bankcard</span></span>
- <span data-ttu-id="abc05-1417">card number</span><span class="sxs-lookup"><span data-stu-id="abc05-1417">card number</span></span>
- <span data-ttu-id="abc05-1418">card num</span><span class="sxs-lookup"><span data-stu-id="abc05-1418">card num</span></span>
- <span data-ttu-id="abc05-1419">전화 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1419">cardnumber</span></span>
- <span data-ttu-id="abc05-1420">시 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1420">cardnumbers</span></span>
- <span data-ttu-id="abc05-1421">card numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-1421">card numbers</span></span>
- <span data-ttu-id="abc05-1422">카드</span><span class="sxs-lookup"><span data-stu-id="abc05-1422">creditcard</span></span>
- <span data-ttu-id="abc05-1423">credit cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1423">credit cards</span></span>
- <span data-ttu-id="abc05-1424">creditcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1424">creditcards</span></span>
- <span data-ttu-id="abc05-1425">ccn</span><span class="sxs-lookup"><span data-stu-id="abc05-1425">ccn</span></span>
- <span data-ttu-id="abc05-1426">card holder</span><span class="sxs-lookup"><span data-stu-id="abc05-1426">card holder</span></span>
- <span data-ttu-id="abc05-1427">소유자</span><span class="sxs-lookup"><span data-stu-id="abc05-1427">cardholder</span></span>
- <span data-ttu-id="abc05-1428">card holders</span><span class="sxs-lookup"><span data-stu-id="abc05-1428">card holders</span></span>
- <span data-ttu-id="abc05-1429">에이 홀더</span><span class="sxs-lookup"><span data-stu-id="abc05-1429">cardholders</span></span>
- <span data-ttu-id="abc05-1430">check card</span><span class="sxs-lookup"><span data-stu-id="abc05-1430">check card</span></span>
- <span data-ttu-id="abc05-1431">checkcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1431">checkcard</span></span>
- <span data-ttu-id="abc05-1432">check cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1432">check cards</span></span>
- <span data-ttu-id="abc05-1433">checkcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1433">checkcards</span></span>
- <span data-ttu-id="abc05-1434">debit card</span><span class="sxs-lookup"><span data-stu-id="abc05-1434">debit card</span></span>
- <span data-ttu-id="abc05-1435">debitcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1435">debitcard</span></span>
- <span data-ttu-id="abc05-1436">debit cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1436">debit cards</span></span>
- <span data-ttu-id="abc05-1437">debitcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1437">debitcards</span></span>
- <span data-ttu-id="abc05-1438">atm card</span><span class="sxs-lookup"><span data-stu-id="abc05-1438">atm card</span></span>
- <span data-ttu-id="abc05-1439">atmcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1439">atmcard</span></span>
- <span data-ttu-id="abc05-1440">atm cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1440">atm cards</span></span>
- <span data-ttu-id="abc05-1441">atmcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1441">atmcards</span></span>
- <span data-ttu-id="abc05-1442">enroute</span><span class="sxs-lookup"><span data-stu-id="abc05-1442">enroute</span></span>
- <span data-ttu-id="abc05-1443">en route</span><span class="sxs-lookup"><span data-stu-id="abc05-1443">en route</span></span>
- <span data-ttu-id="abc05-1444">card type</span><span class="sxs-lookup"><span data-stu-id="abc05-1444">card type</span></span>
- <span data-ttu-id="abc05-1445">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="abc05-1445">carte bancaire</span></span>
- <span data-ttu-id="abc05-1446">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="abc05-1446">carte de crédit</span></span>
- <span data-ttu-id="abc05-1447">carte de credit</span><span class="sxs-lookup"><span data-stu-id="abc05-1447">carte de credit</span></span>
- <span data-ttu-id="abc05-1448">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1448">numéro de carte</span></span>
- <span data-ttu-id="abc05-1449">numero de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1449">numero de carte</span></span>
- <span data-ttu-id="abc05-1450">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1450">nº de la carte</span></span>
- <span data-ttu-id="abc05-1451">nº de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1451">nº de carte</span></span>
- <span data-ttu-id="abc05-1452">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="abc05-1452">kreditkarte</span></span>
- <span data-ttu-id="abc05-1453">karte</span><span class="sxs-lookup"><span data-stu-id="abc05-1453">karte</span></span>
- <span data-ttu-id="abc05-1454">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="abc05-1454">karteninhaber</span></span>
- <span data-ttu-id="abc05-1455">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="abc05-1455">karteninhabers</span></span>
- <span data-ttu-id="abc05-1456">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="abc05-1456">kreditkarteninhaber</span></span>
- <span data-ttu-id="abc05-1457">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="abc05-1457">kreditkarteninstitut</span></span>
- <span data-ttu-id="abc05-1458">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="abc05-1458">kreditkartentyp</span></span>
- <span data-ttu-id="abc05-1459">eigentümername</span><span class="sxs-lookup"><span data-stu-id="abc05-1459">eigentümername</span></span>
- <span data-ttu-id="abc05-1460">kartennr</span><span class="sxs-lookup"><span data-stu-id="abc05-1460">kartennr</span></span> 
- <span data-ttu-id="abc05-1461">kartennummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1461">kartennummer</span></span>
- <span data-ttu-id="abc05-1462">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1462">kreditkartennummer</span></span>
- <span data-ttu-id="abc05-1463">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1463">kreditkarten-nummer</span></span>
- <span data-ttu-id="abc05-1464">carta di credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1464">carta di credito</span></span>
- <span data-ttu-id="abc05-1465">carta credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1465">carta credito</span></span>
- <span data-ttu-id="abc05-1466">카 ta</span><span class="sxs-lookup"><span data-stu-id="abc05-1466">carta</span></span>
- <span data-ttu-id="abc05-1467">n carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1467">n carta</span></span>
- <span data-ttu-id="abc05-1468">veiligheid.</span><span class="sxs-lookup"><span data-stu-id="abc05-1468">nr.</span></span> <span data-ttu-id="abc05-1469">카 ta</span><span class="sxs-lookup"><span data-stu-id="abc05-1469">carta</span></span>
- <span data-ttu-id="abc05-1470">nr carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1470">nr carta</span></span>
- <span data-ttu-id="abc05-1471">numero carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1471">numero carta</span></span>
- <span data-ttu-id="abc05-1472">numero della carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1472">numero della carta</span></span>
- <span data-ttu-id="abc05-1473">numero di carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1473">numero di carta</span></span>
- <span data-ttu-id="abc05-1474">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1474">tarjeta credito</span></span>
- <span data-ttu-id="abc05-1475">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1475">tarjeta de credito</span></span>
- <span data-ttu-id="abc05-1476">tarjeta crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1476">tarjeta crédito</span></span>
- <span data-ttu-id="abc05-1477">tarjeta de crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1477">tarjeta de crédito</span></span>
- <span data-ttu-id="abc05-1478">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="abc05-1478">tarjeta de atm</span></span>
- <span data-ttu-id="abc05-1479">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="abc05-1479">tarjeta atm</span></span>
- <span data-ttu-id="abc05-1480">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1480">tarjeta debito</span></span>
- <span data-ttu-id="abc05-1481">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1481">tarjeta de debito</span></span>
- <span data-ttu-id="abc05-1482">tarjeta débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1482">tarjeta débito</span></span>
- <span data-ttu-id="abc05-1483">tarjeta de débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1483">tarjeta de débito</span></span>
- <span data-ttu-id="abc05-1484">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1484">nº de tarjeta</span></span>
- <span data-ttu-id="abc05-1485">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1485">no.</span></span> <span data-ttu-id="abc05-1486">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1486">de tarjeta</span></span>
- <span data-ttu-id="abc05-1487">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1487">no de tarjeta</span></span>
- <span data-ttu-id="abc05-1488">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1488">numero de tarjeta</span></span>
- <span data-ttu-id="abc05-1489">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1489">número de tarjeta</span></span>
- <span data-ttu-id="abc05-1490">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="abc05-1490">tarjeta no</span></span>
- <span data-ttu-id="abc05-1491">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="abc05-1491">tarjetahabiente</span></span>
- <span data-ttu-id="abc05-1492">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1492">cartão de crédito</span></span>
- <span data-ttu-id="abc05-1493">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1493">cartão de credito</span></span>
- <span data-ttu-id="abc05-1494">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1494">cartao de crédito</span></span>
- <span data-ttu-id="abc05-1495">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1495">cartao de credito</span></span>
- <span data-ttu-id="abc05-1496">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1496">cartão de débito</span></span>
- <span data-ttu-id="abc05-1497">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1497">cartao de débito</span></span>
- <span data-ttu-id="abc05-1498">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1498">cartão de debito</span></span>
- <span data-ttu-id="abc05-1499">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1499">cartao de debito</span></span>
- <span data-ttu-id="abc05-1500">débito automático</span><span class="sxs-lookup"><span data-stu-id="abc05-1500">débito automático</span></span>
- <span data-ttu-id="abc05-1501">debito automatico</span><span class="sxs-lookup"><span data-stu-id="abc05-1501">debito automatico</span></span>
- <span data-ttu-id="abc05-1502">número do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1502">número do cartão</span></span>
- <span data-ttu-id="abc05-1503">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1503">numero do cartão</span></span> 
- <span data-ttu-id="abc05-1504">número do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1504">número do cartao</span></span>
- <span data-ttu-id="abc05-1505">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1505">numero do cartao</span></span>
- <span data-ttu-id="abc05-1506">número de cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1506">número de cartão</span></span>
- <span data-ttu-id="abc05-1507">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1507">numero de cartão</span></span>
- <span data-ttu-id="abc05-1508">número de cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1508">número de cartao</span></span>
- <span data-ttu-id="abc05-1509">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1509">numero de cartao</span></span>
- <span data-ttu-id="abc05-1510">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1510">nº do cartão</span></span>
- <span data-ttu-id="abc05-1511">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1511">nº do cartao</span></span>
- <span data-ttu-id="abc05-1512">n º</span><span class="sxs-lookup"><span data-stu-id="abc05-1512">nº.</span></span> <span data-ttu-id="abc05-1513">do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1513">do cartão</span></span>
- <span data-ttu-id="abc05-1514">no do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1514">no do cartão</span></span>
- <span data-ttu-id="abc05-1515">no do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1515">no do cartao</span></span>
- <span data-ttu-id="abc05-1516">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1516">no.</span></span> <span data-ttu-id="abc05-1517">do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1517">do cartão</span></span>
- <span data-ttu-id="abc05-1518">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1518">no.</span></span> <span data-ttu-id="abc05-1519">do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1519">do cartao</span></span> 
   
## <a name="croatia-identity-card-number"></a><span data-ttu-id="abc05-1520">크로아티아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1520">Croatia Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1521">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1521">Format</span></span>

<span data-ttu-id="abc05-1522">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1522">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1523">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1523">Pattern</span></span>

<span data-ttu-id="abc05-1524">9자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1524">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1525">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1525">Checksum</span></span>

<span data-ttu-id="abc05-1526">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-1526">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1527">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1527">Definition</span></span>

<span data-ttu-id="abc05-1528">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1528">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1529">Func_croatia_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1529">The function Func_croatia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1530">Keyword_croatia_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1530">A keyword from Keyword_croatia_id_card is found.</span></span>

```xml
<!--Croatia Identity Card Number-->
<Entity id="ff12f884-c20a-4189-b185-34c8e7258d47" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_id_card"/>
     <Match idRef="Keyword_croatia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1531">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1531">Keywords</span></span>

#### <a name="keyword_croatia_id_card"></a><span data-ttu-id="abc05-1532">Keyword_croatia_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-1532">Keyword_croatia_id_card</span></span>

- <span data-ttu-id="abc05-1533">Croatian identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-1533">Croatian identity card</span></span>
- <span data-ttu-id="abc05-1534">Osobna iskaznica</span><span class="sxs-lookup"><span data-stu-id="abc05-1534">Osobna iskaznica</span></span>

   
## <a name="croatia-personal-identification-oib-number"></a><span data-ttu-id="abc05-1535">크로아티아 개인 식별(OIB) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1535">Croatia Personal Identification (OIB) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1536">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1536">Format</span></span>

<span data-ttu-id="abc05-1537">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1537">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1538">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1538">Pattern</span></span>

<span data-ttu-id="abc05-1539">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-1539">11 digits:</span></span>
- <span data-ttu-id="abc05-1540">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1540">10 digits</span></span> 
- <span data-ttu-id="abc05-1541">최종 자릿수는 국제 데이터 교환 목적을 위한 검사 숫자 이며, HR는 11 자리 숫자 앞에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1541">Final digit is a check digit For the purposes of international data exchange, the letters HR are added preceding the eleven digits.</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1542">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1542">Checksum</span></span>

<span data-ttu-id="abc05-1543">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1543">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1544">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1544">Definition</span></span>

<span data-ttu-id="abc05-1545">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1545">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1546">Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1546">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1547">Keyword_croatia_oib_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1547">A keyword from Keyword_croatia_oib_number is found.</span></span>
- <span data-ttu-id="abc05-1548">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1548">The checksum passes.</span></span>

<span data-ttu-id="abc05-1549">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1549">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1550">Func_croatia_oib_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1550">The function Func_croatia_oib_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1551">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1551">The checksum passes.</span></span>

```xml
<!-- Croatia Personal Identification (OIB) Number -->
<Entity id="31983b6d-db95-4eb2-a630-b44bd091968d" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_croatia_oib_number"/>
     <Match idRef="Keyword_croatia_oib_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_croatia_oib_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1552">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1552">Keywords</span></span>

#### <a name="keyword_croatia_oib_number"></a><span data-ttu-id="abc05-1553">Keyword_croatia_oib_number</span><span class="sxs-lookup"><span data-stu-id="abc05-1553">Keyword_croatia_oib_number</span></span>

- <span data-ttu-id="abc05-1554">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="abc05-1554">Personal Identification Number</span></span>
- <span data-ttu-id="abc05-1555">Osobni identifikacijski broj</span><span class="sxs-lookup"><span data-stu-id="abc05-1555">Osobni identifikacijski broj</span></span> 
- <span data-ttu-id="abc05-1556">OIB</span><span class="sxs-lookup"><span data-stu-id="abc05-1556">OIB</span></span> 

   
## <a name="czech-personal-identity-number"></a><span data-ttu-id="abc05-1557">체코어 개인 Id 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1557">Czech Personal Identity Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1558">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1558">Format</span></span>

<span data-ttu-id="abc05-1559">선택적 슬래시 (이전 형식)가 있는 9 자리 숫자와 슬래시 (새 형식)가 있는 10 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1559">Nine digits with optional forward slash (old format) 10 digits with optional forward slash (new format)</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1560">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1560">Pattern</span></span>

<span data-ttu-id="abc05-1561">9 자리 숫자 (이전 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-1561">Nine digits (old format):</span></span>
- <span data-ttu-id="abc05-1562">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1562">Nine digits</span></span>

<span data-ttu-id="abc05-1563">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-1563">OR</span></span>

- <span data-ttu-id="abc05-1564">출생 날짜를 나타내는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1564">Six digits that represent date of birth</span></span>
- <span data-ttu-id="abc05-1565">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="abc05-1565">A forward slash</span></span>
- <span data-ttu-id="abc05-1566">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1566">Three digits</span></span>

<span data-ttu-id="abc05-1567">10 자리 숫자 (새 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-1567">10 digits (new format):</span></span>
- <span data-ttu-id="abc05-1568">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1568">10 digits</span></span>

<span data-ttu-id="abc05-1569">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-1569">OR</span></span>

- <span data-ttu-id="abc05-1570">출생 날짜를 나타내는 6 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1570">Six digits that represent date of birth</span></span>
- <span data-ttu-id="abc05-1571">정방향 슬래시</span><span class="sxs-lookup"><span data-stu-id="abc05-1571">A forward slash</span></span> 
- <span data-ttu-id="abc05-1572">마지막 숫자가 검사 숫자인 4 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1572">Four digits where last digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1573">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1573">Checksum</span></span>

<span data-ttu-id="abc05-1574">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1574">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1575">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1575">Definition</span></span>

<span data-ttu-id="abc05-1576">DLP 정책은 300 Func_czech_id_card 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 85% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1576">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_czech_id_card finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-1577">Keyword_czech_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1577">A keyword from Keyword_czech_id_card is found.</span></span>
<span data-ttu-id="abc05-1578">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1578">The checksum passes.</span></span>

```xml
<!-- Czech Personal Identity Number -->
<Entity id="60c0725a-4eb6-455b-9dda-05d8a7396497"      patternsProximity="300" recommendedConfidence="85">
   <Pattern confidenceLevel="85">
      <IdMatch idRef="Func_czech_id_card" />
      <Match idRef="Keyword_czech_id_card" />
   </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="abc05-1579">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1579">Keywords</span></span>

- <span data-ttu-id="abc05-1580">체코어 개인 id 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1580">czech personal identity number</span></span>
- <span data-ttu-id="abc05-1581">Rodné číslo</span><span class="sxs-lookup"><span data-stu-id="abc05-1581">Rodné číslo</span></span>
   
## <a name="denmark-personal-identification-number"></a><span data-ttu-id="abc05-1582">덴마크 개인 식별 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1582">Denmark Personal Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1583">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1583">Format</span></span>

<span data-ttu-id="abc05-1584">하이픈을 포함하는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1584">10 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1585">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1585">Pattern</span></span>

<span data-ttu-id="abc05-1586">10자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-1586">10 digits:</span></span>
- <span data-ttu-id="abc05-1587">생년월일에 해당하는 DDMMYY 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-1587">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="abc05-1588">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-1588">A hyphen</span></span> 
- <span data-ttu-id="abc05-1589">마지막 숫자가 검사 숫자인 4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1589">Four digits where the final digit is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1590">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1590">Checksum</span></span>

<span data-ttu-id="abc05-1591">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1591">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1592">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1592">Definition</span></span>

<span data-ttu-id="abc05-1593">DLP 정책은 300 Regex_denmark_id 문자 근사에서 해당 패턴과 일치 하는 콘텐츠를 찾는 경우이 유형의 중요 한 정보를 검색 한다는 것을 75% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1593">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_denmark_id finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-1594">Keyword_denmark_id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1594">A keyword from Keyword_denmark_id is found.</span></span>
<span data-ttu-id="abc05-1595">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1595">The checksum passes.</span></span>

```xml
<!-- Denmark Personal Identification Number -->
<Entity id="6c4f2fef-56e1-4c00-8093-88d7a01cf460" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_denmark_id"/>
     <Match idRef="Keyword_denmark_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1596">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1596">Keywords</span></span>

#### <a name="keyword_denmark_id"></a><span data-ttu-id="abc05-1597">Keyword_denmark_id</span><span class="sxs-lookup"><span data-stu-id="abc05-1597">Keyword_denmark_id</span></span>

- <span data-ttu-id="abc05-1598">Personal Identification Number</span><span class="sxs-lookup"><span data-stu-id="abc05-1598">Personal Identification Number</span></span>
- <span data-ttu-id="abc05-1599">CPR</span><span class="sxs-lookup"><span data-stu-id="abc05-1599">CPR</span></span>
- <span data-ttu-id="abc05-1600">Det Centrale Personregister</span><span class="sxs-lookup"><span data-stu-id="abc05-1600">Det Centrale Personregister</span></span>
- <span data-ttu-id="abc05-1601">Personnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1601">Personnummer</span></span>
   
## <a name="drug-enforcement-agency-dea-number"></a><span data-ttu-id="abc05-1602">DEA(약물 집행 기구) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1602">Drug Enforcement Agency (DEA) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1603">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1603">Format</span></span>

<span data-ttu-id="abc05-1604">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1604">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1605">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1605">Pattern</span></span>

<span data-ttu-id="abc05-1606">패턴에는 다음이 모두 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1606">Pattern must include all of the following:</span></span>
- <span data-ttu-id="abc05-1607">등록 코드에 해당하는 abcdefghjklmnprstux 중 한 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-1607">One letter (not case sensitive) from this set of possible letters: abcdefghjklmnprstux, which is a registrant code</span></span> 
- <span data-ttu-id="abc05-1608">등록자 성의 첫 문자에 해당하는 한 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-1608">One letter (not case sensitive), which is the first letter of the registrant's last name</span></span> 
- <span data-ttu-id="abc05-1609">검사 숫자의 마지막 7개 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1609">Seven digits, the last of which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1610">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1610">Checksum</span></span>

<span data-ttu-id="abc05-1611">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1611">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1612">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1612">Definition</span></span>

<span data-ttu-id="abc05-1613">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1613">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1614">Func_dea_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1614">The function Func_dea_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1615">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1615">The checksum passes.</span></span>

```xml
<!-- DEA Number -->
<Entity id="9a5445ad-406e-43eb-8bd7-cac17ab6d0e4" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_dea_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1616">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1616">Keywords</span></span>

<span data-ttu-id="abc05-1617">없음</span><span class="sxs-lookup"><span data-stu-id="abc05-1617">None</span></span>

   
## <a name="eu-debit-card-number"></a><span data-ttu-id="abc05-1618">유럽 직불 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1618">EU Debit Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1619">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1619">Format</span></span>

<span data-ttu-id="abc05-1620">16자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1620">16 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1621">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1621">Pattern</span></span>

<span data-ttu-id="abc05-1622">매우 복잡하고 강력한 패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1622">Very complex and robust pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1623">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1623">Checksum</span></span>

<span data-ttu-id="abc05-1624">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1624">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1625">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1625">Definition</span></span>

<span data-ttu-id="abc05-1626">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1626">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1627">Func_eu_debit_card 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1627">The function Func_eu_debit_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1628">다음 중 하나 이상이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1628">At least one of the following is true:</span></span>
    - <span data-ttu-id="abc05-1629">Keyword_eu_debit_card의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1629">A keyword from Keyword_eu_debit_card is found.</span></span>
    - <span data-ttu-id="abc05-1630">Keyword_card_terms_dict의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1630">A keyword from Keyword_card_terms_dict is found.</span></span>
    - <span data-ttu-id="abc05-1631">Keyword_card_security_terms_dict의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1631">A keyword from Keyword_card_security_terms_dict is found.</span></span>
    - <span data-ttu-id="abc05-1632">Keyword_card_expiration_terms_dict의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1632">A keyword from Keyword_card_expiration_terms_dict is found.</span></span>
    - <span data-ttu-id="abc05-1633">Func_expiration_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1633">The function Func_expiration_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-1634">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1634">The checksum passes.</span></span>

```xml
    <!-- EU Debit Card Number -->
    <Entity id="0e9b3178-9678-47dd-a509-37222ca96b42" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_eu_debit_card" />
        <Any minMatches="1">
          <Match idRef="Keyword_eu_debit_card" />
          <Match idRef="Keyword_card_terms_dict" />
          <Match idRef="Keyword_card_security_terms_dict" />
          <Match idRef="Keyword_card_expiration_terms_dict" />
          <Match idRef="Func_expiration_date" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1635">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1635">Keywords</span></span>

#### <a name="keyword_eu_debit_card"></a><span data-ttu-id="abc05-1636">Keyword_eu_debit_card</span><span class="sxs-lookup"><span data-stu-id="abc05-1636">Keyword_eu_debit_card</span></span>

- <span data-ttu-id="abc05-1637">account number</span><span class="sxs-lookup"><span data-stu-id="abc05-1637">account number</span></span> 
- <span data-ttu-id="abc05-1638">card number</span><span class="sxs-lookup"><span data-stu-id="abc05-1638">card number</span></span> 
- <span data-ttu-id="abc05-1639">card no.</span><span class="sxs-lookup"><span data-stu-id="abc05-1639">card no.</span></span> 
- <span data-ttu-id="abc05-1640">security number</span><span class="sxs-lookup"><span data-stu-id="abc05-1640">security number</span></span> 
- <span data-ttu-id="abc05-1641">참조란 #</span><span class="sxs-lookup"><span data-stu-id="abc05-1641">cc#</span></span> 

#### <a name="keyword_card_terms_dict"></a><span data-ttu-id="abc05-1642">Keyword_card_terms_dict</span><span class="sxs-lookup"><span data-stu-id="abc05-1642">Keyword_card_terms_dict</span></span>

- <span data-ttu-id="abc05-1643">acct nbr</span><span class="sxs-lookup"><span data-stu-id="abc05-1643">acct nbr</span></span> 
- <span data-ttu-id="abc05-1644">acct num</span><span class="sxs-lookup"><span data-stu-id="abc05-1644">acct num</span></span> 
- <span data-ttu-id="abc05-1645">acct no</span><span class="sxs-lookup"><span data-stu-id="abc05-1645">acct no</span></span> 
- <span data-ttu-id="abc05-1646">american express</span><span class="sxs-lookup"><span data-stu-id="abc05-1646">american express</span></span> 
- <span data-ttu-id="abc05-1647">americanexpress</span><span class="sxs-lookup"><span data-stu-id="abc05-1647">americanexpress</span></span> 
- <span data-ttu-id="abc05-1648">americano espresso</span><span class="sxs-lookup"><span data-stu-id="abc05-1648">americano espresso</span></span> 
- <span data-ttu-id="abc05-1649">amex</span><span class="sxs-lookup"><span data-stu-id="abc05-1649">amex</span></span> 
- <span data-ttu-id="abc05-1650">atm card</span><span class="sxs-lookup"><span data-stu-id="abc05-1650">atm card</span></span> 
- <span data-ttu-id="abc05-1651">atm cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1651">atm cards</span></span> 
- <span data-ttu-id="abc05-1652">atm kaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1652">atm kaart</span></span> 
- <span data-ttu-id="abc05-1653">atmcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1653">atmcard</span></span> 
- <span data-ttu-id="abc05-1654">atmcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1654">atmcards</span></span> 
- <span data-ttu-id="abc05-1655">atmkaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1655">atmkaart</span></span> 
- <span data-ttu-id="abc05-1656">atmkaarten</span><span class="sxs-lookup"><span data-stu-id="abc05-1656">atmkaarten</span></span> 
- <span data-ttu-id="abc05-1657">bancontact</span><span class="sxs-lookup"><span data-stu-id="abc05-1657">bancontact</span></span> 
- <span data-ttu-id="abc05-1658">bank card</span><span class="sxs-lookup"><span data-stu-id="abc05-1658">bank card</span></span> 
- <span data-ttu-id="abc05-1659">bankkaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1659">bankkaart</span></span> 
- <span data-ttu-id="abc05-1660">card holder</span><span class="sxs-lookup"><span data-stu-id="abc05-1660">card holder</span></span> 
- <span data-ttu-id="abc05-1661">card holders</span><span class="sxs-lookup"><span data-stu-id="abc05-1661">card holders</span></span> 
- <span data-ttu-id="abc05-1662">card num</span><span class="sxs-lookup"><span data-stu-id="abc05-1662">card num</span></span> 
- <span data-ttu-id="abc05-1663">card number</span><span class="sxs-lookup"><span data-stu-id="abc05-1663">card number</span></span> 
- <span data-ttu-id="abc05-1664">card numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-1664">card numbers</span></span> 
- <span data-ttu-id="abc05-1665">card type</span><span class="sxs-lookup"><span data-stu-id="abc05-1665">card type</span></span> 
- <span data-ttu-id="abc05-1666">cardano numerico</span><span class="sxs-lookup"><span data-stu-id="abc05-1666">cardano numerico</span></span> 
- <span data-ttu-id="abc05-1667">소유자</span><span class="sxs-lookup"><span data-stu-id="abc05-1667">cardholder</span></span> 
- <span data-ttu-id="abc05-1668">에이 홀더</span><span class="sxs-lookup"><span data-stu-id="abc05-1668">cardholders</span></span> 
- <span data-ttu-id="abc05-1669">전화 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1669">cardnumber</span></span> 
- <span data-ttu-id="abc05-1670">시 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1670">cardnumbers</span></span> 
- <span data-ttu-id="abc05-1671">carta bianca</span><span class="sxs-lookup"><span data-stu-id="abc05-1671">carta bianca</span></span> 
- <span data-ttu-id="abc05-1672">carta credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1672">carta credito</span></span> 
- <span data-ttu-id="abc05-1673">carta di credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1673">carta di credito</span></span> 
- <span data-ttu-id="abc05-1674">cartao de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1674">cartao de credito</span></span> 
- <span data-ttu-id="abc05-1675">cartao de crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1675">cartao de crédito</span></span> 
- <span data-ttu-id="abc05-1676">cartao de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1676">cartao de debito</span></span> 
- <span data-ttu-id="abc05-1677">cartao de débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1677">cartao de débito</span></span> 
- <span data-ttu-id="abc05-1678">carte bancaire</span><span class="sxs-lookup"><span data-stu-id="abc05-1678">carte bancaire</span></span> 
- <span data-ttu-id="abc05-1679">carte blanche</span><span class="sxs-lookup"><span data-stu-id="abc05-1679">carte blanche</span></span> 
- <span data-ttu-id="abc05-1680">carte bleue</span><span class="sxs-lookup"><span data-stu-id="abc05-1680">carte bleue</span></span> 
- <span data-ttu-id="abc05-1681">carte de credit</span><span class="sxs-lookup"><span data-stu-id="abc05-1681">carte de credit</span></span> 
- <span data-ttu-id="abc05-1682">carte de crédit</span><span class="sxs-lookup"><span data-stu-id="abc05-1682">carte de crédit</span></span> 
- <span data-ttu-id="abc05-1683">carte di credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1683">carte di credito</span></span> 
- <span data-ttu-id="abc05-1684">carteblanche</span><span class="sxs-lookup"><span data-stu-id="abc05-1684">carteblanche</span></span> 
- <span data-ttu-id="abc05-1685">cartão de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1685">cartão de credito</span></span> 
- <span data-ttu-id="abc05-1686">cartão de crédito</span><span class="sxs-lookup"><span data-stu-id="abc05-1686">cartão de crédito</span></span> 
- <span data-ttu-id="abc05-1687">cartão de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1687">cartão de debito</span></span> 
- <span data-ttu-id="abc05-1688">cartão de débito</span><span class="sxs-lookup"><span data-stu-id="abc05-1688">cartão de débito</span></span> 
- <span data-ttu-id="abc05-1689">cb</span><span class="sxs-lookup"><span data-stu-id="abc05-1689">cb</span></span> 
- <span data-ttu-id="abc05-1690">ccn</span><span class="sxs-lookup"><span data-stu-id="abc05-1690">ccn</span></span> 
- <span data-ttu-id="abc05-1691">check card</span><span class="sxs-lookup"><span data-stu-id="abc05-1691">check card</span></span> 
- <span data-ttu-id="abc05-1692">check cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1692">check cards</span></span> 
- <span data-ttu-id="abc05-1693">checkcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1693">checkcard</span></span>
- <span data-ttu-id="abc05-1694">checkcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1694">checkcards</span></span> 
- <span data-ttu-id="abc05-1695">chequekaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1695">chequekaart</span></span> 
- <span data-ttu-id="abc05-1696">cirrus</span><span class="sxs-lookup"><span data-stu-id="abc05-1696">cirrus</span></span> 
- <span data-ttu-id="abc05-1697">cirrus-edc-maestro</span><span class="sxs-lookup"><span data-stu-id="abc05-1697">cirrus-edc-maestro</span></span> 
- <span data-ttu-id="abc05-1698">controlekaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1698">controlekaart</span></span> 
- <span data-ttu-id="abc05-1699">controlekaarten</span><span class="sxs-lookup"><span data-stu-id="abc05-1699">controlekaarten</span></span> 
- <span data-ttu-id="abc05-1700">credit card</span><span class="sxs-lookup"><span data-stu-id="abc05-1700">credit card</span></span> 
- <span data-ttu-id="abc05-1701">credit cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1701">credit cards</span></span> 
- <span data-ttu-id="abc05-1702">카드</span><span class="sxs-lookup"><span data-stu-id="abc05-1702">creditcard</span></span> 
- <span data-ttu-id="abc05-1703">creditcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1703">creditcards</span></span> 
- <span data-ttu-id="abc05-1704">debetkaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1704">debetkaart</span></span> 
- <span data-ttu-id="abc05-1705">debetkaarten</span><span class="sxs-lookup"><span data-stu-id="abc05-1705">debetkaarten</span></span> 
- <span data-ttu-id="abc05-1706">debit card</span><span class="sxs-lookup"><span data-stu-id="abc05-1706">debit card</span></span> 
- <span data-ttu-id="abc05-1707">debit cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1707">debit cards</span></span> 
- <span data-ttu-id="abc05-1708">debitcard</span><span class="sxs-lookup"><span data-stu-id="abc05-1708">debitcard</span></span> 
- <span data-ttu-id="abc05-1709">debitcards</span><span class="sxs-lookup"><span data-stu-id="abc05-1709">debitcards</span></span> 
- <span data-ttu-id="abc05-1710">debito automatico</span><span class="sxs-lookup"><span data-stu-id="abc05-1710">debito automatico</span></span> 
- <span data-ttu-id="abc05-1711">diners club</span><span class="sxs-lookup"><span data-stu-id="abc05-1711">diners club</span></span> 
- <span data-ttu-id="abc05-1712">dinersclub</span><span class="sxs-lookup"><span data-stu-id="abc05-1712">dinersclub</span></span> 
- <span data-ttu-id="abc05-1713">찾아보십시오</span><span class="sxs-lookup"><span data-stu-id="abc05-1713">discover</span></span> 
- <span data-ttu-id="abc05-1714">discover card</span><span class="sxs-lookup"><span data-stu-id="abc05-1714">discover card</span></span> 
- <span data-ttu-id="abc05-1715">discover cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1715">discover cards</span></span> 
- <span data-ttu-id="abc05-1716">discovercard</span><span class="sxs-lookup"><span data-stu-id="abc05-1716">discovercard</span></span> 
- <span data-ttu-id="abc05-1717">discovercards</span><span class="sxs-lookup"><span data-stu-id="abc05-1717">discovercards</span></span> 
- <span data-ttu-id="abc05-1718">débito automático</span><span class="sxs-lookup"><span data-stu-id="abc05-1718">débito automático</span></span>
- <span data-ttu-id="abc05-1719">edc</span><span class="sxs-lookup"><span data-stu-id="abc05-1719">edc</span></span> 
- <span data-ttu-id="abc05-1720">eigentümername</span><span class="sxs-lookup"><span data-stu-id="abc05-1720">eigentümername</span></span> 
- <span data-ttu-id="abc05-1721">european debit card</span><span class="sxs-lookup"><span data-stu-id="abc05-1721">european debit card</span></span> 
- <span data-ttu-id="abc05-1722">hoofdkaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1722">hoofdkaart</span></span> 
- <span data-ttu-id="abc05-1723">hoofdkaarten</span><span class="sxs-lookup"><span data-stu-id="abc05-1723">hoofdkaarten</span></span> 
- <span data-ttu-id="abc05-1724">in viaggio</span><span class="sxs-lookup"><span data-stu-id="abc05-1724">in viaggio</span></span> 
- <span data-ttu-id="abc05-1725">japanese card bureau</span><span class="sxs-lookup"><span data-stu-id="abc05-1725">japanese card bureau</span></span> 
- <span data-ttu-id="abc05-1726">japanse kaartdienst</span><span class="sxs-lookup"><span data-stu-id="abc05-1726">japanse kaartdienst</span></span> 
- <span data-ttu-id="abc05-1727">jcb</span><span class="sxs-lookup"><span data-stu-id="abc05-1727">jcb</span></span> 
- <span data-ttu-id="abc05-1728">kaart</span><span class="sxs-lookup"><span data-stu-id="abc05-1728">kaart</span></span> 
- <span data-ttu-id="abc05-1729">kaart num</span><span class="sxs-lookup"><span data-stu-id="abc05-1729">kaart num</span></span> 
- <span data-ttu-id="abc05-1730">kaartaantal</span><span class="sxs-lookup"><span data-stu-id="abc05-1730">kaartaantal</span></span> 
- <span data-ttu-id="abc05-1731">kaartaantallen</span><span class="sxs-lookup"><span data-stu-id="abc05-1731">kaartaantallen</span></span> 
- <span data-ttu-id="abc05-1732">kaarthouder</span><span class="sxs-lookup"><span data-stu-id="abc05-1732">kaarthouder</span></span> 
- <span data-ttu-id="abc05-1733">kaarthouders</span><span class="sxs-lookup"><span data-stu-id="abc05-1733">kaarthouders</span></span> 
- <span data-ttu-id="abc05-1734">karte</span><span class="sxs-lookup"><span data-stu-id="abc05-1734">karte</span></span>  
- <span data-ttu-id="abc05-1735">karteninhaber</span><span class="sxs-lookup"><span data-stu-id="abc05-1735">karteninhaber</span></span> 
- <span data-ttu-id="abc05-1736">karteninhabers</span><span class="sxs-lookup"><span data-stu-id="abc05-1736">karteninhabers</span></span>
- <span data-ttu-id="abc05-1737">kartennr</span><span class="sxs-lookup"><span data-stu-id="abc05-1737">kartennr</span></span> 
- <span data-ttu-id="abc05-1738">kartennummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1738">kartennummer</span></span> 
- <span data-ttu-id="abc05-1739">kreditkarte</span><span class="sxs-lookup"><span data-stu-id="abc05-1739">kreditkarte</span></span> 
- <span data-ttu-id="abc05-1740">kreditkarten-nummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1740">kreditkarten-nummer</span></span> 
- <span data-ttu-id="abc05-1741">kreditkarteninhaber</span><span class="sxs-lookup"><span data-stu-id="abc05-1741">kreditkarteninhaber</span></span> 
- <span data-ttu-id="abc05-1742">kreditkarteninstitut</span><span class="sxs-lookup"><span data-stu-id="abc05-1742">kreditkarteninstitut</span></span> 
- <span data-ttu-id="abc05-1743">kreditkartennummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1743">kreditkartennummer</span></span> 
- <span data-ttu-id="abc05-1744">kreditkartentyp</span><span class="sxs-lookup"><span data-stu-id="abc05-1744">kreditkartentyp</span></span> 
- <span data-ttu-id="abc05-1745">maestro</span><span class="sxs-lookup"><span data-stu-id="abc05-1745">maestro</span></span> 
- <span data-ttu-id="abc05-1746">master card</span><span class="sxs-lookup"><span data-stu-id="abc05-1746">master card</span></span> 
- <span data-ttu-id="abc05-1747">master cards</span><span class="sxs-lookup"><span data-stu-id="abc05-1747">master cards</span></span> 
- <span data-ttu-id="abc05-1748">mastercard</span><span class="sxs-lookup"><span data-stu-id="abc05-1748">mastercard</span></span> 
- <span data-ttu-id="abc05-1749">mastercards</span><span class="sxs-lookup"><span data-stu-id="abc05-1749">mastercards</span></span> 
- <span data-ttu-id="abc05-1750">mc</span><span class="sxs-lookup"><span data-stu-id="abc05-1750">mc</span></span> 
- <span data-ttu-id="abc05-1751">mister cash</span><span class="sxs-lookup"><span data-stu-id="abc05-1751">mister cash</span></span> 
- <span data-ttu-id="abc05-1752">n carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1752">n carta</span></span> 
- <span data-ttu-id="abc05-1753">카 ta</span><span class="sxs-lookup"><span data-stu-id="abc05-1753">carta</span></span> 
- <span data-ttu-id="abc05-1754">no de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1754">no de tarjeta</span></span> 
- <span data-ttu-id="abc05-1755">no do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1755">no do cartao</span></span> 
- <span data-ttu-id="abc05-1756">no do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1756">no do cartão</span></span> 
- <span data-ttu-id="abc05-1757">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1757">no.</span></span> <span data-ttu-id="abc05-1758">de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1758">de tarjeta</span></span> 
- <span data-ttu-id="abc05-1759">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1759">no.</span></span> <span data-ttu-id="abc05-1760">do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1760">do cartao</span></span> 
- <span data-ttu-id="abc05-1761">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1761">no.</span></span> <span data-ttu-id="abc05-1762">do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1762">do cartão</span></span> 
- <span data-ttu-id="abc05-1763">nr carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1763">nr carta</span></span> 
- <span data-ttu-id="abc05-1764">veiligheid.</span><span class="sxs-lookup"><span data-stu-id="abc05-1764">nr.</span></span> <span data-ttu-id="abc05-1765">카 ta</span><span class="sxs-lookup"><span data-stu-id="abc05-1765">carta</span></span> 
- <span data-ttu-id="abc05-1766">numeri di scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1766">numeri di scheda</span></span> 
- <span data-ttu-id="abc05-1767">numero carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1767">numero carta</span></span> 
- <span data-ttu-id="abc05-1768">numero de cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1768">numero de cartao</span></span> 
- <span data-ttu-id="abc05-1769">numero de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1769">numero de carte</span></span> 
- <span data-ttu-id="abc05-1770">numero de cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1770">numero de cartão</span></span> 
- <span data-ttu-id="abc05-1771">numero de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1771">numero de tarjeta</span></span>
- <span data-ttu-id="abc05-1772">numero della carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1772">numero della carta</span></span> 
- <span data-ttu-id="abc05-1773">numero di carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1773">numero di carta</span></span> 
- <span data-ttu-id="abc05-1774">numero di scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1774">numero di scheda</span></span> 
- <span data-ttu-id="abc05-1775">numero do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1775">numero do cartao</span></span> 
- <span data-ttu-id="abc05-1776">numero do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1776">numero do cartão</span></span> 
- <span data-ttu-id="abc05-1777">numéro de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1777">numéro de carte</span></span> 
- <span data-ttu-id="abc05-1778">nº carta</span><span class="sxs-lookup"><span data-stu-id="abc05-1778">nº carta</span></span> 
- <span data-ttu-id="abc05-1779">nº de carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1779">nº de carte</span></span> 
- <span data-ttu-id="abc05-1780">nº de la carte</span><span class="sxs-lookup"><span data-stu-id="abc05-1780">nº de la carte</span></span> 
- <span data-ttu-id="abc05-1781">nº de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1781">nº de tarjeta</span></span> 
- <span data-ttu-id="abc05-1782">nº do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1782">nº do cartao</span></span> 
- <span data-ttu-id="abc05-1783">nº do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1783">nº do cartão</span></span> 
- <span data-ttu-id="abc05-1784">n º</span><span class="sxs-lookup"><span data-stu-id="abc05-1784">nº.</span></span> <span data-ttu-id="abc05-1785">do cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1785">do cartão</span></span> 
- <span data-ttu-id="abc05-1786">número de cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1786">número de cartao</span></span> 
- <span data-ttu-id="abc05-1787">número de cartão</span><span class="sxs-lookup"><span data-stu-id="abc05-1787">número de cartão</span></span> 
- <span data-ttu-id="abc05-1788">número de tarjeta</span><span class="sxs-lookup"><span data-stu-id="abc05-1788">número de tarjeta</span></span> 
- <span data-ttu-id="abc05-1789">número do cartao</span><span class="sxs-lookup"><span data-stu-id="abc05-1789">número do cartao</span></span> 
- <span data-ttu-id="abc05-1790">scheda dell'assegno</span><span class="sxs-lookup"><span data-stu-id="abc05-1790">scheda dell'assegno</span></span> 
- <span data-ttu-id="abc05-1791">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="abc05-1791">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="abc05-1792">scheda dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="abc05-1792">scheda dell'atmosfera</span></span> 
- <span data-ttu-id="abc05-1793">scheda della banca</span><span class="sxs-lookup"><span data-stu-id="abc05-1793">scheda della banca</span></span> 
- <span data-ttu-id="abc05-1794">scheda di controllo</span><span class="sxs-lookup"><span data-stu-id="abc05-1794">scheda di controllo</span></span> 
- <span data-ttu-id="abc05-1795">scheda di debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1795">scheda di debito</span></span> 
- <span data-ttu-id="abc05-1796">scheda matrice</span><span class="sxs-lookup"><span data-stu-id="abc05-1796">scheda matrice</span></span> 
- <span data-ttu-id="abc05-1797">schede dell'atmosfera</span><span class="sxs-lookup"><span data-stu-id="abc05-1797">schede dell'atmosfera</span></span> 
- <span data-ttu-id="abc05-1798">schede di controllo</span><span class="sxs-lookup"><span data-stu-id="abc05-1798">schede di controllo</span></span> 
- <span data-ttu-id="abc05-1799">schede di debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1799">schede di debito</span></span> 
- <span data-ttu-id="abc05-1800">schede matrici</span><span class="sxs-lookup"><span data-stu-id="abc05-1800">schede matrici</span></span> 
- <span data-ttu-id="abc05-1801">scoprono la scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1801">scoprono la scheda</span></span> 
- <span data-ttu-id="abc05-1802">scoprono le schede</span><span class="sxs-lookup"><span data-stu-id="abc05-1802">scoprono le schede</span></span> 
- <span data-ttu-id="abc05-1803">분리</span><span class="sxs-lookup"><span data-stu-id="abc05-1803">solo</span></span> 
- <span data-ttu-id="abc05-1804">supporti di scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1804">supporti di scheda</span></span> 
- <span data-ttu-id="abc05-1805">supporto di scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1805">supporto di scheda</span></span> 
- <span data-ttu-id="abc05-1806">스위치</span><span class="sxs-lookup"><span data-stu-id="abc05-1806">switch</span></span> 
- <span data-ttu-id="abc05-1807">tarjeta atm</span><span class="sxs-lookup"><span data-stu-id="abc05-1807">tarjeta atm</span></span> 
- <span data-ttu-id="abc05-1808">tarjeta credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1808">tarjeta credito</span></span> 
- <span data-ttu-id="abc05-1809">tarjeta de atm</span><span class="sxs-lookup"><span data-stu-id="abc05-1809">tarjeta de atm</span></span> 
- <span data-ttu-id="abc05-1810">tarjeta de credito</span><span class="sxs-lookup"><span data-stu-id="abc05-1810">tarjeta de credito</span></span> 
- <span data-ttu-id="abc05-1811">tarjeta de debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1811">tarjeta de debito</span></span> 
- <span data-ttu-id="abc05-1812">tarjeta debito</span><span class="sxs-lookup"><span data-stu-id="abc05-1812">tarjeta debito</span></span> 
- <span data-ttu-id="abc05-1813">tarjeta no</span><span class="sxs-lookup"><span data-stu-id="abc05-1813">tarjeta no</span></span>
- <span data-ttu-id="abc05-1814">tarjetahabiente</span><span class="sxs-lookup"><span data-stu-id="abc05-1814">tarjetahabiente</span></span> 
- <span data-ttu-id="abc05-1815">tipo della scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1815">tipo della scheda</span></span> 
- <span data-ttu-id="abc05-1816">ufficio giapponese della</span><span class="sxs-lookup"><span data-stu-id="abc05-1816">ufficio giapponese della</span></span> 
- <span data-ttu-id="abc05-1817">scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1817">scheda</span></span> 
- <span data-ttu-id="abc05-1818">v pay</span><span class="sxs-lookup"><span data-stu-id="abc05-1818">v pay</span></span> 
- <span data-ttu-id="abc05-1819">v-지급</span><span class="sxs-lookup"><span data-stu-id="abc05-1819">v-pay</span></span> 
- <span data-ttu-id="abc05-1820">visa</span><span class="sxs-lookup"><span data-stu-id="abc05-1820">visa</span></span> 
- <span data-ttu-id="abc05-1821">visa plus</span><span class="sxs-lookup"><span data-stu-id="abc05-1821">visa plus</span></span> 
- <span data-ttu-id="abc05-1822">visa electron</span><span class="sxs-lookup"><span data-stu-id="abc05-1822">visa electron</span></span> 
- <span data-ttu-id="abc05-1823">visto</span><span class="sxs-lookup"><span data-stu-id="abc05-1823">visto</span></span> 
- <span data-ttu-id="abc05-1824">visum</span><span class="sxs-lookup"><span data-stu-id="abc05-1824">visum</span></span> 
- <span data-ttu-id="abc05-1825">vpay</span><span class="sxs-lookup"><span data-stu-id="abc05-1825">vpay</span></span>   

#### <a name="keyword_card_security_terms_dict"></a><span data-ttu-id="abc05-1826">Keyword_card_security_terms_dict</span><span class="sxs-lookup"><span data-stu-id="abc05-1826">Keyword_card_security_terms_dict</span></span>

- <span data-ttu-id="abc05-1827">card identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-1827">card identification number</span></span>
- <span data-ttu-id="abc05-1828">card verification</span><span class="sxs-lookup"><span data-stu-id="abc05-1828">card verification</span></span> 
- <span data-ttu-id="abc05-1829">cardi la verifica</span><span class="sxs-lookup"><span data-stu-id="abc05-1829">cardi la verifica</span></span> 
- <span data-ttu-id="abc05-1830">cid</span><span class="sxs-lookup"><span data-stu-id="abc05-1830">cid</span></span> 
- <span data-ttu-id="abc05-1831">cod seg</span><span class="sxs-lookup"><span data-stu-id="abc05-1831">cod seg</span></span> 
- <span data-ttu-id="abc05-1832">cod seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1832">cod seguranca</span></span> 
- <span data-ttu-id="abc05-1833">cod segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1833">cod segurança</span></span> 
- <span data-ttu-id="abc05-1834">cod sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1834">cod sicurezza</span></span> 
- <span data-ttu-id="abc05-1835">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1835">cod.</span></span> <span data-ttu-id="abc05-1836">seg</span><span class="sxs-lookup"><span data-stu-id="abc05-1836">seg</span></span> 
- <span data-ttu-id="abc05-1837">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1837">cod.</span></span> <span data-ttu-id="abc05-1838">seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1838">seguranca</span></span> 
- <span data-ttu-id="abc05-1839">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1839">cod.</span></span> <span data-ttu-id="abc05-1840">segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1840">segurança</span></span> 
- <span data-ttu-id="abc05-1841">cod.</span><span class="sxs-lookup"><span data-stu-id="abc05-1841">cod.</span></span> <span data-ttu-id="abc05-1842">sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1842">sicurezza</span></span> 
- <span data-ttu-id="abc05-1843">codice di sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1843">codice di sicurezza</span></span> 
- <span data-ttu-id="abc05-1844">codice di verifica</span><span class="sxs-lookup"><span data-stu-id="abc05-1844">codice di verifica</span></span> 
- <span data-ttu-id="abc05-1845">codigo</span><span class="sxs-lookup"><span data-stu-id="abc05-1845">codigo</span></span> 
- <span data-ttu-id="abc05-1846">codigo de seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1846">codigo de seguranca</span></span> 
- <span data-ttu-id="abc05-1847">codigo de segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1847">codigo de segurança</span></span> 
- <span data-ttu-id="abc05-1848">crittogramma</span><span class="sxs-lookup"><span data-stu-id="abc05-1848">crittogramma</span></span> 
- <span data-ttu-id="abc05-1849">cryptogram</span><span class="sxs-lookup"><span data-stu-id="abc05-1849">cryptogram</span></span> 
- <span data-ttu-id="abc05-1850">cryptogramme</span><span class="sxs-lookup"><span data-stu-id="abc05-1850">cryptogramme</span></span> 
- <span data-ttu-id="abc05-1851">cv2</span><span class="sxs-lookup"><span data-stu-id="abc05-1851">cv2</span></span> 
- <span data-ttu-id="abc05-1852">cvc</span><span class="sxs-lookup"><span data-stu-id="abc05-1852">cvc</span></span> 
- <span data-ttu-id="abc05-1853">cvc2</span><span class="sxs-lookup"><span data-stu-id="abc05-1853">cvc2</span></span> 
- <span data-ttu-id="abc05-1854">cvn</span><span class="sxs-lookup"><span data-stu-id="abc05-1854">cvn</span></span> 
- <span data-ttu-id="abc05-1855">cvv</span><span class="sxs-lookup"><span data-stu-id="abc05-1855">cvv</span></span> 
- <span data-ttu-id="abc05-1856">cvv2</span><span class="sxs-lookup"><span data-stu-id="abc05-1856">cvv2</span></span> 
- <span data-ttu-id="abc05-1857">cód seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1857">cód seguranca</span></span> 
- <span data-ttu-id="abc05-1858">cód segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1858">cód segurança</span></span> 
- <span data-ttu-id="abc05-1859">cód.</span><span class="sxs-lookup"><span data-stu-id="abc05-1859">cód.</span></span> <span data-ttu-id="abc05-1860">seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1860">seguranca</span></span> 
- <span data-ttu-id="abc05-1861">cód.</span><span class="sxs-lookup"><span data-stu-id="abc05-1861">cód.</span></span> <span data-ttu-id="abc05-1862">segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1862">segurança</span></span> 
- <span data-ttu-id="abc05-1863">código</span><span class="sxs-lookup"><span data-stu-id="abc05-1863">código</span></span> 
- <span data-ttu-id="abc05-1864">código de seguranca</span><span class="sxs-lookup"><span data-stu-id="abc05-1864">código de seguranca</span></span> 
- <span data-ttu-id="abc05-1865">código de segurança</span><span class="sxs-lookup"><span data-stu-id="abc05-1865">código de segurança</span></span> 
- <span data-ttu-id="abc05-1866">de kaart controle</span><span class="sxs-lookup"><span data-stu-id="abc05-1866">de kaart controle</span></span> 
- <span data-ttu-id="abc05-1867">geeft nr uit</span><span class="sxs-lookup"><span data-stu-id="abc05-1867">geeft nr uit</span></span> 
- <span data-ttu-id="abc05-1868">issue no</span><span class="sxs-lookup"><span data-stu-id="abc05-1868">issue no</span></span> 
- <span data-ttu-id="abc05-1869">issue number</span><span class="sxs-lookup"><span data-stu-id="abc05-1869">issue number</span></span> 
- <span data-ttu-id="abc05-1870">kaartidentificatienummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1870">kaartidentificatienummer</span></span> 
- <span data-ttu-id="abc05-1871">kreditkartenprufnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1871">kreditkartenprufnummer</span></span> 
- <span data-ttu-id="abc05-1872">kreditkartenprüfnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1872">kreditkartenprüfnummer</span></span> 
- <span data-ttu-id="abc05-1873">kwestieaantal</span><span class="sxs-lookup"><span data-stu-id="abc05-1873">kwestieaantal</span></span> 
- <span data-ttu-id="abc05-1874">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1874">no.</span></span> <span data-ttu-id="abc05-1875">dell'edizione</span><span class="sxs-lookup"><span data-stu-id="abc05-1875">dell'edizione</span></span> 
- <span data-ttu-id="abc05-1876">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1876">no.</span></span> <span data-ttu-id="abc05-1877">di sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1877">di sicurezza</span></span> 
- <span data-ttu-id="abc05-1878">numero de securite</span><span class="sxs-lookup"><span data-stu-id="abc05-1878">numero de securite</span></span> 
- <span data-ttu-id="abc05-1879">numero de verificacao</span><span class="sxs-lookup"><span data-stu-id="abc05-1879">numero de verificacao</span></span> 
- <span data-ttu-id="abc05-1880">numero dell'edizione</span><span class="sxs-lookup"><span data-stu-id="abc05-1880">numero dell'edizione</span></span> 
- <span data-ttu-id="abc05-1881">numero di identificazione della</span><span class="sxs-lookup"><span data-stu-id="abc05-1881">numero di identificazione della</span></span> 
- <span data-ttu-id="abc05-1882">scheda</span><span class="sxs-lookup"><span data-stu-id="abc05-1882">scheda</span></span> 
- <span data-ttu-id="abc05-1883">numero di sicurezza</span><span class="sxs-lookup"><span data-stu-id="abc05-1883">numero di sicurezza</span></span> 
- <span data-ttu-id="abc05-1884">numero van veiligheid</span><span class="sxs-lookup"><span data-stu-id="abc05-1884">numero van veiligheid</span></span> 
- <span data-ttu-id="abc05-1885">numéro de sécurité</span><span class="sxs-lookup"><span data-stu-id="abc05-1885">numéro de sécurité</span></span> 
- <span data-ttu-id="abc05-1886">nº autorizzazione</span><span class="sxs-lookup"><span data-stu-id="abc05-1886">nº autorizzazione</span></span> 
- <span data-ttu-id="abc05-1887">número de verificação</span><span class="sxs-lookup"><span data-stu-id="abc05-1887">número de verificação</span></span> 
- <span data-ttu-id="abc05-1888">perno il blocco</span><span class="sxs-lookup"><span data-stu-id="abc05-1888">perno il blocco</span></span> 
- <span data-ttu-id="abc05-1889">pin block</span><span class="sxs-lookup"><span data-stu-id="abc05-1889">pin block</span></span> 
- <span data-ttu-id="abc05-1890">prufziffer</span><span class="sxs-lookup"><span data-stu-id="abc05-1890">prufziffer</span></span> 
- <span data-ttu-id="abc05-1891">prüfziffer</span><span class="sxs-lookup"><span data-stu-id="abc05-1891">prüfziffer</span></span> 
- <span data-ttu-id="abc05-1892">security code</span><span class="sxs-lookup"><span data-stu-id="abc05-1892">security code</span></span> 
- <span data-ttu-id="abc05-1893">security no</span><span class="sxs-lookup"><span data-stu-id="abc05-1893">security no</span></span> 
- <span data-ttu-id="abc05-1894">security number</span><span class="sxs-lookup"><span data-stu-id="abc05-1894">security number</span></span> 
- <span data-ttu-id="abc05-1895">sicherheits kode</span><span class="sxs-lookup"><span data-stu-id="abc05-1895">sicherheits kode</span></span> 
- <span data-ttu-id="abc05-1896">sicherheitscode</span><span class="sxs-lookup"><span data-stu-id="abc05-1896">sicherheitscode</span></span> 
- <span data-ttu-id="abc05-1897">sicherheitsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1897">sicherheitsnummer</span></span> 
- <span data-ttu-id="abc05-1898">speldblok</span><span class="sxs-lookup"><span data-stu-id="abc05-1898">speldblok</span></span> 
- <span data-ttu-id="abc05-1899">veiligheid 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-1899">veiligheid nr</span></span> 
- <span data-ttu-id="abc05-1900">veiligheidsaantal</span><span class="sxs-lookup"><span data-stu-id="abc05-1900">veiligheidsaantal</span></span> 
- <span data-ttu-id="abc05-1901">veiligheidscode</span><span class="sxs-lookup"><span data-stu-id="abc05-1901">veiligheidscode</span></span> 
- <span data-ttu-id="abc05-1902">veiligheidsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1902">veiligheidsnummer</span></span> 
- <span data-ttu-id="abc05-1903">verfalldatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1903">verfalldatum</span></span> 

#### <a name="keyword_card_expiration_terms_dict"></a><span data-ttu-id="abc05-1904">Keyword_card_expiration_terms_dict</span><span class="sxs-lookup"><span data-stu-id="abc05-1904">Keyword_card_expiration_terms_dict</span></span>

- <span data-ttu-id="abc05-1905">ablauf</span><span class="sxs-lookup"><span data-stu-id="abc05-1905">ablauf</span></span> 
- <span data-ttu-id="abc05-1906">data de expiracao</span><span class="sxs-lookup"><span data-stu-id="abc05-1906">data de expiracao</span></span> 
- <span data-ttu-id="abc05-1907">data de expiração</span><span class="sxs-lookup"><span data-stu-id="abc05-1907">data de expiração</span></span> 
- <span data-ttu-id="abc05-1908">data del exp</span><span class="sxs-lookup"><span data-stu-id="abc05-1908">data del exp</span></span> 
- <span data-ttu-id="abc05-1909">data di exp</span><span class="sxs-lookup"><span data-stu-id="abc05-1909">data di exp</span></span> 
- <span data-ttu-id="abc05-1910">data di scadenza</span><span class="sxs-lookup"><span data-stu-id="abc05-1910">data di scadenza</span></span> 
- <span data-ttu-id="abc05-1911">data em que expira</span><span class="sxs-lookup"><span data-stu-id="abc05-1911">data em que expira</span></span> 
- <span data-ttu-id="abc05-1912">data scad</span><span class="sxs-lookup"><span data-stu-id="abc05-1912">data scad</span></span> 
- <span data-ttu-id="abc05-1913">data scadenza</span><span class="sxs-lookup"><span data-stu-id="abc05-1913">data scadenza</span></span> 
- <span data-ttu-id="abc05-1914">date de validité</span><span class="sxs-lookup"><span data-stu-id="abc05-1914">date de validité</span></span> 
- <span data-ttu-id="abc05-1915">datum afloop</span><span class="sxs-lookup"><span data-stu-id="abc05-1915">datum afloop</span></span> 
- <span data-ttu-id="abc05-1916">datum van exp</span><span class="sxs-lookup"><span data-stu-id="abc05-1916">datum van exp</span></span> 
- <span data-ttu-id="abc05-1917">de afloop</span><span class="sxs-lookup"><span data-stu-id="abc05-1917">de afloop</span></span> 
- <span data-ttu-id="abc05-1918">espira</span><span class="sxs-lookup"><span data-stu-id="abc05-1918">espira</span></span> 
- <span data-ttu-id="abc05-1919">espira</span><span class="sxs-lookup"><span data-stu-id="abc05-1919">espira</span></span> 
- <span data-ttu-id="abc05-1920">exp date</span><span class="sxs-lookup"><span data-stu-id="abc05-1920">exp date</span></span> 
- <span data-ttu-id="abc05-1921">exp datum</span><span class="sxs-lookup"><span data-stu-id="abc05-1921">exp datum</span></span> 
- <span data-ttu-id="abc05-1922">행사</span><span class="sxs-lookup"><span data-stu-id="abc05-1922">expiration</span></span> 
- <span data-ttu-id="abc05-1923">예정</span><span class="sxs-lookup"><span data-stu-id="abc05-1923">expire</span></span> 
- <span data-ttu-id="abc05-1924">expires</span><span class="sxs-lookup"><span data-stu-id="abc05-1924">expires</span></span> 
- <span data-ttu-id="abc05-1925">만료</span><span class="sxs-lookup"><span data-stu-id="abc05-1925">expiry</span></span> 
- <span data-ttu-id="abc05-1926">fecha de expiracion</span><span class="sxs-lookup"><span data-stu-id="abc05-1926">fecha de expiracion</span></span> 
- <span data-ttu-id="abc05-1927">fecha de venc</span><span class="sxs-lookup"><span data-stu-id="abc05-1927">fecha de venc</span></span> 
- <span data-ttu-id="abc05-1928">gultig bis</span><span class="sxs-lookup"><span data-stu-id="abc05-1928">gultig bis</span></span> 
- <span data-ttu-id="abc05-1929">gultigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1929">gultigkeitsdatum</span></span> 
- <span data-ttu-id="abc05-1930">gültig bis</span><span class="sxs-lookup"><span data-stu-id="abc05-1930">gültig bis</span></span> 
- <span data-ttu-id="abc05-1931">gültigkeitsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1931">gültigkeitsdatum</span></span> 
- <span data-ttu-id="abc05-1932">la scadenza</span><span class="sxs-lookup"><span data-stu-id="abc05-1932">la scadenza</span></span> 
- <span data-ttu-id="abc05-1933">scadenza</span><span class="sxs-lookup"><span data-stu-id="abc05-1933">scadenza</span></span> 
- <span data-ttu-id="abc05-1934">valable</span><span class="sxs-lookup"><span data-stu-id="abc05-1934">valable</span></span> 
- <span data-ttu-id="abc05-1935">유효한 ade</span><span class="sxs-lookup"><span data-stu-id="abc05-1935">validade</span></span> 
- <span data-ttu-id="abc05-1936">valido hasta</span><span class="sxs-lookup"><span data-stu-id="abc05-1936">valido hasta</span></span> 
- <span data-ttu-id="abc05-1937">valor</span><span class="sxs-lookup"><span data-stu-id="abc05-1937">valor</span></span> 
- <span data-ttu-id="abc05-1938">venc</span><span class="sxs-lookup"><span data-stu-id="abc05-1938">venc</span></span> 
- <span data-ttu-id="abc05-1939">vencimento</span><span class="sxs-lookup"><span data-stu-id="abc05-1939">vencimento</span></span> 
- <span data-ttu-id="abc05-1940">vencimiento</span><span class="sxs-lookup"><span data-stu-id="abc05-1940">vencimiento</span></span> 
- <span data-ttu-id="abc05-1941">verloopt</span><span class="sxs-lookup"><span data-stu-id="abc05-1941">verloopt</span></span> 
- <span data-ttu-id="abc05-1942">vervaldag</span><span class="sxs-lookup"><span data-stu-id="abc05-1942">vervaldag</span></span> 
- <span data-ttu-id="abc05-1943">vervaldatum</span><span class="sxs-lookup"><span data-stu-id="abc05-1943">vervaldatum</span></span> 
- <span data-ttu-id="abc05-1944">vto</span><span class="sxs-lookup"><span data-stu-id="abc05-1944">vto</span></span> 
- <span data-ttu-id="abc05-1945">válido hasta</span><span class="sxs-lookup"><span data-stu-id="abc05-1945">válido hasta</span></span> 
   
## <a name="eu-drivers-license-number"></a><span data-ttu-id="abc05-1946">EU 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1946">EU Driver's License Number</span></span>

<span data-ttu-id="abc05-1947">자세한 내용은 [EU 운전 면허 번호 중요 정보 유형을](eu-driver-s-license-number.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abc05-1947">To learn more, see [EU Driver's License Number sensitive information type](eu-driver-s-license-number.md).</span></span>
  
## <a name="eu-national-identification-number"></a><span data-ttu-id="abc05-1948">EU 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1948">EU National Identification Number</span></span>

<span data-ttu-id="abc05-1949">자세한 내용은 [EU 국가 식별 번호 중요 한 정보 유형을](eu-national-identification-number.md)참조 하세요.</span><span class="sxs-lookup"><span data-stu-id="abc05-1949">To learn more, see [EU National Identification Number sensitive information type](eu-national-identification-number.md).</span></span>
  
## <a name="eu-passport-number"></a><span data-ttu-id="abc05-1950">EU 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1950">EU Passport Number</span></span>

<span data-ttu-id="abc05-1951">자세한 내용은 [EU Passport 번호 중요 한 정보 유형을](eu-passport-number.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abc05-1951">To learn more, see [EU Passport Number sensitive information type](eu-passport-number.md).</span></span>
  
## <a name="eu-social-security-number-or-equivalent-id"></a><span data-ttu-id="abc05-1952">EU 주민 등록 번호 또는 동등한 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-1952">EU Social Security Number or Equivalent ID</span></span>

<span data-ttu-id="abc05-1953">자세한 내용은 [EU 주민 등록 번호 또는 동등한 ID 중요 정보 유형을](eu-social-security-number-or-equivalent-id.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abc05-1953">To learn more, see [EU Social Security Number or Equivalent ID sensitive information type](eu-social-security-number-or-equivalent-id.md).</span></span>
  
## <a name="eu-tax-identification-number"></a><span data-ttu-id="abc05-1954">EU 세금 확인 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1954">EU Tax Identification Number</span></span>

<span data-ttu-id="abc05-1955">자세한 내용은 [EU 세금 식별 번호 중요 한 정보 유형을](eu-tax-identification-number.md)참조 하십시오.</span><span class="sxs-lookup"><span data-stu-id="abc05-1955">To learn more, see [EU Tax Identification Number sensitive information type](eu-tax-identification-number.md).</span></span>
  
## <a name="finland-national-id"></a><span data-ttu-id="abc05-1956">핀란드 국가 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-1956">Finland National ID</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1957">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1957">Format</span></span>

<span data-ttu-id="abc05-1958">세기를 나타내는 6자리 숫자와 문자, 3자리 숫자와 검사 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1958">Six digits plus a character indicating a century plus three digits plus a check digit</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1959">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1959">Pattern</span></span>

<span data-ttu-id="abc05-1960">패턴에는 다음이 모두 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1960">Pattern must include all of the following:</span></span>
- <span data-ttu-id="abc05-1961">생년월일에 해당하는 DDMMYY 형식의 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1961">Six digits in the format format DDMMYY which are a date of birth</span></span> 
- <span data-ttu-id="abc05-1962">세기 표시('-', '+' 또는 'a')</span><span class="sxs-lookup"><span data-stu-id="abc05-1962">Century marker (either '-', '+' or 'a')</span></span> 
- <span data-ttu-id="abc05-1963">3자리 개인 ID 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1963">Three-digit personal identification number</span></span> 
- <span data-ttu-id="abc05-1964">검사 숫자에 해당하는 1자리 숫자 또는 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-1964">A digit or letter (case insensitive) which is a check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1965">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1965">Checksum</span></span>

<span data-ttu-id="abc05-1966">예</span><span class="sxs-lookup"><span data-stu-id="abc05-1966">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1967">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1967">Definition</span></span>

<span data-ttu-id="abc05-1968">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1968">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1969">Func_finnish_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1969">The function Func_finnish_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1970">Keyword_finnish_national_id의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1970">A keyword from Keyword_finnish_national_id is found.</span></span>
- <span data-ttu-id="abc05-1971">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1971">The checksum passes.</span></span>

```xml
<!-- Finnish National ID-->
<Entity id="338FD995-4CB5-4F87-AD35-79BD1DD926C1" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_finnish_national_id" />
          <Match idRef="Keyword_finnish_national_id" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1972">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1972">Keywords</span></span>

- <span data-ttu-id="abc05-1973">Keyword_finnish_national_id</span><span class="sxs-lookup"><span data-stu-id="abc05-1973">Keyword_finnish_national_id</span></span>
- <span data-ttu-id="abc05-1974">Sosiaaliturvatunnus</span><span class="sxs-lookup"><span data-stu-id="abc05-1974">Sosiaaliturvatunnus</span></span>
- <span data-ttu-id="abc05-1975">SOTU Henkilötunnus HETU</span><span class="sxs-lookup"><span data-stu-id="abc05-1975">SOTU Henkilötunnus HETU</span></span>
- <span data-ttu-id="abc05-1976">Personbeteckning</span><span class="sxs-lookup"><span data-stu-id="abc05-1976">Personbeteckning</span></span>
- <span data-ttu-id="abc05-1977">Personnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-1977">Personnummer</span></span>
   
## <a name="finland-passport-number"></a><span data-ttu-id="abc05-1978">핀란드 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1978">Finland Passport Number</span></span>

<span data-ttu-id="abc05-1979">9 개의 문자 및 숫자 패턴 조합 형식 조합: 두 문자 (대/소문자 구분 안 함) 7 자리 체크섬 정의 없음 DLP 75 정책은이 유형의 중요 한 정보를 검색 한 것으로,이에 따라 300 문자의 근사: 정규식 Regex_finland_passport_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1979">Format Combination of nine letters and digits Pattern Combination of nine letters and digits: Two letters (not case sensitive) Seven digits Checksum No Definition A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The regular expression Regex_finland_passport_number finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-1980">Keyword_finland_passport_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1980">A keyword from Keyword_finland_passport_number is found.</span></span>
<!-- Finland Passport Number -->
<span data-ttu-id="abc05-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span><span class="sxs-lookup"><span data-stu-id="abc05-1981"><Entity id="d1685ac3-1d3a-40f8-8198-32ef5669c7a5" recommendedConfidence="75" patternsProximity="300"> <Pattern confidenceLevel="75"> <IdMatch idRef="Regex_finland_passport_number"/> <Match idRef="Keyword_finland_passport_number"/> </Pattern>
</Entity></span></span>
<span data-ttu-id="abc05-1982">Passport Keyword_finland_passport_number의 키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1982">Keywords Keyword_finland_passport_number Passport Passi</span></span>
   
## <a name="france-drivers-license-number"></a><span data-ttu-id="abc05-1983">프랑스 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-1983">France Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-1984">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-1984">Format</span></span>

<span data-ttu-id="abc05-1985">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1985">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-1986">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-1986">Pattern</span></span>

<span data-ttu-id="abc05-1987">비슷한 패턴(예: 프랑스 전화 번호)을 무시하기 위한 유효성 검사 기능을 포함하는 12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-1987">12 digits with validation to discount similar patterns such as French telephone numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-1988">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-1988">Checksum</span></span>

<span data-ttu-id="abc05-1989">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-1989">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-1990">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-1990">Definition</span></span>

<span data-ttu-id="abc05-1991">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1991">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-1992">Func_french_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1992">The function Func_french_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-1993">다음 중 하나 이상이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1993">At least one of the following is true:</span></span>
- <span data-ttu-id="abc05-1994">Keyword_french_drivers_license의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1994">A keyword from Keyword_french_drivers_license is found.</span></span>
- <span data-ttu-id="abc05-1995">Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-1995">The function Func_eu_date finds a date in the right date format.</span></span>

```xml
<!-- France Driver's License Number -->
<Entity id="18e55a36-a01b-4b0f-943d-dc10282a1824" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_french_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_french_drivers_license" />
          <Match idRef="Func_eu_date" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-1996">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-1996">Keywords</span></span>

#### <a name="keyword_french_drivers_license"></a><span data-ttu-id="abc05-1997">Keyword_french_drivers_license</span><span class="sxs-lookup"><span data-stu-id="abc05-1997">Keyword_french_drivers_license</span></span>

- <span data-ttu-id="abc05-1998">drivers licence</span><span class="sxs-lookup"><span data-stu-id="abc05-1998">drivers licence</span></span>
- <span data-ttu-id="abc05-1999">drivers license</span><span class="sxs-lookup"><span data-stu-id="abc05-1999">drivers license</span></span>
- <span data-ttu-id="abc05-2000">driving licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2000">driving licence</span></span>
- <span data-ttu-id="abc05-2001">driving license</span><span class="sxs-lookup"><span data-stu-id="abc05-2001">driving license</span></span>
- <span data-ttu-id="abc05-2002">permis de conduire</span><span class="sxs-lookup"><span data-stu-id="abc05-2002">permis de conduire</span></span>
- <span data-ttu-id="abc05-2003">licence number</span><span class="sxs-lookup"><span data-stu-id="abc05-2003">licence number</span></span>
- <span data-ttu-id="abc05-2004">license number</span><span class="sxs-lookup"><span data-stu-id="abc05-2004">license number</span></span>
- <span data-ttu-id="abc05-2005">licence numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-2005">licence numbers</span></span>
- <span data-ttu-id="abc05-2006">license numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-2006">license numbers</span></span>

## <a name="france-national-id-card-cni"></a><span data-ttu-id="abc05-2007">프랑스 국가 ID 카드(CNI)</span><span class="sxs-lookup"><span data-stu-id="abc05-2007">France National ID Card (CNI)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2008">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2008">Format</span></span>

<span data-ttu-id="abc05-2009">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2009">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2010">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2010">Pattern</span></span>

<span data-ttu-id="abc05-2011">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2011">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2012">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2012">Checksum</span></span>

<span data-ttu-id="abc05-2013">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2013">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2014">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2014">Definition</span></span>

<span data-ttu-id="abc05-2015">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2015">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2016">Regex_france_cni 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2016">The regular expression Regex_france_cni finds content that matches the pattern.</span></span>

```xml
<!-- France CNI -->
<Entity id="f741ac74-1bc0-4665-b69b-f0c7f927c0c4" patternsProximity="300" recommendedConfidence="65">
  <Pattern confidenceLevel="65">
        <IdMatch idRef="Regex_france_cni" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2017">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2017">Keywords</span></span>

<span data-ttu-id="abc05-2018">없음</span><span class="sxs-lookup"><span data-stu-id="abc05-2018">None</span></span>
   
## <a name="france-passport-number"></a><span data-ttu-id="abc05-2019">프랑스 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2019">France Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2020">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2020">Format</span></span>

<span data-ttu-id="abc05-2021">9자리 숫자 및 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2021">Nine digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2022">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2022">Pattern</span></span>

<span data-ttu-id="abc05-2023">9자리 숫자 및 문자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2023">Nine digits and letters:</span></span>
- <span data-ttu-id="abc05-2024">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2024">Two digits</span></span> 
- <span data-ttu-id="abc05-2025">2문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2025">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2026">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2026">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2027">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2027">Checksum</span></span>

<span data-ttu-id="abc05-2028">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2028">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2029">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2029">Definition</span></span>

<span data-ttu-id="abc05-2030">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2030">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2031">Func_fr_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2031">The function Func_fr_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2032">Keyword_passport의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2032">A keyword from Keyword_passport is found.</span></span>

```xml
<!-- France Passport Number -->
<Entity id="3008b884-8c8c-4cd8-a289-99f34fc7ff5d" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_fr_passport" />
        <Match idRef="Keyword_passport" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2033">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2033">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="abc05-2034">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-2034">Keyword_passport</span></span>

- <span data-ttu-id="abc05-2035">Passport Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2035">Passport Number</span></span>
- <span data-ttu-id="abc05-2036">Passport No</span><span class="sxs-lookup"><span data-stu-id="abc05-2036">Passport No</span></span>
- <span data-ttu-id="abc05-2037">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-2037">Passport #</span></span>
- <span data-ttu-id="abc05-2038">여권 #</span><span class="sxs-lookup"><span data-stu-id="abc05-2038">Passport#</span></span>
- <span data-ttu-id="abc05-2039">PassportID</span><span class="sxs-lookup"><span data-stu-id="abc05-2039">PassportID</span></span>
- <span data-ttu-id="abc05-2040">Passportno</span><span class="sxs-lookup"><span data-stu-id="abc05-2040">Passportno</span></span>
- <span data-ttu-id="abc05-2041">passportnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-2041">passportnumber</span></span>
- <span data-ttu-id="abc05-2042">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-2042">パスポート</span></span>
- <span data-ttu-id="abc05-2043">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2043">パスポート番号</span></span>
- <span data-ttu-id="abc05-2044">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-2044">パスポートのNum</span></span>
- <span data-ttu-id="abc05-2045">パスポート ＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2045">パスポート ＃</span></span> 
- <span data-ttu-id="abc05-2046">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="abc05-2046">Numéro de passeport</span></span>
- <span data-ttu-id="abc05-2047">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="abc05-2047">Passeport n °</span></span>
- <span data-ttu-id="abc05-2048">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="abc05-2048">Passeport Non</span></span>
- <span data-ttu-id="abc05-2049">Passeport #</span><span class="sxs-lookup"><span data-stu-id="abc05-2049">Passeport #</span></span>
- <span data-ttu-id="abc05-2050">포트 #</span><span class="sxs-lookup"><span data-stu-id="abc05-2050">Passeport#</span></span>
- <span data-ttu-id="abc05-2051">지/포트 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-2051">PasseportNon</span></span>
- <span data-ttu-id="abc05-2052">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="abc05-2052">Passeportn °</span></span>

      
## <a name="france-social-security-number-insee"></a><span data-ttu-id="abc05-2053">프랑스 사회 보장 번호(INSEE)</span><span class="sxs-lookup"><span data-stu-id="abc05-2053">France Social Security Number (INSEE)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2054">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2054">Format</span></span>

<span data-ttu-id="abc05-2055">15자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2055">15 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2056">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2056">Pattern</span></span>

<span data-ttu-id="abc05-2057">다음 두 패턴 중 하나가 일치해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2057">Must match one of two patterns:</span></span>
- <span data-ttu-id="abc05-2058">13 자리 숫자와 공백 다음 두 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2058">13 digits followed by a space followed by two digits</span></span><br/>
<span data-ttu-id="abc05-2059">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-2059">or</span></span>
- <span data-ttu-id="abc05-2060">15자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2060">15 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2061">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2061">Checksum</span></span>

<span data-ttu-id="abc05-2062">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2062">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2063">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2063">Definition</span></span>

<span data-ttu-id="abc05-2064">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2064">A DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2065">Func_french_insee 또는 Func_fr_insee 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2065">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2066">Keyword_fr_insee의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2066">A keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="abc05-2067">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2067">The checksum passes.</span></span>

<span data-ttu-id="abc05-2068">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2068">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2069">Func_french_insee 또는 Func_fr_insee 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2069">The function Func_french_insee or Func_fr_insee finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2070">Keyword_fr_insee의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2070">No keyword from Keyword_fr_insee is found.</span></span>
- <span data-ttu-id="abc05-2071">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2071">The checksum passes.</span></span>

```xml
<!-- France INSEE -->
<Entity id="71f62b97-efe0-4aa1-aa49-e14de253619d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="95">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="1">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_french_insee" />
        <Match idRef="Func_fr_insee" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_fr_insee" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2072">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2072">Keywords</span></span>

#### <a name="keyword_fr_insee"></a><span data-ttu-id="abc05-2073">Keyword_fr_insee</span><span class="sxs-lookup"><span data-stu-id="abc05-2073">Keyword_fr_insee</span></span>

- <span data-ttu-id="abc05-2074">insee</span><span class="sxs-lookup"><span data-stu-id="abc05-2074">insee</span></span>
- <span data-ttu-id="abc05-2075">securité sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-2075">securité sociale</span></span>
- <span data-ttu-id="abc05-2076">securite sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-2076">securite sociale</span></span>
- <span data-ttu-id="abc05-2077">national id</span><span class="sxs-lookup"><span data-stu-id="abc05-2077">national id</span></span>
- <span data-ttu-id="abc05-2078">national identification</span><span class="sxs-lookup"><span data-stu-id="abc05-2078">national identification</span></span>
- <span data-ttu-id="abc05-2079">numéro d'identité</span><span class="sxs-lookup"><span data-stu-id="abc05-2079">numéro d'identité</span></span>
- <span data-ttu-id="abc05-2080">no d'identité</span><span class="sxs-lookup"><span data-stu-id="abc05-2080">no d'identité</span></span>
- <span data-ttu-id="abc05-2081">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-2081">no.</span></span> <span data-ttu-id="abc05-2082">d'identité</span><span class="sxs-lookup"><span data-stu-id="abc05-2082">d'identité</span></span>
- <span data-ttu-id="abc05-2083">numero d'identite</span><span class="sxs-lookup"><span data-stu-id="abc05-2083">numero d'identite</span></span>
- <span data-ttu-id="abc05-2084">no d'identite</span><span class="sxs-lookup"><span data-stu-id="abc05-2084">no d'identite</span></span>
- <span data-ttu-id="abc05-2085">아니요.</span><span class="sxs-lookup"><span data-stu-id="abc05-2085">no.</span></span> <span data-ttu-id="abc05-2086">d'identite</span><span class="sxs-lookup"><span data-stu-id="abc05-2086">d'identite</span></span>
- <span data-ttu-id="abc05-2087">social security number</span><span class="sxs-lookup"><span data-stu-id="abc05-2087">social security number</span></span>
- <span data-ttu-id="abc05-2088">social security code</span><span class="sxs-lookup"><span data-stu-id="abc05-2088">social security code</span></span>
- <span data-ttu-id="abc05-2089">social insurance number</span><span class="sxs-lookup"><span data-stu-id="abc05-2089">social insurance number</span></span>
- <span data-ttu-id="abc05-2090">le numéro d'identification nationale</span><span class="sxs-lookup"><span data-stu-id="abc05-2090">le numéro d'identification nationale</span></span>
- <span data-ttu-id="abc05-2091">d'identité nationale</span><span class="sxs-lookup"><span data-stu-id="abc05-2091">d'identité nationale</span></span>
- <span data-ttu-id="abc05-2092">numéro de sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-2092">numéro de sécurité sociale</span></span>
- <span data-ttu-id="abc05-2093">le code de la sécurité sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-2093">le code de la sécurité sociale</span></span>
- <span data-ttu-id="abc05-2094">numéro d'assurance sociale</span><span class="sxs-lookup"><span data-stu-id="abc05-2094">numéro d'assurance sociale</span></span>
- <span data-ttu-id="abc05-2095">numéro de sécu</span><span class="sxs-lookup"><span data-stu-id="abc05-2095">numéro de sécu</span></span>
- <span data-ttu-id="abc05-2096">code sécu</span><span class="sxs-lookup"><span data-stu-id="abc05-2096">code sécu</span></span> 
   
## <a name="german-drivers-license-number"></a><span data-ttu-id="abc05-2097">독일 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2097">German Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2098">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2098">Format</span></span>

<span data-ttu-id="abc05-2099">11자리 숫자와 문자 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-2099">Combination of 11 digits and letters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2100">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2100">Pattern</span></span>

<span data-ttu-id="abc05-2101">11자리 숫자와 문자(대/소문자 구분 안 함):</span><span class="sxs-lookup"><span data-stu-id="abc05-2101">11 digits and letters (not case sensitive):</span></span>
- <span data-ttu-id="abc05-2102">1자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2102">A digit or letter</span></span> 
- <span data-ttu-id="abc05-2103">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2103">Two digits</span></span> 
- <span data-ttu-id="abc05-2104">6자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2104">Six digits or letters</span></span> 
- <span data-ttu-id="abc05-2105">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2105">A digit</span></span> 
- <span data-ttu-id="abc05-2106">1자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2106">A digit or letter</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2107">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2107">Checksum</span></span>

<span data-ttu-id="abc05-2108">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2108">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2109">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2109">Definition</span></span>

<span data-ttu-id="abc05-2110">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2110">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2111">Func_german_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2111">The function Func_german_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2112">다음 중 하나 이상이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2112">At least one of the following is true:</span></span>
    - <span data-ttu-id="abc05-2113">Keyword_german_drivers_license_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2113">A keyword from Keyword_german_drivers_license_number is found.</span></span>
    - <span data-ttu-id="abc05-2114">Keyword_german_drivers_license_collaborative의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2114">A keyword from Keyword_german_drivers_license_collaborative is found.</span></span>
    - <span data-ttu-id="abc05-2115">Keyword_german_drivers_license의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2115">A keyword from Keyword_german_drivers_license is found.</span></span>
- <span data-ttu-id="abc05-2116">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2116">The checksum passes.</span></span>

```xml
<!-- German Driver's License Number -->
<Entity id="91da9335-1edb-45b7-a95f-5fe41a16c63c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_drivers_license" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_drivers_license_number" />
          <Match idRef="Keyword_german_drivers_license_collaborative" />
          <Match idRef="Keyword_german_drivers_license" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2117">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2117">Keywords</span></span>

#### <a name="keyword_german_drivers_license_number"></a><span data-ttu-id="abc05-2118">Keyword_german_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2118">Keyword_german_drivers_license_number</span></span>

- <span data-ttu-id="abc05-2119">Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2119">Führerschein</span></span>
- <span data-ttu-id="abc05-2120">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2120">Fuhrerschein</span></span>
- <span data-ttu-id="abc05-2121">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2121">Fuehrerschein</span></span>
- <span data-ttu-id="abc05-2122">Führerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2122">Führerscheinnummer</span></span>
- <span data-ttu-id="abc05-2123">Fuhrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2123">Fuhrerscheinnummer</span></span>
- <span data-ttu-id="abc05-2124">Fuehrerscheinnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2124">Fuehrerscheinnummer</span></span>
- <span data-ttu-id="abc05-2125">Führerschein-</span><span class="sxs-lookup"><span data-stu-id="abc05-2125">Führerschein-</span></span> 
- <span data-ttu-id="abc05-2126">Fuhrerschein-</span><span class="sxs-lookup"><span data-stu-id="abc05-2126">Fuhrerschein-</span></span> 
- <span data-ttu-id="abc05-2127">Fuehrerschein-</span><span class="sxs-lookup"><span data-stu-id="abc05-2127">Fuehrerschein-</span></span> 
- <span data-ttu-id="abc05-2128">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2128">FührerscheinnummerNr</span></span>
- <span data-ttu-id="abc05-2129">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2129">FuhrerscheinnummerNr</span></span>
- <span data-ttu-id="abc05-2130">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2130">FuehrerscheinnummerNr</span></span>
- <span data-ttu-id="abc05-2131">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2131">FührerscheinnummerKlasse</span></span>
- <span data-ttu-id="abc05-2132">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2132">FuhrerscheinnummerKlasse</span></span>
- <span data-ttu-id="abc05-2133">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2133">FuehrerscheinnummerKlasse</span></span>
- <span data-ttu-id="abc05-2134">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2134">Führerschein- Nr</span></span>
- <span data-ttu-id="abc05-2135">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2135">Fuhrerschein- Nr</span></span>
- <span data-ttu-id="abc05-2136">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2136">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="abc05-2137">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2137">Führerschein- Klasse</span></span> 
- <span data-ttu-id="abc05-2138">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2138">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="abc05-2139">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2139">Fuehrerschein- Klasse</span></span>
- <span data-ttu-id="abc05-2140">FührerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2140">FührerscheinnummerNr</span></span> 
- <span data-ttu-id="abc05-2141">FuhrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2141">FuhrerscheinnummerNr</span></span> 
- <span data-ttu-id="abc05-2142">FuehrerscheinnummerNr</span><span class="sxs-lookup"><span data-stu-id="abc05-2142">FuehrerscheinnummerNr</span></span> 
- <span data-ttu-id="abc05-2143">FührerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2143">FührerscheinnummerKlasse</span></span> 
- <span data-ttu-id="abc05-2144">FuhrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2144">FuhrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="abc05-2145">FuehrerscheinnummerKlasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2145">FuehrerscheinnummerKlasse</span></span> 
- <span data-ttu-id="abc05-2146">Führerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2146">Führerschein- Nr</span></span> 
- <span data-ttu-id="abc05-2147">Fuhrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2147">Fuhrerschein- Nr</span></span> 
- <span data-ttu-id="abc05-2148">Fuehrerschein- Nr</span><span class="sxs-lookup"><span data-stu-id="abc05-2148">Fuehrerschein- Nr</span></span> 
- <span data-ttu-id="abc05-2149">Führerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2149">Führerschein- Klasse</span></span> 
- <span data-ttu-id="abc05-2150">Fuhrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2150">Fuhrerschein- Klasse</span></span> 
- <span data-ttu-id="abc05-2151">Fuehrerschein- Klasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2151">Fuehrerschein- Klasse</span></span> 
- <span data-ttu-id="abc05-2152">DL</span><span class="sxs-lookup"><span data-stu-id="abc05-2152">DL</span></span> 
- <span data-ttu-id="abc05-2153">된다</span><span class="sxs-lookup"><span data-stu-id="abc05-2153">DLS</span></span>
- <span data-ttu-id="abc05-2154">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-2154">Driv Lic</span></span> 
- <span data-ttu-id="abc05-2155">Driv Licen</span><span class="sxs-lookup"><span data-stu-id="abc05-2155">Driv Licen</span></span> 
- <span data-ttu-id="abc05-2156">Driv License</span><span class="sxs-lookup"><span data-stu-id="abc05-2156">Driv License</span></span>
- <span data-ttu-id="abc05-2157">Driv Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2157">Driv Licenses</span></span> 
- <span data-ttu-id="abc05-2158">Driv Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2158">Driv Licence</span></span> 
- <span data-ttu-id="abc05-2159">Driv Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-2159">Driv Licences</span></span> 
- <span data-ttu-id="abc05-2160">Driv Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-2160">Driv Lic</span></span> 
- <span data-ttu-id="abc05-2161">Driver Licen</span><span class="sxs-lookup"><span data-stu-id="abc05-2161">Driver Licen</span></span> 
- <span data-ttu-id="abc05-2162">Driver License</span><span class="sxs-lookup"><span data-stu-id="abc05-2162">Driver License</span></span> 
- <span data-ttu-id="abc05-2163">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2163">Driver Licenses</span></span> 
- <span data-ttu-id="abc05-2164">Driver Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2164">Driver Licence</span></span> 
- <span data-ttu-id="abc05-2165">Driver Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-2165">Driver Licences</span></span> 
- <span data-ttu-id="abc05-2166">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-2166">Drivers Lic</span></span> 
- <span data-ttu-id="abc05-2167">Drivers Licen</span><span class="sxs-lookup"><span data-stu-id="abc05-2167">Drivers Licen</span></span> 
- <span data-ttu-id="abc05-2168">Drivers License</span><span class="sxs-lookup"><span data-stu-id="abc05-2168">Drivers License</span></span> 
- <span data-ttu-id="abc05-2169">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2169">Drivers Licenses</span></span> 
- <span data-ttu-id="abc05-2170">Drivers Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2170">Drivers Licence</span></span> 
- <span data-ttu-id="abc05-2171">Drivers Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-2171">Drivers Licences</span></span> 
- <span data-ttu-id="abc05-2172">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-2172">Driver's Lic</span></span> 
- <span data-ttu-id="abc05-2173">Driver's Licen</span><span class="sxs-lookup"><span data-stu-id="abc05-2173">Driver's Licen</span></span> 
- <span data-ttu-id="abc05-2174">Driver's License</span><span class="sxs-lookup"><span data-stu-id="abc05-2174">Driver's License</span></span> 
- <span data-ttu-id="abc05-2175">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2175">Driver's Licenses</span></span> 
- <span data-ttu-id="abc05-2176">Driver's Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2176">Driver's Licence</span></span> 
- <span data-ttu-id="abc05-2177">Driver's Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-2177">Driver's Licences</span></span> 
- <span data-ttu-id="abc05-2178">Driving Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-2178">Driving Lic</span></span> 
- <span data-ttu-id="abc05-2179">Driving Licen</span><span class="sxs-lookup"><span data-stu-id="abc05-2179">Driving Licen</span></span> 
- <span data-ttu-id="abc05-2180">Driving License</span><span class="sxs-lookup"><span data-stu-id="abc05-2180">Driving License</span></span> 
- <span data-ttu-id="abc05-2181">Driving Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2181">Driving Licenses</span></span> 
- <span data-ttu-id="abc05-2182">Driving Licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2182">Driving Licence</span></span> 
- <span data-ttu-id="abc05-2183">Driving Licences</span><span class="sxs-lookup"><span data-stu-id="abc05-2183">Driving Licences</span></span>

#### <a name="keyword_german_drivers_license_collaborative"></a><span data-ttu-id="abc05-2184">Keyword_german_drivers_license_collaborative</span><span class="sxs-lookup"><span data-stu-id="abc05-2184">Keyword_german_drivers_license_collaborative</span></span>

- <span data-ttu-id="abc05-2185">Veiligheid-Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2185">Nr-Führerschein</span></span> 
- <span data-ttu-id="abc05-2186">Veiligheid-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2186">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2187">Veiligheid-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2187">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="abc05-2188">Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2188">No-Führerschein</span></span> 
- <span data-ttu-id="abc05-2189">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2189">No-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2190">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2190">No-Fuehrerschein</span></span> 
- <span data-ttu-id="abc05-2191">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2191">N-Führerschein</span></span> 
- <span data-ttu-id="abc05-2192">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2192">N-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2193">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2193">N-Fuehrerschein</span></span>
- <span data-ttu-id="abc05-2194">Veiligheid-Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2194">Nr-Führerschein</span></span> 
- <span data-ttu-id="abc05-2195">Veiligheid-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2195">Nr-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2196">Veiligheid-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2196">Nr-Fuehrerschein</span></span> 
- <span data-ttu-id="abc05-2197">Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2197">No-Führerschein</span></span> 
- <span data-ttu-id="abc05-2198">Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2198">No-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2199">Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2199">No-Fuehrerschein</span></span> 
- <span data-ttu-id="abc05-2200">N-Führerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2200">N-Führerschein</span></span> 
- <span data-ttu-id="abc05-2201">N-Fuhrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2201">N-Fuhrerschein</span></span> 
- <span data-ttu-id="abc05-2202">N-Fuehrerschein</span><span class="sxs-lookup"><span data-stu-id="abc05-2202">N-Fuehrerschein</span></span> 

#### <a name="keyword_german_drivers_license"></a><span data-ttu-id="abc05-2203">Keyword_german_drivers_license</span><span class="sxs-lookup"><span data-stu-id="abc05-2203">Keyword_german_drivers_license</span></span>

- <span data-ttu-id="abc05-2204">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-2204">ausstellungsdatum</span></span>
- <span data-ttu-id="abc05-2205">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="abc05-2205">ausstellungsort</span></span>
- <span data-ttu-id="abc05-2206">ausstellende behöde</span><span class="sxs-lookup"><span data-stu-id="abc05-2206">ausstellende behöde</span></span>
- <span data-ttu-id="abc05-2207">ausstellende behorde</span><span class="sxs-lookup"><span data-stu-id="abc05-2207">ausstellende behorde</span></span>
- <span data-ttu-id="abc05-2208">ausstellende behoerde</span><span class="sxs-lookup"><span data-stu-id="abc05-2208">ausstellende behoerde</span></span>
   
## <a name="german-passport-number"></a><span data-ttu-id="abc05-2209">독일 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2209">German Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2210">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2210">Format</span></span>

<span data-ttu-id="abc05-2211">10자리 숫자 또는 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2211">10 digits or letters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2212">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2212">Pattern</span></span>

<span data-ttu-id="abc05-2213">패턴에는 다음이 모두 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2213">Pattern must include all of the following:</span></span>
- <span data-ttu-id="abc05-2214">첫 번째 문자는 숫자 또는 (C, F, G, H, J, K) 집합의 문자임</span><span class="sxs-lookup"><span data-stu-id="abc05-2214">First character is a digit or a letter from this set (C, F, G, H, J, K)</span></span> 
- <span data-ttu-id="abc05-2215">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2215">Three digits</span></span> 
- <span data-ttu-id="abc05-2216">5자리 숫자 또는 (C, -H, J-N, P, R, T, V-Z) 집합의 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2216">Five digits or letters from this set (C, -H, J-N, P, R, T, V-Z)</span></span> 
- <span data-ttu-id="abc05-2217">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2217">A digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2218">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2218">Checksum</span></span>

<span data-ttu-id="abc05-2219">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2219">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2220">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2220">Definition</span></span>

<span data-ttu-id="abc05-2221">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2221">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2222">Func_german_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2222">The function Func_german_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2223">5개의 키워드 목록 중에 포함된 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2223">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="abc05-2224">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2224">The checksum passes.</span></span>

<span data-ttu-id="abc05-2225">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2225">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2226">Func_german_passport_data 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2226">The function Func_german_passport_data finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2227">5개의 키워드 목록 중에 포함된 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2227">A keyword from any of the five keyword lists is found.</span></span>
- <span data-ttu-id="abc05-2228">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2228">The checksum passes.</span></span>

```xml
<!-- German Passport Number -->
<Entity id="2e3da144-d42b-47ed-b123-fbf78604e52c" patternsProximity="300" recommendedConfidence="75">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_german_passport" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
  <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_german_passport_data" />
        <Any minMatches="1">
          <Match idRef="Keyword_german_passport" />
          <Match idRef="Keyword_german_passport_collaborative" />
          <Match idRef="Keyword_german_passport_number" />
          <Match idRef="Keyword_german_passport1" />
          <Match idRef="Keyword_german_passport2" />
        </Any>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2229">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2229">Keywords</span></span>

#### <a name="keyword_german_passport"></a><span data-ttu-id="abc05-2230">Keyword_german_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-2230">Keyword_german_passport</span></span>

- <span data-ttu-id="abc05-2231">reisepass</span><span class="sxs-lookup"><span data-stu-id="abc05-2231">reisepass</span></span>
- <span data-ttu-id="abc05-2232">reisepasse</span><span class="sxs-lookup"><span data-stu-id="abc05-2232">reisepasse</span></span>
- <span data-ttu-id="abc05-2233">reisepassnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2233">reisepassnummer</span></span>
- <span data-ttu-id="abc05-2234">여권</span><span class="sxs-lookup"><span data-stu-id="abc05-2234">passport</span></span>
- <span data-ttu-id="abc05-2235">passports</span><span class="sxs-lookup"><span data-stu-id="abc05-2235">passports</span></span>

#### <a name="keyword_german_passport_collaborative"></a><span data-ttu-id="abc05-2236">Keyword_german_passport_collaborative</span><span class="sxs-lookup"><span data-stu-id="abc05-2236">Keyword_german_passport_collaborative</span></span>

- <span data-ttu-id="abc05-2237">ge삼 부, tsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-2237">geburtsdatum</span></span>
- <span data-ttu-id="abc05-2238">ausstellungsdatum</span><span class="sxs-lookup"><span data-stu-id="abc05-2238">ausstellungsdatum</span></span>
- <span data-ttu-id="abc05-2239">ausstellungsort</span><span class="sxs-lookup"><span data-stu-id="abc05-2239">ausstellungsort</span></span>

#### <a name="keyword_german_passport_number"></a><span data-ttu-id="abc05-2240">Keyword_german_passport_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2240">Keyword_german_passport_number</span></span>

<span data-ttu-id="abc05-2241">Reisepass Veiligheid-Reisepass</span><span class="sxs-lookup"><span data-stu-id="abc05-2241">No-Reisepass Nr-Reisepass</span></span>

#### <a name="keyword_german_passport1"></a><span data-ttu-id="abc05-2242">Keyword_german_passport1</span><span class="sxs-lookup"><span data-stu-id="abc05-2242">Keyword_german_passport1</span></span>

<span data-ttu-id="abc05-2243">Reisepass-Veiligheid</span><span class="sxs-lookup"><span data-stu-id="abc05-2243">Reisepass-Nr</span></span>

#### <a name="keyword_german_passport2"></a><span data-ttu-id="abc05-2244">Keyword_german_passport2</span><span class="sxs-lookup"><span data-stu-id="abc05-2244">Keyword_german_passport2</span></span>

<span data-ttu-id="abc05-2245">bnationalit</span><span class="sxs-lookup"><span data-stu-id="abc05-2245">bnationalit.t</span></span>
   
## <a name="germany-identity-card-number"></a><span data-ttu-id="abc05-2246">독일 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2246">Germany Identity Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2247">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2247">Format</span></span>

<span data-ttu-id="abc05-2248">2010 년 11 월 1 일 이후: 9 개 문자 및 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2248">Since 1 November 2010: Nine letters and digits</span></span>

<span data-ttu-id="abc05-2249">1 월 1987 년 10 월 31 일 (2010:10 자리 숫자)</span><span class="sxs-lookup"><span data-stu-id="abc05-2249">From 1 April 1987 until 31 October 2010: 10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2250">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2250">Pattern</span></span>

<span data-ttu-id="abc05-2251">2010년 11월 1일 이후:</span><span class="sxs-lookup"><span data-stu-id="abc05-2251">Since 1 November 2010:</span></span>
- <span data-ttu-id="abc05-2252">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2252">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2253">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2253">Eight digits</span></span>

<span data-ttu-id="abc05-2254">1 년 4 월 1987 일 ~ 10 2010 월 31 일까 지:</span><span class="sxs-lookup"><span data-stu-id="abc05-2254">From 1 April 1987 until 31 October 2010:</span></span>
- <span data-ttu-id="abc05-2255">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2255">10 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2256">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2256">Checksum</span></span>

<span data-ttu-id="abc05-2257">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2257">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2258">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2258">Definition</span></span>

<span data-ttu-id="abc05-2259">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2259">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2260">정규식 Regex_germany_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2260">The regular expression Regex_germany_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2261">Keyword_germany_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2261">A keyword from Keyword_germany_id_card is found.</span></span>

```xml
<!-- Germany Identity Card Number -->
<Entity id="e577372f-c42e-47a0-9d85-bebed1c237d4" recommendedConfidence="65" patternsProximity="300">
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Regex_germany_id_card"/>
     <Match idRef="Keyword_germany_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2262">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2262">Keywords</span></span>

#### <a name="keyword_germany_id_card"></a><span data-ttu-id="abc05-2263">Keyword_germany_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-2263">Keyword_germany_id_card</span></span>

- <span data-ttu-id="abc05-2264">Identity Card</span><span class="sxs-lookup"><span data-stu-id="abc05-2264">Identity Card</span></span>
- <span data-ttu-id="abc05-2265">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2265">ID</span></span>
- <span data-ttu-id="abc05-2266">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-2266">Identification</span></span>
- <span data-ttu-id="abc05-2267">Personalausweis</span><span class="sxs-lookup"><span data-stu-id="abc05-2267">Personalausweis</span></span>
- <span data-ttu-id="abc05-2268">Identifizierungsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2268">Identifizierungsnummer</span></span>
- <span data-ttu-id="abc05-2269">Ausweis</span><span class="sxs-lookup"><span data-stu-id="abc05-2269">Ausweis</span></span>
- <span data-ttu-id="abc05-2270">Identifikation</span><span class="sxs-lookup"><span data-stu-id="abc05-2270">Identifikation</span></span>
   
## <a name="greece-national-id-card"></a><span data-ttu-id="abc05-2271">그리스 국가 ID 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2271">Greece National ID Card</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2272">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2272">Format</span></span>

<span data-ttu-id="abc05-2273">7-8자리 문자 및 숫자와 대시의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-2273">Combination of 7-8 letters and numbers plus a dash</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2274">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2274">Pattern</span></span>

<span data-ttu-id="abc05-2275">7자리 문자 및 숫자(이전 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-2275">Seven letters and numbers (old format):</span></span>
- <span data-ttu-id="abc05-2276">1개 문자(그리스어 알파벳의 임의 문자) </span><span class="sxs-lookup"><span data-stu-id="abc05-2276">One letter (any letter of the Greek alphabet)</span></span> 
- <span data-ttu-id="abc05-2277">대시 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-2277">A dash</span></span> 
- <span data-ttu-id="abc05-2278">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2278">Six digits</span></span>

<span data-ttu-id="abc05-2279">8자리 문자와 숫자(새로운 형식):</span><span class="sxs-lookup"><span data-stu-id="abc05-2279">Eight letters and numbers (new format):</span></span>
- <span data-ttu-id="abc05-2280">그리스어 및 라틴어 알파벳 둘 다에 해당 대문자가 포함된 2개 문자(ABEZHIKMNOPTYX) </span><span class="sxs-lookup"><span data-stu-id="abc05-2280">Two letters whose uppercase character occurs in both the Greek and Latin alphabets (ABEZHIKMNOPTYX)</span></span> 
- <span data-ttu-id="abc05-2281">대시 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-2281">A dash</span></span> 
- <span data-ttu-id="abc05-2282">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2282">Six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2283">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2283">Checksum</span></span>

<span data-ttu-id="abc05-2284">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2284">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2285">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2285">Definition</span></span>

<span data-ttu-id="abc05-2286">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2286">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2287">정규식 Regex_greece_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2287">The regular expression Regex_greece_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2288">Keyword_greece_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2288">A keyword from Keyword_greece_id_card is found.</span></span>

```xml
<!-- Greece National ID Card -->
<Entity id="82568215-1da1-46d3-874a-d2294d81b5ac" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_greece_id_card"/>
     <Match idRef="Keyword_greece_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2289">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2289">Keywords</span></span>

#### <a name="keyword_greece_id_card"></a><span data-ttu-id="abc05-2290">Keyword_greece_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-2290">Keyword_greece_id_card</span></span>

- <span data-ttu-id="abc05-2291">Greek identity Card</span><span class="sxs-lookup"><span data-stu-id="abc05-2291">Greek identity Card</span></span>
- <span data-ttu-id="abc05-2292">Tautotita</span><span class="sxs-lookup"><span data-stu-id="abc05-2292">Tautotita</span></span>
- <span data-ttu-id="abc05-2293">Δελτίο αστυνομικής ταυτότητας</span><span class="sxs-lookup"><span data-stu-id="abc05-2293">Δελτίο αστυνομικής ταυτότητας</span></span>
- <span data-ttu-id="abc05-2294">Ταυτότητα</span><span class="sxs-lookup"><span data-stu-id="abc05-2294">Ταυτότητα</span></span>
   
## <a name="hong-kong-identity-card-hkid-number"></a><span data-ttu-id="abc05-2295">HKID(홍콩 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2295">Hong Kong Identity Card (HKID) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2296">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2296">Format</span></span>

<span data-ttu-id="abc05-2297">8-9자리 문자 및 숫자와 마지막 문자를 선택적 괄호로 묶어서 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-2297">Combination of 8-9 letters and numbers plus optional parentheses around the final character</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2298">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2298">Pattern</span></span>

<span data-ttu-id="abc05-2299">8-9자리 문자 조합:</span><span class="sxs-lookup"><span data-stu-id="abc05-2299">Combination of 8-9 letters:</span></span>
- <span data-ttu-id="abc05-2300">1-2개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2300">1-2 letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2301">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2301">Six digits</span></span> 
- <span data-ttu-id="abc05-2302">검사 숫자에 해당하고 선택적으로 괄호로 묶는 마지막 문자(임의 숫자 또는 문자 A)</span><span class="sxs-lookup"><span data-stu-id="abc05-2302">The final character (any digit or the letter A), which is the check digit and is optionally enclosed in parentheses.</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2303">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2303">Checksum</span></span>

<span data-ttu-id="abc05-2304">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2304">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2305">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2305">Definition</span></span>

<span data-ttu-id="abc05-2306">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2306">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2307">Func_hong_kong_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2307">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2308">Keyword_hong_kong_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2308">A keyword from Keyword_hong_kong_id_card is found.</span></span>
- <span data-ttu-id="abc05-2309">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2309">The checksum passes.</span></span>

<span data-ttu-id="abc05-2310">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2310">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2311">Func_hong_kong_id_card 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2311">The function Func_hong_kong_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2312">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2312">The checksum passes.</span></span>

```xml
<!-- Hong Kong Identity Card (HKID) number -->
<Entity id="e63c28a7-ad29-4c17-a41a-3d2a0b70fd9c" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_hong_kong_id_card"/>
     <Match idRef="Keyword_hong_kong_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_hong_kong_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2313">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2313">Keywords</span></span>

#### <a name="keyword_hong_kong_id_card"></a><span data-ttu-id="abc05-2314">Keyword_hong_kong_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-2314">Keyword_hong_kong_id_card</span></span>

- <span data-ttu-id="abc05-2315">홍콩 특별 식별자 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2315">hong kong identity card</span></span>
- <span data-ttu-id="abc05-2316">HKIDC</span><span class="sxs-lookup"><span data-stu-id="abc05-2316">HKIDC</span></span>
- <span data-ttu-id="abc05-2317">id card</span><span class="sxs-lookup"><span data-stu-id="abc05-2317">id card</span></span>
- <span data-ttu-id="abc05-2318">identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-2318">identity card</span></span>
- <span data-ttu-id="abc05-2319">zh-hk id 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2319">hk identity card</span></span>
- <span data-ttu-id="abc05-2320">홍콩 id</span><span class="sxs-lookup"><span data-stu-id="abc05-2320">hong kong id</span></span>
- <span data-ttu-id="abc05-2321">香港身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2321">香港身份證</span></span>
- <span data-ttu-id="abc05-2322">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2322">香港永久性居民身份證</span></span>
- <span data-ttu-id="abc05-2323">身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2323">身份證</span></span>
- <span data-ttu-id="abc05-2324">身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2324">身份証</span></span>
- <span data-ttu-id="abc05-2325">身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2325">身分證</span></span>
- <span data-ttu-id="abc05-2326">身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2326">身分証</span></span>
- <span data-ttu-id="abc05-2327">香港身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2327">香港身份証</span></span>
- <span data-ttu-id="abc05-2328">香港身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2328">香港身分證</span></span>
- <span data-ttu-id="abc05-2329">香港身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2329">香港身分証</span></span>
- <span data-ttu-id="abc05-2330">香港身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2330">香港身份證</span></span>
- <span data-ttu-id="abc05-2331">香港居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2331">香港居民身份證</span></span>
- <span data-ttu-id="abc05-2332">香港居民身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2332">香港居民身份証</span></span>
- <span data-ttu-id="abc05-2333">香港居民身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2333">香港居民身分證</span></span>
- <span data-ttu-id="abc05-2334">香港居民身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2334">香港居民身分証</span></span>
- <span data-ttu-id="abc05-2335">香港永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2335">香港永久性居民身份証</span></span>
- <span data-ttu-id="abc05-2336">香港永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2336">香港永久性居民身分證</span></span>
- <span data-ttu-id="abc05-2337">香港永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2337">香港永久性居民身分証</span></span>
- <span data-ttu-id="abc05-2338">香港永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2338">香港永久性居民身份證</span></span>
- <span data-ttu-id="abc05-2339">香港非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2339">香港非永久性居民身份證</span></span>
- <span data-ttu-id="abc05-2340">香港非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2340">香港非永久性居民身份証</span></span>
- <span data-ttu-id="abc05-2341">香港非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2341">香港非永久性居民身分證</span></span>
- <span data-ttu-id="abc05-2342">香港非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2342">香港非永久性居民身分証</span></span>
- <span data-ttu-id="abc05-2343">香港特別行政區永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2343">香港特別行政區永久性居民身份證</span></span>
- <span data-ttu-id="abc05-2344">香港特別行政區永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2344">香港特別行政區永久性居民身份証</span></span>
- <span data-ttu-id="abc05-2345">香港特別行政區永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2345">香港特別行政區永久性居民身分證</span></span>
- <span data-ttu-id="abc05-2346">香港特別行政區永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2346">香港特別行政區永久性居民身分証</span></span>
- <span data-ttu-id="abc05-2347">香港特別行政區非永久性居民身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-2347">香港特別行政區非永久性居民身份證</span></span>
- <span data-ttu-id="abc05-2348">香港特別行政區非永久性居民身份証</span><span class="sxs-lookup"><span data-stu-id="abc05-2348">香港特別行政區非永久性居民身份証</span></span>
- <span data-ttu-id="abc05-2349">香港特別行政區非永久性居民身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-2349">香港特別行政區非永久性居民身分證</span></span>
- <span data-ttu-id="abc05-2350">香港特別行政區非永久性居民身分証</span><span class="sxs-lookup"><span data-stu-id="abc05-2350">香港特別行政區非永久性居民身分証</span></span>
   
## <a name="india-permanent-account-number-pan"></a><span data-ttu-id="abc05-2351">인도 PAN(영구 계정 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-2351">India Permanent Account Number (PAN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2352">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2352">Format</span></span>

<span data-ttu-id="abc05-2353">10자리 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2353">10 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2354">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2354">Pattern</span></span>

<span data-ttu-id="abc05-2355">10자리 문자 또는 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2355">10 letters or digits:</span></span>
- <span data-ttu-id="abc05-2356">5개 문자(대/소문자 구분 안 함) </span><span class="sxs-lookup"><span data-stu-id="abc05-2356">Five letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2357">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2357">Four digits</span></span> 
- <span data-ttu-id="abc05-2358">알파벳 검사 숫자에 해당하는 문자 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-2358">A letter which is an alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2359">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2359">Checksum</span></span>

<span data-ttu-id="abc05-2360">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2360">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2361">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2361">Definition</span></span>

<span data-ttu-id="abc05-2362">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2362">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2363">정규식 Regex_india_permanent_account_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2363">The regular expression Regex_india_permanent_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2364">Keyword_india_permanent_account_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2364">A keyword from Keyword_india_permanent_account_number is found.</span></span>
- <span data-ttu-id="abc05-2365">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2365">The checksum passes.</span></span>

```xml
<!-- India Permanent Account Number -->
<Entity id="2602bfee-9bb0-47a5-a7a6-2bf3053e2804" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_india_permanent_account_number"/>
     <Match idRef="Keyword_india_permanent_account_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2366">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2366">Keywords</span></span>

#### <a name="keyword_india_permanent_account_number"></a><span data-ttu-id="abc05-2367">Keyword_india_permanent_account_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2367">Keyword_india_permanent_account_number</span></span>

- <span data-ttu-id="abc05-2368">Permanent Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2368">Permanent Account Number</span></span> 
- <span data-ttu-id="abc05-2369">확대</span><span class="sxs-lookup"><span data-stu-id="abc05-2369">PAN</span></span> 
   
## <a name="india-unique-identification-aadhaar-number"></a><span data-ttu-id="abc05-2370">인도 고유 ID(Aadhaar) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2370">India Unique Identification (Aadhaar) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2371">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2371">Format</span></span>

<span data-ttu-id="abc05-2372">선택적 공백 또는 대시를 포함하는 12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2372">12 digits containing optional spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2373">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2373">Pattern</span></span>

<span data-ttu-id="abc05-2374">12자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2374">12 digits:</span></span>
- <span data-ttu-id="abc05-2375">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2375">Four digits</span></span> 
- <span data-ttu-id="abc05-2376">선택적 공백 또는 대시 </span><span class="sxs-lookup"><span data-stu-id="abc05-2376">An optional space or dash</span></span> 
- <span data-ttu-id="abc05-2377">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2377">Four digits</span></span> 
- <span data-ttu-id="abc05-2378">선택적 공백 또는 대시 </span><span class="sxs-lookup"><span data-stu-id="abc05-2378">An optional space or dash</span></span> 
- <span data-ttu-id="abc05-2379">검사 숫자에 해당하는 마지막 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2379">The final digit which is the check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2380">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2380">Checksum</span></span>

<span data-ttu-id="abc05-2381">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2381">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2382">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2382">Definition</span></span>

<span data-ttu-id="abc05-2383">DLP 정책은 300 Func_india_aadhaar 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 85% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2383">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-2384">Keyword_india_aadhar에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2384">A keyword from Keyword_india_aadhar is found.</span></span>
<span data-ttu-id="abc05-2385">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2385">The checksum passes.</span></span>
<span data-ttu-id="abc05-2386">DLP 정책은 300 Func_india_aadhaar 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 75% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2386">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_india_aadhaar finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-2387">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2387">The checksum passes.</span></span>
```xml
<!-- India Unique Identification (Aadhaar) number -->
<Entity id="1ca46b29-76f5-4f46-9383-cfa15e91048f" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_india_aadhaar"/>
     <Match idRef="Keyword_india_aadhar"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_india_aadhaar"/>
  </Pattern>
</Entity>
```
### <a name="keywords"></a><span data-ttu-id="abc05-2388">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2388">Keywords</span></span>
   
#### <a name="keyword_india_aadhar"></a><span data-ttu-id="abc05-2389">Keyword_india_aadhar</span><span class="sxs-lookup"><span data-stu-id="abc05-2389">Keyword_india_aadhar</span></span>
- <span data-ttu-id="abc05-2390">Aadhar</span><span class="sxs-lookup"><span data-stu-id="abc05-2390">Aadhar</span></span>
- <span data-ttu-id="abc05-2391">Aadhaar</span><span class="sxs-lookup"><span data-stu-id="abc05-2391">Aadhaar</span></span>
- <span data-ttu-id="abc05-2392">UID</span><span class="sxs-lookup"><span data-stu-id="abc05-2392">UID</span></span>
- <span data-ttu-id="abc05-2393">आधार</span><span class="sxs-lookup"><span data-stu-id="abc05-2393">आधार</span></span>
   
## <a name="indonesia-identity-card-ktp-number"></a><span data-ttu-id="abc05-2394">인도네시아 ID 카드(KTP) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2394">Indonesia Identity Card (KTP) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2395">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2395">Format</span></span>

<span data-ttu-id="abc05-2396">선택적으로 마침표를 포함하는 16자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2396">16 digits containing optional periods</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2397">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2397">Pattern</span></span>

<span data-ttu-id="abc05-2398">16자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2398">16 digits:</span></span>
- <span data-ttu-id="abc05-2399">2자리 시/도 코드 </span><span class="sxs-lookup"><span data-stu-id="abc05-2399">Two-digit province code</span></span> 
- <span data-ttu-id="abc05-2400">마침표(옵션) </span><span class="sxs-lookup"><span data-stu-id="abc05-2400">A period (optional)</span></span> 
- <span data-ttu-id="abc05-2401">2자리 지역 또는 구/군/시 코드 </span><span class="sxs-lookup"><span data-stu-id="abc05-2401">Two-digit regency or city code</span></span> 
- <span data-ttu-id="abc05-2402">2자리 소구역 코드 </span><span class="sxs-lookup"><span data-stu-id="abc05-2402">Two-digit subdistrict code</span></span> 
- <span data-ttu-id="abc05-2403">마침표(옵션) </span><span class="sxs-lookup"><span data-stu-id="abc05-2403">A period (optional)</span></span> 
- <span data-ttu-id="abc05-2404">생년월일에 해당하는 DDMMYY 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-2404">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="abc05-2405">마침표(옵션) </span><span class="sxs-lookup"><span data-stu-id="abc05-2405">A period (optional)</span></span> 
- <span data-ttu-id="abc05-2406">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2406">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2407">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2407">Checksum</span></span>

<span data-ttu-id="abc05-2408">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2408">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2409">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2409">Definition</span></span>

<span data-ttu-id="abc05-2410">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2410">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2411">정규식 Regex_indonesia_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2411">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2412">Keyword_indonesia_id_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2412">A keyword from Keyword_indonesia_id_card is found.</span></span>

<span data-ttu-id="abc05-2413">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2413">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2414">정규식 Regex_indonesia_id_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2414">The regular expression Regex_indonesia_id_card finds content that matches the pattern.</span></span>

```xml
<!-- Indonesia Identity Card (KTP) Number -->
<Entity id="da68fdb0-f383-4981-8c86-82689d3b7d55" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_indonesia_id_card"/>
     <Match idRef="Keyword_indonesia_id_card"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_indonesia_id_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2415">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2415">Keywords</span></span>
   
#### <a name="keyword_indonesia_id_card"></a><span data-ttu-id="abc05-2416">Keyword_indonesia_id_card</span><span class="sxs-lookup"><span data-stu-id="abc05-2416">Keyword_indonesia_id_card</span></span>

- <span data-ttu-id="abc05-2417">KTP</span><span class="sxs-lookup"><span data-stu-id="abc05-2417">KTP</span></span>
- <span data-ttu-id="abc05-2418">Kartu Tanda Penduduk</span><span class="sxs-lookup"><span data-stu-id="abc05-2418">Kartu Tanda Penduduk</span></span> 
- <span data-ttu-id="abc05-2419">Nomor Induk Kependudukan</span><span class="sxs-lookup"><span data-stu-id="abc05-2419">Nomor Induk Kependudukan</span></span> 
   
## <a name="international-banking-account-number-iban"></a><span data-ttu-id="abc05-2420">IBAN(국제 은행 계좌 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-2420">International Banking Account Number (IBAN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2421">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2421">Format</span></span>

<span data-ttu-id="abc05-2422">국가 코드 (두 문자) + 검사 숫자 (2 자리 숫자)와 bban 숫자 (최대 30 자)</span><span class="sxs-lookup"><span data-stu-id="abc05-2422">Country code (two letters) plus check digits (two digits) plus bban number (up to 30 characters)</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2423">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2423">Pattern</span></span>

<span data-ttu-id="abc05-2424">패턴에는 다음이 모두 포함되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2424">Pattern must include all of the following:</span></span>

- <span data-ttu-id="abc05-2425">두 글자로 된 국가 코드</span><span class="sxs-lookup"><span data-stu-id="abc05-2425">Two-letter country code</span></span>
- <span data-ttu-id="abc05-2426">두 개의 검사 숫자 (선택적 공백)</span><span class="sxs-lookup"><span data-stu-id="abc05-2426">Two check digits (followed by an optional space)</span></span> 
- <span data-ttu-id="abc05-2427">1-7 개 문자 또는 숫자의 그룹 (공백으로 구분 가능)</span><span class="sxs-lookup"><span data-stu-id="abc05-2427">1-7 groups of four letters or digits (can be separated by spaces)</span></span>
- <span data-ttu-id="abc05-2428">1-3 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2428">1-3 letters or digits</span></span>

<span data-ttu-id="abc05-2429">각 국가의 형식은 약간 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2429">The format for each country is slightly different.</span></span> <span data-ttu-id="abc05-2430">IBAN 중요 한 정보 유형은 다음과 같은 60 국가를 포함 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2430">The IBAN sensitive information type covers these 60 countries:</span></span>

<span data-ttu-id="abc05-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, kw, hu,, to,,, fr,,, i,,, ie, il, is,, l,, 5, 60, md, me, mk, e, mt, mu , nl-nl, no, pl, pt, ro, rs, sa, se, si,, sm, tn, tr, vg</span><span class="sxs-lookup"><span data-stu-id="abc05-2431">ad, ae, al, at, az, ba, be, bg, bh, ch, cr, cy, cz, de, dk, do, ee, es, fi, fo, fr, gb, ge, gi, gl, gr, hr, hu, ie, il, is, it, kw, kz, lb, li, lt, lu, lv, mc, md, me, mk, mr, mt, mu, nl, no, pl, pt, ro, rs, sa, se, si, sk, sm, tn, tr, vg</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2432">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2432">Checksum</span></span>

<span data-ttu-id="abc05-2433">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2433">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2434">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2434">Definition</span></span>

<span data-ttu-id="abc05-2435">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2435">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2436">Func_iban 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2436">The function Func_iban finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2437">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2437">The checksum passes.</span></span>

```xml
<Entity id="e7dc4711-11b7-4cb0-b88b-2c394a771f0e" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_iban" />
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2438">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2438">Keywords</span></span>

<span data-ttu-id="abc05-2439">없음</span><span class="sxs-lookup"><span data-stu-id="abc05-2439">None</span></span>

   
## <a name="ip-address"></a><span data-ttu-id="abc05-2440">IP 주소</span><span class="sxs-lookup"><span data-stu-id="abc05-2440">IP Address</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2441">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2441">Format</span></span>

#### <a name="ipv4"></a><span data-ttu-id="abc05-2442">IPv4</span><span class="sxs-lookup"><span data-stu-id="abc05-2442">IPv4:</span></span>
<span data-ttu-id="abc05-2443">IPv4 주소의 서식 있는 버전(마침표 있음) 및 서식 없는 버전(마침표 없음)으로 구성된 복잡한 패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2443">Complex pattern which accounts for formatted (periods) and unformatted (no periods) versions of the IPv4 addresses</span></span>

#### <a name="ipv6"></a><span data-ttu-id="abc05-2444">IPv6</span><span class="sxs-lookup"><span data-stu-id="abc05-2444">IPv6:</span></span>
<span data-ttu-id="abc05-2445">서식 있는(콜론 포함) IPv6 번호로 구성된 복잡한 패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2445">Complex pattern which accounts for formatted IPv6 numbers (which include colons)</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2446">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2446">Pattern</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2447">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2447">Checksum</span></span>

<span data-ttu-id="abc05-2448">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2448">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2449">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2449">Definition</span></span>

<span data-ttu-id="abc05-2450">IPv6의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2450">For IPv6, a DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2451">Regex_ipv6_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2451">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2452">Keyword_ipaddress의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2452">No keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="abc05-2453">IPv4의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2453">For IPv4, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2454">Regex_ipv4_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2454">The regular expression Regex_ipv4_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2455">Keyword_ipaddress의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2455">A keyword from Keyword_ipaddress is found.</span></span>

<span data-ttu-id="abc05-2456">IPv6의 경우 DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 95% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2456">For IPv6, a DLP policy is 95% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2457">Regex_ipv6_address 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2457">The regular expression Regex_ipv6_address finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2458">Keyword_ipaddress의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2458">No keyword from Keyword_ipaddress is found.</span></span>

```xml
    <!-- IP Address -->
    <Entity id="1daa4ad5-e2dd-4ca4-a788-54722c09efb2" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv4_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="95">
        <IdMatch idRef="Regex_ipv6_address" />
        <Any minMatches="1">
          <Match idRef="Keyword_ipaddress" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2459">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2459">Keywords</span></span>

#### <a name="keyword_ipaddress"></a><span data-ttu-id="abc05-2460">Keyword_ipaddress</span><span class="sxs-lookup"><span data-stu-id="abc05-2460">Keyword_ipaddress</span></span>

- <span data-ttu-id="abc05-2461">IP(이 키워드는 대/소문자를 구분함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2461">IP (this keyword is case sensitive)</span></span>
- <span data-ttu-id="abc05-2462">ip address</span><span class="sxs-lookup"><span data-stu-id="abc05-2462">ip address</span></span> 
- <span data-ttu-id="abc05-2463">ip addresses</span><span class="sxs-lookup"><span data-stu-id="abc05-2463">ip addresses</span></span>
- <span data-ttu-id="abc05-2464">internet protocol</span><span class="sxs-lookup"><span data-stu-id="abc05-2464">internet protocol</span></span>
- <span data-ttu-id="abc05-2465">IP-כתובת ה</span><span class="sxs-lookup"><span data-stu-id="abc05-2465">IP-כתובת ה</span></span> 
   
## <a name="international-classification-of-diseases-icd-10-cm"></a><span data-ttu-id="abc05-2466">Diseases의 국제 분류 (ICD-10-CM)</span><span class="sxs-lookup"><span data-stu-id="abc05-2466">International Classification of Diseases (ICD-10-CM)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2467">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2467">Format</span></span>

<span data-ttu-id="abc05-2468">사전</span><span class="sxs-lookup"><span data-stu-id="abc05-2468">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2469">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2469">Pattern</span></span>

<span data-ttu-id="abc05-2470">Keyword</span><span class="sxs-lookup"><span data-stu-id="abc05-2470">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2471">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2471">Checksum</span></span>

<span data-ttu-id="abc05-2472">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2472">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2473">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2473">Definition</span></span>

<span data-ttu-id="abc05-2474">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2474">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2475">Dictionary_icd_10_updated에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2475">A keyword from Dictionary_icd_10_updated is found.</span></span>
- <span data-ttu-id="abc05-2476">Dictionary_icd_10_codes에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2476">A keyword from Dictionary_icd_10_codes is found.</span></span>

<span data-ttu-id="abc05-2477">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2477">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2478">업데이트 된 Dictionary_icd_10_ 키워드를 찾았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2478">A keyword from Dictionary_icd_10_ updated is found.</span></span>

```xml
      <!-- ICD-10 CM -->
      <Entity id="3356946c-6bb7-449b-b253-6ffa419c0ce7" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_10_updated" />
          <Match idRef="Dictionary_icd_10_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_10_updated" />
        </Pattern>

```

<span data-ttu-id="abc05-2479">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2479">Keywords</span></span>

<span data-ttu-id="abc05-2480">[Diseases의 국제 분류, 10 번째 개정판, 임상 수정 (icd-10CM)](https://go.microsoft.com/fwlink/?linkid=852604)을 기반으로 하는 Dictionary_icd_10_updated 키워드 사전의 모든 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2480">Any term from the Dictionary_icd_10_updated keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="abc05-2481">이 유형은 보험 코드가 아니라 용어에 대해서만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2481">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="abc05-2482">[Diseases의 국제 분류, 10 번째 개정판, 임상 수정 (icd-10CM)](https://go.microsoft.com/fwlink/?linkid=852604)을 기반으로 하는 Dictionary_icd_10_codes 키워드 사전의 모든 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2482">Any term from the Dictionary_icd_10_codes keyword dictionary, which is based on the [International Classification of Diseases, Tenth Revision, Clinical Modification (ICD-10-CM)](https://go.microsoft.com/fwlink/?linkid=852604).</span></span> <span data-ttu-id="abc05-2483">이 유형은 설명에 해당 하는 보험 코드 에서만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2483">This type looks only for insurance codes, not the description.</span></span>

## <a name="international-classification-of-diseases-icd-9-cm"></a><span data-ttu-id="abc05-2484">Diseases의 국제 분류 (ICD-9-CM)</span><span class="sxs-lookup"><span data-stu-id="abc05-2484">International Classification of Diseases (ICD-9-CM)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2485">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2485">Format</span></span>

<span data-ttu-id="abc05-2486">사전</span><span class="sxs-lookup"><span data-stu-id="abc05-2486">Dictionary</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2487">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2487">Pattern</span></span>

<span data-ttu-id="abc05-2488">Keyword</span><span class="sxs-lookup"><span data-stu-id="abc05-2488">Keyword</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2489">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2489">Checksum</span></span>

<span data-ttu-id="abc05-2490">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2490">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2491">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2491">Definition</span></span>

<span data-ttu-id="abc05-2492">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2492">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2493">Dictionary_icd_9_updated에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2493">A keyword from Dictionary_icd_9_updated is found.</span></span>
- <span data-ttu-id="abc05-2494">Dictionary_icd_9_codes에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2494">A keyword from Dictionary_icd_9_codes is found.</span></span>

<span data-ttu-id="abc05-2495">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2495">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2496">Dictionary_icd_9_updated에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2496">A keyword from Dictionary_icd_9_updated is found.</span></span>

```xml
    <Entity id="fa3f9c74-ee07-4c52-b5f2-085d6b2c0ec4" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
          <IdMatch idRef="Dictionary_icd_9_updated" />
          <Match idRef="Dictionary_icd_9_codes" />
        </Pattern>
        <Pattern confidenceLevel="75">
          <IdMatch idRef="Dictionary_icd_9_updated" />
        </Pattern>
      </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2497">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2497">Keywords</span></span>

<span data-ttu-id="abc05-2498">[Diseases, 아홉 번째 Revision, 임상 수정 (icd-9CM)의 국가별 분류](https://go.microsoft.com/fwlink/?linkid=852605)를 기반으로 하는 Dictionary_icd_9_updated 키워드 사전의 모든 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2498">Any term from the Dictionary_icd_9_updated keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="abc05-2499">이 유형은 보험 코드가 아니라 용어에 대해서만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2499">This type looks only for the term, not the insurance codes.</span></span>

<span data-ttu-id="abc05-2500">[Diseases, 아홉 번째 Revision, 임상 수정 (icd-9CM)의 국가별 분류](https://go.microsoft.com/fwlink/?linkid=852605)를 기반으로 하는 Dictionary_icd_9_codes 키워드 사전의 모든 용어입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2500">Any term from the Dictionary_icd_9_codes keyword dictionary, which is based on the [International Classification of Diseases,Ninth Revision, Clinical Modification (ICD-9-CM)](https://go.microsoft.com/fwlink/?linkid=852605).</span></span> <span data-ttu-id="abc05-2501">이 유형은 설명에 해당 하는 보험 코드 에서만 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2501">This type looks only for insurance codes, not the description.</span></span>

## <a name="ireland-personal-public-service-pps-number"></a><span data-ttu-id="abc05-2502">아일랜드 PPS(개인 공공 서비스) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2502">Ireland Personal Public Service (PPS) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2503">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2503">Format</span></span>

<span data-ttu-id="abc05-2504">이전 형식 (31 년 12 월 2012 일까지):</span><span class="sxs-lookup"><span data-stu-id="abc05-2504">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="abc05-2505">7자리 숫자와 1-2개 문자 </span><span class="sxs-lookup"><span data-stu-id="abc05-2505">Seven digits followed by 1-2 letters</span></span> 

<span data-ttu-id="abc05-2506">새 형식 (1 년 1 월 2013 및 이후):</span><span class="sxs-lookup"><span data-stu-id="abc05-2506">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="abc05-2507">7자리 숫자와 2개 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2507">Seven digits followed by two letters</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2508">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2508">Pattern</span></span>

<span data-ttu-id="abc05-2509">이전 형식 (31 년 12 월 2012 일까지):</span><span class="sxs-lookup"><span data-stu-id="abc05-2509">Old format (until 31 Dec 2012):</span></span>
- <span data-ttu-id="abc05-2510">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2510">Seven digits</span></span> 
- <span data-ttu-id="abc05-2511">1-2개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2511">1-2 letters (not case sensitive)</span></span> 

<span data-ttu-id="abc05-2512">새 형식 (1 년 1 월 2013 및 이후):</span><span class="sxs-lookup"><span data-stu-id="abc05-2512">New format (1 Jan 2013 and after):</span></span>
- <span data-ttu-id="abc05-2513">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2513">Seven digits</span></span> 
- <span data-ttu-id="abc05-2514">알파벳 검사 숫자에 해당하는 문자 1개(대/소문자 구분 안 함) </span><span class="sxs-lookup"><span data-stu-id="abc05-2514">A letter (not case sensitive) which is an alphabetic check digit</span></span> 
- <span data-ttu-id="abc05-2515">문자 "A" 또는 "H"(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2515">The letter "A" or "H" (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2516">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2516">Checksum</span></span>

<span data-ttu-id="abc05-2517">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2517">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2518">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2518">Definition</span></span>

<span data-ttu-id="abc05-2519">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2520">Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2520">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2521">다음 중 하나가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2521">One of the following is true:</span></span>
    - <span data-ttu-id="abc05-2522">Keyword_ireland_pps에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2522">A keyword from Keyword_ireland_pps is found.</span></span>
    - <span data-ttu-id="abc05-2523">Func_eu_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2523">The function Func_eu_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-2524">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2524">The checksum passes.</span></span>

<span data-ttu-id="abc05-2525">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2525">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2526">Func_ireland_pps 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2526">The function Func_ireland_pps finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2527">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2527">The checksum passes.</span></span>

```xml
<!-- Ireland Personal Public Service (PPS) Number -->
<Entity id="1cdb674d-c19a-4fcf-9f4b-7f56cc87345a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_ireland_pps"/>
     <Any minMatches="1">
  <Match idRef="Keyword_ireland_pps"/>
  <Match idRef="Func_eu_date"/>
     </Any>
  </Pattern>
  <Pattern confidenceLevel="65">
     <IdMatch idRef="Func_ireland_pps"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2528">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2528">Keywords</span></span>

#### <a name="keyword_ireland_pps"></a><span data-ttu-id="abc05-2529">Keyword_ireland_pps</span><span class="sxs-lookup"><span data-stu-id="abc05-2529">Keyword_ireland_pps</span></span>

- <span data-ttu-id="abc05-2530">Personal Public Service Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2530">Personal Public Service Number</span></span> 
- <span data-ttu-id="abc05-2531">PPS Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2531">PPS Number</span></span> 
- <span data-ttu-id="abc05-2532">PPS Num</span><span class="sxs-lookup"><span data-stu-id="abc05-2532">PPS Num</span></span> 
- <span data-ttu-id="abc05-2533">PPS No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2533">PPS No.</span></span> 
- <span data-ttu-id="abc05-2534">PPS #</span><span class="sxs-lookup"><span data-stu-id="abc05-2534">PPS #</span></span> 
- <span data-ttu-id="abc05-2535">.PPS #</span><span class="sxs-lookup"><span data-stu-id="abc05-2535">PPS#</span></span> 
- <span data-ttu-id="abc05-2536">PPSN</span><span class="sxs-lookup"><span data-stu-id="abc05-2536">PPSN</span></span> 
- <span data-ttu-id="abc05-2537">Public Services Card</span><span class="sxs-lookup"><span data-stu-id="abc05-2537">Public Services Card</span></span> 
- <span data-ttu-id="abc05-2538">Uimhir Phearsanta Seirbhíse Poiblí</span><span class="sxs-lookup"><span data-stu-id="abc05-2538">Uimhir Phearsanta Seirbhíse Poiblí</span></span> 
- <span data-ttu-id="abc05-2539">Uimh</span><span class="sxs-lookup"><span data-stu-id="abc05-2539">Uimh.</span></span> <span data-ttu-id="abc05-2540">PSP</span><span class="sxs-lookup"><span data-stu-id="abc05-2540">PSP</span></span> 
- <span data-ttu-id="abc05-2541">PSP</span><span class="sxs-lookup"><span data-stu-id="abc05-2541">PSP</span></span> 
   
## <a name="israel-bank-account-number"></a><span data-ttu-id="abc05-2542">이스라엘 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2542">Israel Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2543">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2543">Format</span></span>

<span data-ttu-id="abc05-2544">13자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2544">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2545">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2545">Pattern</span></span>

<span data-ttu-id="abc05-2546">서식이</span><span class="sxs-lookup"><span data-stu-id="abc05-2546">Formatted:</span></span>
- <span data-ttu-id="abc05-2547">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2547">Two digits</span></span> 
- <span data-ttu-id="abc05-2548">대시 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-2548">A dash</span></span> 
- <span data-ttu-id="abc05-2549">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2549">Three digits</span></span> 
- <span data-ttu-id="abc05-2550">대시 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-2550">A dash</span></span> 
- <span data-ttu-id="abc05-2551">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2551">Eight digits</span></span>

<span data-ttu-id="abc05-2552">서식</span><span class="sxs-lookup"><span data-stu-id="abc05-2552">Unformatted:</span></span>
- <span data-ttu-id="abc05-2553">13자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2553">13 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2554">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2554">Checksum</span></span>

<span data-ttu-id="abc05-2555">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2555">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2556">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2556">Definition</span></span>

<span data-ttu-id="abc05-2557">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2557">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2558">Regex_israel_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2558">The regular expression Regex_israel_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2559">Keyword_israel_bank_account_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2559">A keyword from Keyword_israel_bank_account_number is found.</span></span>

```xml
<!-- Israel Bank Account Number -->
<Entity id="7d08b2ff-a0b9-437f-957c-aeddbf9b2b25" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_israel_bank_account_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_israel_bank_account_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2560">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2560">Keywords</span></span>

#### <a name="keyword_israel_bank_account_number"></a><span data-ttu-id="abc05-2561">Keyword_israel_bank_account_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2561">Keyword_israel_bank_account_number</span></span>

- <span data-ttu-id="abc05-2562">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2562">Bank Account Number</span></span> 
- <span data-ttu-id="abc05-2563">Bank Account</span><span class="sxs-lookup"><span data-stu-id="abc05-2563">Bank Account</span></span> 
- <span data-ttu-id="abc05-2564">Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2564">Account Number</span></span> 
- <span data-ttu-id="abc05-2565">מספר חשבון בנק</span><span class="sxs-lookup"><span data-stu-id="abc05-2565">מספר חשבון בנק</span></span> 
   
## <a name="israel-national-id"></a><span data-ttu-id="abc05-2566">이스라엘 국가 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2566">Israel National ID</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2567">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2567">Format</span></span>

<span data-ttu-id="abc05-2568">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2568">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2569">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2569">Pattern</span></span>

<span data-ttu-id="abc05-2570">9자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2570">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2571">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2571">Checksum</span></span>

<span data-ttu-id="abc05-2572">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2572">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2573">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2573">Definition</span></span>

<span data-ttu-id="abc05-2574">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2574">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2575">Func_israeli_national_id_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2575">The function Func_israeli_national_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2576">Keyword_Israel_National_ID의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2576">A keyword from Keyword_Israel_National_ID is found.</span></span>
- <span data-ttu-id="abc05-2577">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2577">The checksum passes.</span></span>

```xml
<!-- Israel National ID Number -->
<Entity id="e05881f5-1db1-418c-89aa-a3ac5c5277ee" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_israeli_national_id_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_Israel_National_ID" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2578">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2578">Keywords</span></span>

#### <a name="keyword_israel_national_id"></a><span data-ttu-id="abc05-2579">Keyword_Israel_National_ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2579">Keyword_Israel_National_ID</span></span>

- <span data-ttu-id="abc05-2580">מספר זהות</span><span class="sxs-lookup"><span data-stu-id="abc05-2580">מספר זהות</span></span> 
- <span data-ttu-id="abc05-2581">National ID Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2581">National ID Number</span></span>
   
## <a name="italy-drivers-license-number"></a><span data-ttu-id="abc05-2582">이탈리아 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2582">Italy Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2583">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2583">Format</span></span>

<span data-ttu-id="abc05-2584">10개의 문자 및 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-2584">A combination of 10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2585">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2585">Pattern</span></span>

- <span data-ttu-id="abc05-2586">10개의 문자 및 숫자 조합:</span><span class="sxs-lookup"><span data-stu-id="abc05-2586">A combination of 10 letters and digits:</span></span>
- <span data-ttu-id="abc05-2587">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2587">One letter (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2588">문자 "A" 또는 "V"(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2588">The letter "A" or "V" (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-2589">7개 문자(대/소문자 구분 안 함), 숫자 또는 밑줄 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-2589">Seven letters (not case sensitive), digits, or the underscore character</span></span> 
- <span data-ttu-id="abc05-2590">1개 문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2590">One letter (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2591">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2591">Checksum</span></span>

<span data-ttu-id="abc05-2592">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2592">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2593">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2593">Definition</span></span>

<span data-ttu-id="abc05-2594">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2594">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2595">Regex_italy_drivers_license_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2595">The regular expression Regex_italy_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2596">Keyword_italy_drivers_license_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2596">A keyword from Keyword_italy_drivers_license_number is found.</span></span>

```xml
<!-- Italy Driver's license Number -->
<Entity id="97d6244f-9157-41bd-8e0c-9d669a5c4d71" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_italy_drivers_license_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_italy_drivers_license_number" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2597">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2597">Keywords</span></span>

#### <a name="keyword_italy_drivers_license_number"></a><span data-ttu-id="abc05-2598">Keyword_italy_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2598">Keyword_italy_drivers_license_number</span></span>

- <span data-ttu-id="abc05-2599">numero di patente di guida</span><span class="sxs-lookup"><span data-stu-id="abc05-2599">numero di patente di guida</span></span> 
- <span data-ttu-id="abc05-2600">patente di guida</span><span class="sxs-lookup"><span data-stu-id="abc05-2600">patente di guida</span></span> 
   
## <a name="japan-bank-account-number"></a><span data-ttu-id="abc05-2601">일본 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2601">Japan Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2602">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2602">Format</span></span>

<span data-ttu-id="abc05-2603">7 또는 8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2603">Seven or eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2604">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2604">Pattern</span></span>

<span data-ttu-id="abc05-2605">은행 계좌 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-2605">Bank account number:</span></span>
- <span data-ttu-id="abc05-2606">7 또는 8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2606">Seven or eight digits</span></span>
- <span data-ttu-id="abc05-2607">은행 계좌 지점 코드:</span><span class="sxs-lookup"><span data-stu-id="abc05-2607">Bank account branch code:</span></span>
- <span data-ttu-id="abc05-2608">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2608">Four digits</span></span> 
- <span data-ttu-id="abc05-2609">공백 또는 대시(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-2609">A space or dash (optional)</span></span> 
- <span data-ttu-id="abc05-2610">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2610">Three digits</span></span>

<span data-ttu-id="abc05-2611">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2611">Checksum</span></span>

<span data-ttu-id="abc05-2612">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2612">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2613">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2613">Definition</span></span>

<span data-ttu-id="abc05-2614">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2614">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2615">Func_jp_bank_account 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2615">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2616">Keyword_jp_bank_account의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2616">A keyword from Keyword_jp_bank_account is found.</span></span>
- <span data-ttu-id="abc05-2617">다음 중 하나가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2617">One of the following is true:</span></span>
- <span data-ttu-id="abc05-2618">Func_jp_bank_account_branch_code 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2618">The function Func_jp_bank_account_branch_code finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2619">Keyword_jp_bank_branch_code의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2619">A keyword from Keyword_jp_bank_branch_code is found.</span></span>

<span data-ttu-id="abc05-2620">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2620">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2621">Func_jp_bank_account 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2621">The function Func_jp_bank_account finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2622">Keyword_jp_bank_account의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2622">A keyword from Keyword_jp_bank_account is found.</span></span>

```xml
<!-- Japan Bank Account Number -->
<Entity id="d354f95b-96ee-4b80-80bc-4377312b55bc" patternsProximity="300" recommendedConfidence="75">
  <Version minEngineVersion="15.01.0131.000">
    <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_jp_bank_account" />
          <Match idRef="Keyword_jp_bank_account" />
          <Any minMatches="1">
            <Match idRef="Func_jp_bank_account_branch_code" />
            <Match idRef="Keyword_jp_bank_branch_code" />
          </Any>
      </Pattern>
  </Version>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_bank_account" />
        <Match idRef="Keyword_jp_bank_account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2623">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2623">Keywords</span></span>

#### <a name="keyword_jp_bank_account"></a><span data-ttu-id="abc05-2624">Keyword_jp_bank_account</span><span class="sxs-lookup"><span data-stu-id="abc05-2624">Keyword_jp_bank_account</span></span>

- <span data-ttu-id="abc05-2625">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2625">Checking Account Number</span></span> 
- <span data-ttu-id="abc05-2626">Checking Account</span><span class="sxs-lookup"><span data-stu-id="abc05-2626">Checking Account</span></span> 
- <span data-ttu-id="abc05-2627">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-2627">Checking Account #</span></span> 
- <span data-ttu-id="abc05-2628">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2628">Checking Acct Number</span></span> 
- <span data-ttu-id="abc05-2629">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-2629">Checking Acct #</span></span> 
- <span data-ttu-id="abc05-2630">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2630">Checking Acct No.</span></span> 
- <span data-ttu-id="abc05-2631">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2631">Checking Account No.</span></span> 
- <span data-ttu-id="abc05-2632">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2632">Bank Account Number</span></span> 
- <span data-ttu-id="abc05-2633">Bank Account</span><span class="sxs-lookup"><span data-stu-id="abc05-2633">Bank Account</span></span> 
- <span data-ttu-id="abc05-2634">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-2634">Bank Account #</span></span> 
- <span data-ttu-id="abc05-2635">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2635">Bank Acct Number</span></span> 
- <span data-ttu-id="abc05-2636">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-2636">Bank Acct #</span></span> 
- <span data-ttu-id="abc05-2637">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2637">Bank Acct No.</span></span> 
- <span data-ttu-id="abc05-2638">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2638">Bank Account No.</span></span> 
- <span data-ttu-id="abc05-2639">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2639">Savings Account Number</span></span> 
- <span data-ttu-id="abc05-2640">Savings Account</span><span class="sxs-lookup"><span data-stu-id="abc05-2640">Savings Account</span></span> 
- <span data-ttu-id="abc05-2641">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-2641">Savings Account #</span></span> 
- <span data-ttu-id="abc05-2642">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2642">Savings Acct Number</span></span> 
- <span data-ttu-id="abc05-2643">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-2643">Savings Acct #</span></span> 
- <span data-ttu-id="abc05-2644">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2644">Savings Acct No.</span></span> 
- <span data-ttu-id="abc05-2645">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2645">Savings Account No.</span></span> 
- <span data-ttu-id="abc05-2646">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2646">Debit Account Number</span></span> 
- <span data-ttu-id="abc05-2647">Debit Account</span><span class="sxs-lookup"><span data-stu-id="abc05-2647">Debit Account</span></span> 
- <span data-ttu-id="abc05-2648">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-2648">Debit Account #</span></span> 
- <span data-ttu-id="abc05-2649">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2649">Debit Acct Number</span></span> 
- <span data-ttu-id="abc05-2650">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-2650">Debit Acct #</span></span> 
- <span data-ttu-id="abc05-2651">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2651">Debit Acct No.</span></span> 
- <span data-ttu-id="abc05-2652">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2652">Debit Account No.</span></span> 
- <span data-ttu-id="abc05-2653">口座番号を当座預金口座の確認</span><span class="sxs-lookup"><span data-stu-id="abc05-2653">口座番号を当座預金口座の確認</span></span> 
- <span data-ttu-id="abc05-2654">#アカウントの確認 、 勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="abc05-2654">＃アカウントの確認、勘定番号の確認</span></span> 
- <span data-ttu-id="abc05-2655">#勘定の確認</span><span class="sxs-lookup"><span data-stu-id="abc05-2655">＃勘定の確認</span></span> 
- <span data-ttu-id="abc05-2656">勘定番号の確認</span><span class="sxs-lookup"><span data-stu-id="abc05-2656">勘定番号の確認</span></span> 
- <span data-ttu-id="abc05-2657">口座番号の確認</span><span class="sxs-lookup"><span data-stu-id="abc05-2657">口座番号の確認</span></span> 
- <span data-ttu-id="abc05-2658">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2658">銀行口座番号</span></span> 
- <span data-ttu-id="abc05-2659">銀行口座</span><span class="sxs-lookup"><span data-stu-id="abc05-2659">銀行口座</span></span> 
- <span data-ttu-id="abc05-2660">銀行口座＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2660">銀行口座＃</span></span> 
- <span data-ttu-id="abc05-2661">銀行の勘定番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2661">銀行の勘定番号</span></span> 
- <span data-ttu-id="abc05-2662">銀行のacct＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2662">銀行のacct＃</span></span> 
- <span data-ttu-id="abc05-2663">銀行の勘定いいえ</span><span class="sxs-lookup"><span data-stu-id="abc05-2663">銀行の勘定いいえ</span></span> 
- <span data-ttu-id="abc05-2664">銀行口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2664">銀行口座番号</span></span>
- <span data-ttu-id="abc05-2665">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2665">普通預金口座番号</span></span> 
- <span data-ttu-id="abc05-2666">預金口座</span><span class="sxs-lookup"><span data-stu-id="abc05-2666">預金口座</span></span> 
- <span data-ttu-id="abc05-2667">貯蓄口座＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2667">貯蓄口座＃</span></span> 
- <span data-ttu-id="abc05-2668">貯蓄勘定の数</span><span class="sxs-lookup"><span data-stu-id="abc05-2668">貯蓄勘定の数</span></span> 
- <span data-ttu-id="abc05-2669">貯蓄勘定＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2669">貯蓄勘定＃</span></span> 
- <span data-ttu-id="abc05-2670">貯蓄勘定番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2670">貯蓄勘定番号</span></span> 
- <span data-ttu-id="abc05-2671">普通預金口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2671">普通預金口座番号</span></span> 
- <span data-ttu-id="abc05-2672">引き落とし口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2672">引き落とし口座番号</span></span> 
- <span data-ttu-id="abc05-2673">口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2673">口座番号</span></span> 
- <span data-ttu-id="abc05-2674">口座番号＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2674">口座番号＃</span></span> 
- <span data-ttu-id="abc05-2675">デビットのacct番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2675">デビットのacct番号</span></span> 
- <span data-ttu-id="abc05-2676">デビット勘定＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2676">デビット勘定＃</span></span> 
- <span data-ttu-id="abc05-2677">デビットACCTの番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2677">デビットACCTの番号</span></span> 
- <span data-ttu-id="abc05-2678">デビット口座番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2678">デビット口座番号</span></span> 

#### <a name="keyword_jp_bank_branch_code"></a><span data-ttu-id="abc05-2679">Keyword_jp_bank_branch_code</span><span class="sxs-lookup"><span data-stu-id="abc05-2679">Keyword_jp_bank_branch_code</span></span>

<span data-ttu-id="abc05-2680">Otemachi</span><span class="sxs-lookup"><span data-stu-id="abc05-2680">Otemachi</span></span>

## <a name="japan-drivers-license-number"></a><span data-ttu-id="abc05-2681">일본 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2681">Japan Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2682">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2682">Format</span></span>

<span data-ttu-id="abc05-2683">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2683">12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2684">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2684">Pattern</span></span>

<span data-ttu-id="abc05-2685">12자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2685">12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2686">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2686">Checksum</span></span>

<span data-ttu-id="abc05-2687">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2687">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2688">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2688">Definition</span></span>

<span data-ttu-id="abc05-2689">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2689">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2690">Func_jp_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2690">The function Func_jp_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2691">Keyword_jp_drivers_license_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2691">A keyword from Keyword_jp_drivers_license_number is found.</span></span>

```xml
<!-- Japan Driver's License Number -->
<Entity id="c6011143-d087-451c-8313-7f6d4aed2270" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_drivers_license_number" />
        <Match idRef ="Keyword_jp_drivers_license_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2692">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2692">Keywords</span></span>

#### <a name="keyword_jp_drivers_license_number"></a><span data-ttu-id="abc05-2693">Keyword_jp_drivers_license_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2693">Keyword_jp_drivers_license_number</span></span>

- <span data-ttu-id="abc05-2694">dl #</span><span class="sxs-lookup"><span data-stu-id="abc05-2694">dl#</span></span> 
- <span data-ttu-id="abc05-2695">DL</span><span class="sxs-lookup"><span data-stu-id="abc05-2695">DL＃</span></span> 
- <span data-ttu-id="abc05-2696">된다 #</span><span class="sxs-lookup"><span data-stu-id="abc05-2696">dls#</span></span> 
- <span data-ttu-id="abc05-2697">된다</span><span class="sxs-lookup"><span data-stu-id="abc05-2697">DLS＃</span></span> 
- <span data-ttu-id="abc05-2698">driver license</span><span class="sxs-lookup"><span data-stu-id="abc05-2698">driver license</span></span> 
- <span data-ttu-id="abc05-2699">driver licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2699">driver licenses</span></span> 
- <span data-ttu-id="abc05-2700">drivers license</span><span class="sxs-lookup"><span data-stu-id="abc05-2700">drivers license</span></span> 
- <span data-ttu-id="abc05-2701">driver's license</span><span class="sxs-lookup"><span data-stu-id="abc05-2701">driver's license</span></span> 
- <span data-ttu-id="abc05-2702">drivers licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2702">drivers licenses</span></span> 
- <span data-ttu-id="abc05-2703">driver's licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-2703">driver's licenses</span></span> 
- <span data-ttu-id="abc05-2704">driving licence</span><span class="sxs-lookup"><span data-stu-id="abc05-2704">driving licence</span></span> 
- <span data-ttu-id="abc05-2705">lic #</span><span class="sxs-lookup"><span data-stu-id="abc05-2705">lic#</span></span> 
- <span data-ttu-id="abc05-2706">LIC</span><span class="sxs-lookup"><span data-stu-id="abc05-2706">LIC＃</span></span> 
- <span data-ttu-id="abc05-2707">driver'lics #</span><span class="sxs-lookup"><span data-stu-id="abc05-2707">lics#</span></span> 
- <span data-ttu-id="abc05-2708">state id</span><span class="sxs-lookup"><span data-stu-id="abc05-2708">state id</span></span> 
- <span data-ttu-id="abc05-2709">state identification</span><span class="sxs-lookup"><span data-stu-id="abc05-2709">state identification</span></span> 
- <span data-ttu-id="abc05-2710">state identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-2710">state identification number</span></span> 
- <span data-ttu-id="abc05-2711">低所得国＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2711">低所得国＃</span></span> 
- <span data-ttu-id="abc05-2712">免許証</span><span class="sxs-lookup"><span data-stu-id="abc05-2712">免許証</span></span> 
- <span data-ttu-id="abc05-2713">状態ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2713">状態ID</span></span>
- <span data-ttu-id="abc05-2714">状態の識別</span><span class="sxs-lookup"><span data-stu-id="abc05-2714">状態の識別</span></span> 
- <span data-ttu-id="abc05-2715">状態の識別番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2715">状態の識別番号</span></span> 
- <span data-ttu-id="abc05-2716">運転免許</span><span class="sxs-lookup"><span data-stu-id="abc05-2716">運転免許</span></span> 
- <span data-ttu-id="abc05-2717">運転免許証</span><span class="sxs-lookup"><span data-stu-id="abc05-2717">運転免許証</span></span> 
- <span data-ttu-id="abc05-2718">運転免許証番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2718">運転免許証番号</span></span> 
   
## <a name="japan-passport-number"></a><span data-ttu-id="abc05-2719">일본 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2719">Japan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2720">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2720">Format</span></span>

<span data-ttu-id="abc05-2721">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2721">Two letters followed by seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2722">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2722">Pattern</span></span>

<span data-ttu-id="abc05-2723">2개의 문자(대/소문자 구분 안 함)와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2723">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2724">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2724">Checksum</span></span>

<span data-ttu-id="abc05-2725">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2725">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2726">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2726">Definition</span></span>

<span data-ttu-id="abc05-2727">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2727">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2728">Func_jp_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2728">The function Func_jp_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2729">Keyword_jp_passport의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2729">A keyword from Keyword_jp_passport is found.</span></span>

```xml
<!-- Japan Passport Number -->
<Entity id="75177310-1a09-4613-bf6d-833aae3743f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_passport" />
        <Match idRef="Keyword_jp_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2730">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2730">Keywords</span></span>

#### <a name="keyword_jp_passport"></a><span data-ttu-id="abc05-2731">Keyword_jp_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-2731">Keyword_jp_passport</span></span>

- <span data-ttu-id="abc05-2732">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-2732">パスポート</span></span> 
- <span data-ttu-id="abc05-2733">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2733">パスポート番号</span></span> 
- <span data-ttu-id="abc05-2734">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-2734">パスポートのNum</span></span> 
- <span data-ttu-id="abc05-2735">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="abc05-2735">パスポート＃</span></span> 
   
## <a name="japan-resident-registration-number"></a><span data-ttu-id="abc05-2736">일본 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2736">Japan Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2737">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2737">Format</span></span>

<span data-ttu-id="abc05-2738">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2738">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2739">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2739">Pattern</span></span>

<span data-ttu-id="abc05-2740">11자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2740">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2741">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2741">Checksum</span></span>

<span data-ttu-id="abc05-2742">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2742">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2743">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2743">Definition</span></span>

<span data-ttu-id="abc05-2744">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2744">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2745">Func_jp_resident_registration_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2745">The function Func_jp_resident_registration_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2746">Keyword_jp_resident_registration_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2746">A keyword from Keyword_jp_resident_registration_number is found.</span></span>

```xml
<!-- Japan Resident Registration Number -->
<Entity id="01c1209b-6389-4faf-a5f8-3f7e13899652" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_resident_registration_number" />
        <Match idRef ="Keyword_jp_resident_registration_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2747">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2747">Keywords</span></span>

#### <a name="keyword_jp_resident_registration_number"></a><span data-ttu-id="abc05-2748">Keyword_jp_resident_registration_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2748">Keyword_jp_resident_registration_number</span></span>

- <span data-ttu-id="abc05-2749">Resident Registration Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2749">Resident Registration Number</span></span>
- <span data-ttu-id="abc05-2750">Resident Register Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2750">Resident Register Number</span></span> 
- <span data-ttu-id="abc05-2751">Residents Basic Registry Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2751">Residents Basic Registry Number</span></span> 
- <span data-ttu-id="abc05-2752">Resident Registration No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2752">Resident Registration No.</span></span> 
- <span data-ttu-id="abc05-2753">Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2753">Resident Register No.</span></span> 
- <span data-ttu-id="abc05-2754">Residents Basic Registry No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2754">Residents Basic Registry No.</span></span> 
- <span data-ttu-id="abc05-2755">Basic Resident Register No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2755">Basic Resident Register No.</span></span> 
- <span data-ttu-id="abc05-2756">住民登録番号、登録番号をレジデント</span><span class="sxs-lookup"><span data-stu-id="abc05-2756">住民登録番号、登録番号をレジデント</span></span> 
- <span data-ttu-id="abc05-2757">住民基本登録番号、登録番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2757">住民基本登録番号、登録番号</span></span> 
- <span data-ttu-id="abc05-2758">住民基本レジストリ番号を常駐</span><span class="sxs-lookup"><span data-stu-id="abc05-2758">住民基本レジストリ番号を常駐</span></span> 
- <span data-ttu-id="abc05-2759">登録番号を常駐住民基本台帳登録番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2759">登録番号を常駐住民基本台帳登録番号</span></span> 

   
## <a name="japan-social-insurance-number-sin"></a><span data-ttu-id="abc05-2760">일본 SIN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-2760">Japan Social Insurance Number (SIN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2761">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2761">Format</span></span>

<span data-ttu-id="abc05-2762">7-12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2762">7-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2763">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2763">Pattern</span></span>

<span data-ttu-id="abc05-2764">7-12자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2764">7-12 digits:</span></span>
- <span data-ttu-id="abc05-2765">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2765">Four digits</span></span> 
- <span data-ttu-id="abc05-2766">하이픈 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-2766">A hyphen (optional)</span></span> 
- <span data-ttu-id="abc05-2767">6 자리 숫자 또는</span><span class="sxs-lookup"><span data-stu-id="abc05-2767">Six digits OR</span></span>
- <span data-ttu-id="abc05-2768">7-12자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2768">7-12 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2769">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2769">Checksum</span></span>

<span data-ttu-id="abc05-2770">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2770">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2771">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2771">Definition</span></span>

<span data-ttu-id="abc05-2772">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2772">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2773">Func_jp_sin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2773">The function Func_jp_sin finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2774">Keyword_jp_sin의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2774">A keyword from Keyword_jp_sin is found.</span></span>

<span data-ttu-id="abc05-2775">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2775">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2776">Func_jp_sin_pre_1997 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2776">The function Func_jp_sin_pre_1997 finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2777">Keyword_jp_sin의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2777">A keyword from Keyword_jp_sin is found.</span></span>

```xml
<!-- Japan Social Insurance Number -->
<Entity id="c840e719-0896-45bb-84fd-1ed5c95e45ff" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_jp_sin" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_jp_sin_pre_1997" />
        <Match idRef="Keyword_jp_sin" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2778">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2778">Keywords</span></span>

#### <a name="keyword_jp_sin"></a><span data-ttu-id="abc05-2779">Keyword_jp_sin</span><span class="sxs-lookup"><span data-stu-id="abc05-2779">Keyword_jp_sin</span></span>

- <span data-ttu-id="abc05-2780">Social Insurance No.</span><span class="sxs-lookup"><span data-stu-id="abc05-2780">Social Insurance No.</span></span> 
- <span data-ttu-id="abc05-2781">Social Insurance Num</span><span class="sxs-lookup"><span data-stu-id="abc05-2781">Social Insurance Num</span></span> 
- <span data-ttu-id="abc05-2782">Social Insurance Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2782">Social Insurance Number</span></span> 
- <span data-ttu-id="abc05-2783">社会保険のテンキー</span><span class="sxs-lookup"><span data-stu-id="abc05-2783">社会保険のテンキー</span></span> 
- <span data-ttu-id="abc05-2784">社会保険番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2784">社会保険番号</span></span> 

## <a name="japanese-residence-card-number"></a><span data-ttu-id="abc05-2785">일본어 거주지 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2785">Japanese Residence Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2786">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2786">Format</span></span>

<span data-ttu-id="abc05-2787">12 개의 문자 및 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2787">12 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2788">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2788">Pattern</span></span>

<span data-ttu-id="abc05-2789">12 개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2789">12 letters and digits:</span></span>
- <span data-ttu-id="abc05-2790">2문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2790">Two letters (not case sensitive)</span></span>
- <span data-ttu-id="abc05-2791">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2791">Eight digits</span></span> 
- <span data-ttu-id="abc05-2792">2문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-2792">Two letters (not case sensitive)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2793">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2793">Checksum</span></span>

<span data-ttu-id="abc05-2794">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2794">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2795">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2795">Definition</span></span>

<span data-ttu-id="abc05-2796">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2796">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2797">정규식 Regex_jp_residence_card_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2797">The regular expression Regex_jp_residence_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2798">Keyword_jp_residence_card_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2798">A keyword from Keyword_jp_residence_card_number is found.</span></span>

```xml
<!--Japan Residence Card Number-->
-<Entity id="ac36fef2-a289-4e2c-bb48-b02366e89fc0" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Regex_jp_residence_card_number"/>
      <Match idRef="Keyword_jp_residence_card_number"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2799">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2799">Keywords</span></span>

#### <a name="keyword_jp_residence_card_number"></a><span data-ttu-id="abc05-2800">Keyword_jp_residence_card_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2800">Keyword_jp_residence_card_number</span></span>

- <span data-ttu-id="abc05-2801">거주지 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2801">Residence card number</span></span>
- <span data-ttu-id="abc05-2802">거주지 카드 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2802">Residence card no</span></span>
- <span data-ttu-id="abc05-2803">거주지 카드 #</span><span class="sxs-lookup"><span data-stu-id="abc05-2803">Residence card #</span></span>
- <span data-ttu-id="abc05-2804">在留カード番号</span><span class="sxs-lookup"><span data-stu-id="abc05-2804">在留カード番号</span></span>
   
## <a name="malaysia-id-card-number"></a><span data-ttu-id="abc05-2805">말레이시아 ID 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2805">Malaysia ID Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2806">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2806">Format</span></span>

<span data-ttu-id="abc05-2807">선택적으로 하이픈을 포함하는 12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2807">12 digits containing optional hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2808">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2808">Pattern</span></span>

<span data-ttu-id="abc05-2809">12자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2809">12 digits:</span></span>
- <span data-ttu-id="abc05-2810">생년월일에 해당하는 YYMMDD 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-2810">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="abc05-2811">대시(옵션)</span><span class="sxs-lookup"><span data-stu-id="abc05-2811">A dash (optional)</span></span> 
- <span data-ttu-id="abc05-2812">2개 문자로 이루어진 출생지 코드 </span><span class="sxs-lookup"><span data-stu-id="abc05-2812">Two-letter place-of-birth code</span></span> 
- <span data-ttu-id="abc05-2813">대시(옵션)</span><span class="sxs-lookup"><span data-stu-id="abc05-2813">A dash (optional)</span></span> 
- <span data-ttu-id="abc05-2814">임의의 3자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-2814">Three random digits</span></span> 
- <span data-ttu-id="abc05-2815">1자리 성별 코드</span><span class="sxs-lookup"><span data-stu-id="abc05-2815">One-digit gender code</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2816">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2816">Checksum</span></span>

<span data-ttu-id="abc05-2817">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2817">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2818">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2818">Definition</span></span>

<span data-ttu-id="abc05-2819">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2819">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2820">정규식 Regex_malaysia_id_card_number 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2820">The regular expression Regex_malaysia_id_card_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2821">Keyword_malaysia_id_card_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2821">A keyword from Keyword_malaysia_id_card_number is found.</span></span>

```xml
<!-- Malaysia ID Card Number -->
</Entity>
      <Entity id="7f0e921c-9677-435b-aba2-bb8f1013c749" patternsProximity="300" recommendedConfidence="85">
        <Pattern confidenceLevel="85">
            <IdMatch idRef="Regex_malaysia_id_card_number" />
            <Match idRef="Keyword_malaysia_id_card_number" />
        </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2822">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2822">Keywords</span></span>
   
#### <a name="keyword_malaysia_id_card_number"></a><span data-ttu-id="abc05-2823">Keyword_malaysia_id_card_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2823">Keyword_malaysia_id_card_number</span></span>

- <span data-ttu-id="abc05-2824">디지털 응용 프로그램 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2824">digital application card</span></span>
- <span data-ttu-id="abc05-2825">i/c</span><span class="sxs-lookup"><span data-stu-id="abc05-2825">i/c</span></span>
- <span data-ttu-id="abc05-2826">i/c 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2826">i/c no</span></span>
- <span data-ttu-id="abc05-2827">비용</span><span class="sxs-lookup"><span data-stu-id="abc05-2827">ic</span></span>
- <span data-ttu-id="abc05-2828">ic 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2828">ic no</span></span>
- <span data-ttu-id="abc05-2829">id card</span><span class="sxs-lookup"><span data-stu-id="abc05-2829">id card</span></span>
- <span data-ttu-id="abc05-2830">식별 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2830">identification Card</span></span>
- <span data-ttu-id="abc05-2831">identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-2831">identity card</span></span>
- <span data-ttu-id="abc05-2832">k/p</span><span class="sxs-lookup"><span data-stu-id="abc05-2832">k/p</span></span>
- <span data-ttu-id="abc05-2833">k/p 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2833">k/p no</span></span>
- <span data-ttu-id="abc05-2834">kad akuan diri</span><span class="sxs-lookup"><span data-stu-id="abc05-2834">kad akuan diri</span></span>
- <span data-ttu-id="abc05-2835">kad aplikasi 디지털</span><span class="sxs-lookup"><span data-stu-id="abc05-2835">kad aplikasi digital</span></span>
- <span data-ttu-id="abc05-2836">kad pengenalan 말레이시아</span><span class="sxs-lookup"><span data-stu-id="abc05-2836">kad pengenalan malaysia</span></span>
- <span data-ttu-id="abc05-2837">kp</span><span class="sxs-lookup"><span data-stu-id="abc05-2837">kp</span></span>
- <span data-ttu-id="abc05-2838">kp 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2838">kp no</span></span>
- <span data-ttu-id="abc05-2839">mykad</span><span class="sxs-lookup"><span data-stu-id="abc05-2839">mykad</span></span>
- <span data-ttu-id="abc05-2840">mykas</span><span class="sxs-lookup"><span data-stu-id="abc05-2840">mykas</span></span>
- <span data-ttu-id="abc05-2841">mykid</span><span class="sxs-lookup"><span data-stu-id="abc05-2841">mykid</span></span>
- <span data-ttu-id="abc05-2842">mypr</span><span class="sxs-lookup"><span data-stu-id="abc05-2842">mypr</span></span>
- <span data-ttu-id="abc05-2843">myta</span><span class="sxs-lookup"><span data-stu-id="abc05-2843">mytentera</span></span>
- <span data-ttu-id="abc05-2844">말레이시아 id 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2844">malaysia identity card</span></span>
- <span data-ttu-id="abc05-2845">말레이지아 id 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2845">malaysian identity card</span></span>
- <span data-ttu-id="abc05-2846">nric</span><span class="sxs-lookup"><span data-stu-id="abc05-2846">nric</span></span>
- <span data-ttu-id="abc05-2847">개인 식별 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2847">personal identification card</span></span>
   
## <a name="netherlands-citizens-service-bsn-number"></a><span data-ttu-id="abc05-2848">네덜란드 시민 서비스(BSN) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2848">Netherlands Citizen's Service (BSN) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2849">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2849">Format</span></span>

<span data-ttu-id="abc05-2850">선택적으로 공백을 포함하는 8-9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2850">8-9 digits containing optional spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2851">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2851">Pattern</span></span>

<span data-ttu-id="abc05-2852">8-9자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2852">8-9 digits:</span></span>
- <span data-ttu-id="abc05-2853">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2853">Three digits</span></span> 
- <span data-ttu-id="abc05-2854">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-2854">A space (optional)</span></span> 
- <span data-ttu-id="abc05-2855">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2855">Three digits</span></span> 
- <span data-ttu-id="abc05-2856">공백 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-2856">A space (optional)</span></span> 
- <span data-ttu-id="abc05-2857">2-3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2857">2-3 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2858">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2858">Checksum</span></span>

<span data-ttu-id="abc05-2859">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2859">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2860">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2860">Definition</span></span>

<span data-ttu-id="abc05-2861">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2861">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2862">Func_netherlands_bsn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2862">The function Func_netherlands_bsn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2863">Keyword_netherlands_bsn에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2863">A keyword from Keyword_netherlands_bsn is found.</span></span>
- <span data-ttu-id="abc05-2864">Func_eu_date2 함수는 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2864">The function Func_eu_date2 finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-2865">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2865">The checksum passes.</span></span>

```xml
<!-- Netherlands Citizen's Service (BSN) Number -->
<Entity id="c5f54253-ef7e-44f6-a578-440ed67e946d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
       <IdMatch idRef="Func_netherlands_bsn" /> 
       <Match idRef="Keyword_netherlands_bsn" /> 
       <Match idRef="Func_eu_date2" /> 
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2866">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2866">Keywords</span></span>

#### <a name="keyword_netherlands_bsn"></a><span data-ttu-id="abc05-2867">Keyword_netherlands_bsn</span><span class="sxs-lookup"><span data-stu-id="abc05-2867">Keyword_netherlands_bsn</span></span>

- <span data-ttu-id="abc05-2868">Citizen service number</span><span class="sxs-lookup"><span data-stu-id="abc05-2868">Citizen service number</span></span> 
- <span data-ttu-id="abc05-2869">BSN</span><span class="sxs-lookup"><span data-stu-id="abc05-2869">BSN</span></span> 
- <span data-ttu-id="abc05-2870">Burgerservicenummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2870">Burgerservicenummer</span></span> 
- <span data-ttu-id="abc05-2871">Sofinummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2871">Sofinummer</span></span> 
- <span data-ttu-id="abc05-2872">Persoonsgebonden nummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2872">Persoonsgebonden nummer</span></span> 
- <span data-ttu-id="abc05-2873">Persoonsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2873">Persoonsnummer</span></span>    

   
## <a name="new-zealand-ministry-of-health-number"></a><span data-ttu-id="abc05-2874">뉴질랜드 보건부 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2874">New Zealand Ministry of Health Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2875">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2875">Format</span></span>

<span data-ttu-id="abc05-2876">3개 문자, 공백 1개(선택 사항) 및 4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2876">Three letters, a space (optional), and four digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2877">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2877">Pattern</span></span>

<span data-ttu-id="abc05-2878">3 개의 문자 (대/소문자 구분 안 함) 공백 (선택 사항) 4 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2878">Three letters (not case sensitive) a space (optional) four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2879">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2879">Checksum</span></span>

<span data-ttu-id="abc05-2880">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2880">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2881">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2881">Definition</span></span>

<span data-ttu-id="abc05-2882">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2882">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2883">Func_new_zealand_ministry_of_health_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2883">The function Func_new_zealand_ministry_of_health_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2884">Keyword_nz_terms의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2884">A keyword from Keyword_nz_terms is found.</span></span>
- <span data-ttu-id="abc05-2885">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2885">The checksum passes.</span></span>

```xml
<!-- New Zealand Health Number -->
<Entity id="2b71c1c8-d14e-4430-82dc-fd1ed6bf05c7" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_new_zealand_ministry_of_health_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_nz_terms" />
        </Any>
    </Pattern>
</Entity>
```

<span data-ttu-id="abc05-2886">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2886">Keywords</span></span>

<span data-ttu-id="abc05-2887">Keyword_nz_terms</span><span class="sxs-lookup"><span data-stu-id="abc05-2887">Keyword_nz_terms</span></span>

- <span data-ttu-id="abc05-2888">NHI</span><span class="sxs-lookup"><span data-stu-id="abc05-2888">NHI</span></span> 
- <span data-ttu-id="abc05-2889">New Zealand</span><span class="sxs-lookup"><span data-stu-id="abc05-2889">New Zealand</span></span> 
- <span data-ttu-id="abc05-2890">상태</span><span class="sxs-lookup"><span data-stu-id="abc05-2890">Health</span></span> 
- <span data-ttu-id="abc05-2891">처리가</span><span class="sxs-lookup"><span data-stu-id="abc05-2891">treatment</span></span> 
   
## <a name="norway-identification-number"></a><span data-ttu-id="abc05-2892">Norway Identification Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2892">Norway Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2893">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2893">Format</span></span>

<span data-ttu-id="abc05-2894">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2894">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2895">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2895">Pattern</span></span>

<span data-ttu-id="abc05-2896">11자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2896">11 digits:</span></span>
- <span data-ttu-id="abc05-2897">생년월일에 해당하는 DDMMYY 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-2897">Six digits in the format DDMMYY which are the date of birth</span></span> 
- <span data-ttu-id="abc05-2898">3자리 개인 번호 </span><span class="sxs-lookup"><span data-stu-id="abc05-2898">Three-digit individual number</span></span> 
- <span data-ttu-id="abc05-2899">2개의 검사 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2899">Two check digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2900">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2900">Checksum</span></span>

<span data-ttu-id="abc05-2901">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2901">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2902">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2902">Definition</span></span>

<span data-ttu-id="abc05-2903">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2903">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2904">Func_norway_id_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2904">The function Func_norway_id_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2905">Keyword_norway_id_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2905">A keyword from Keyword_norway_id_number is found.</span></span>
- <span data-ttu-id="abc05-2906">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2906">The checksum passes.</span></span>
- <span data-ttu-id="abc05-2907">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2907">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2908">Func_norway_id_numbe 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2908">The function Func_norway_id_numbe finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2909">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2909">The checksum passes.</span></span>

```xml
<!-- Norway Identification Number -->
<Entity id="d4c8a798-e9f2-4bd3-9652-500d24080fc3" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_norway_id_number"/>
     <Match idRef="Keyword_norway_id_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_norway_id_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2910">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2910">Keywords</span></span>

#### <a name="keyword_norway_id_number"></a><span data-ttu-id="abc05-2911">Keyword_norway_id_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2911">Keyword_norway_id_number</span></span>

- <span data-ttu-id="abc05-2912">Personal identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-2912">Personal identification number</span></span>
- <span data-ttu-id="abc05-2913">Norwegian ID Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2913">Norwegian ID Number</span></span>
- <span data-ttu-id="abc05-2914">ID Number</span><span class="sxs-lookup"><span data-stu-id="abc05-2914">ID Number</span></span>
- <span data-ttu-id="abc05-2915">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-2915">Identification</span></span>
- <span data-ttu-id="abc05-2916">Personnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2916">Personnummer</span></span>
- <span data-ttu-id="abc05-2917">Fødselsnummer</span><span class="sxs-lookup"><span data-stu-id="abc05-2917">Fødselsnummer</span></span>

   
## <a name="philippines-unified-multi-purpose-id-number"></a><span data-ttu-id="abc05-2918">필리핀 통합 다목적 ID 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2918">Philippines Unified Multi-Purpose ID Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2919">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2919">Format</span></span>

<span data-ttu-id="abc05-2920">하이픈으로 구분된 12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2920">12 digits separated by hyphens</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2921">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2921">Pattern</span></span>

<span data-ttu-id="abc05-2922">12자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-2922">12 digits:</span></span>
- <span data-ttu-id="abc05-2923">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2923">Four digits</span></span> 
- <span data-ttu-id="abc05-2924">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-2924">A hyphen</span></span> 
- <span data-ttu-id="abc05-2925">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2925">Seven digits</span></span> 
- <span data-ttu-id="abc05-2926">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-2926">A hyphen</span></span> 
- <span data-ttu-id="abc05-2927">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2927">One digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2928">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2928">Checksum</span></span>

<span data-ttu-id="abc05-2929">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-2929">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2930">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2930">Definition</span></span>

<span data-ttu-id="abc05-2931">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2931">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2932">정규식 Regex_philippines_unified_id 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2932">The regular expression Regex_philippines_unified_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2933">Keyword_philippines_id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2933">A keyword from Keyword_philippines_id is found.</span></span>

```xml
<!-- Philippines Unified Multi-Purpose ID number -->
<Entity id="019b39dd-8c25-4765-91a3-d9c6baf3c3b3" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_philippines_unified_id"/>
     <Match idRef="Keyword_philippines_id"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2934">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2934">Keywords</span></span>
   
#### <a name="keyword_philippines_id"></a><span data-ttu-id="abc05-2935">Keyword_philippines_id</span><span class="sxs-lookup"><span data-stu-id="abc05-2935">Keyword_philippines_id</span></span>

- <span data-ttu-id="abc05-2936">Unified Multi-Purpose ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2936">Unified Multi-Purpose ID</span></span> 
- <span data-ttu-id="abc05-2937">UMID</span><span class="sxs-lookup"><span data-stu-id="abc05-2937">UMID</span></span> 
- <span data-ttu-id="abc05-2938">Identity Card</span><span class="sxs-lookup"><span data-stu-id="abc05-2938">Identity Card</span></span> 
- <span data-ttu-id="abc05-2939">Pinag-isang Multi-Layunin ID</span><span class="sxs-lookup"><span data-stu-id="abc05-2939">Pinag-isang Multi-Layunin ID</span></span>
   
## <a name="poland-identity-card"></a><span data-ttu-id="abc05-2940">폴란드 ID 카드</span><span class="sxs-lookup"><span data-stu-id="abc05-2940">Poland Identity Card</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2941">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2941">Format</span></span>

<span data-ttu-id="abc05-2942">3개의 문자 및 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2942">Three letters and six digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2943">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2943">Pattern</span></span>

<span data-ttu-id="abc05-2944">3개의 문자(대/소문자 구분 안 함)와 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2944">Three letters (not case sensitive) followed by six digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2945">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2945">Checksum</span></span>

<span data-ttu-id="abc05-2946">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2946">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2947">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2947">Definition</span></span>

<span data-ttu-id="abc05-2948">DLP 정책은 300 Func_polish_national_id 문자에 근접 한 경우에는이 유형의 중요 한 정보를 검색 하는 것으로 75% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2948">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters: The function Func_polish_national_id finds content that matches the pattern.</span></span>
<span data-ttu-id="abc05-2949">Keyword_polish_national_id_passport_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2949">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
<span data-ttu-id="abc05-2950">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2950">The checksum passes.</span></span>

```xml
<!-- Poland Identity Card-->
<Entity id="25E64989-ED5D-40CA-A939-6C14183BB7BF" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_national_id" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2951">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2951">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="abc05-2952">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2952">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="abc05-2953">Dowód osobisty</span><span class="sxs-lookup"><span data-stu-id="abc05-2953">Dowód osobisty</span></span>
- <span data-ttu-id="abc05-2954">U r i dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="abc05-2954">Numer dowodu osobistego</span></span>
- <span data-ttu-id="abc05-2955">Nazwa i u r i dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="abc05-2955">Nazwa i numer dowodu osobistego</span></span>
- <span data-ttu-id="abc05-2956">Nazwa i veiligheid dowodu osobistego</span><span class="sxs-lookup"><span data-stu-id="abc05-2956">Nazwa i nr dowodu osobistego</span></span>
- <span data-ttu-id="abc05-2957">Nazwa i nr dowodu tożsamości</span><span class="sxs-lookup"><span data-stu-id="abc05-2957">Nazwa i nr dowodu tożsamości</span></span>
- <span data-ttu-id="abc05-2958">Dowód Tożsamości</span><span class="sxs-lookup"><span data-stu-id="abc05-2958">Dowód Tożsamości</span></span>
- <span data-ttu-id="abc05-2959">dow.</span><span class="sxs-lookup"><span data-stu-id="abc05-2959">dow.</span></span> <span data-ttu-id="abc05-2960">르.</span><span class="sxs-lookup"><span data-stu-id="abc05-2960">os.</span></span>

   
## <a name="poland-national-id-pesel"></a><span data-ttu-id="abc05-2961">폴란드 국가 ID(PESEL)</span><span class="sxs-lookup"><span data-stu-id="abc05-2961">Poland National ID (PESEL)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2962">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2962">Format</span></span>

<span data-ttu-id="abc05-2963">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2963">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2964">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2964">Pattern</span></span>

<span data-ttu-id="abc05-2965">11자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2965">11 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2966">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2966">Checksum</span></span>

<span data-ttu-id="abc05-2967">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2967">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2968">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2968">Definition</span></span>

<span data-ttu-id="abc05-2969">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2969">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2970">Func_pesel_identification_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2970">The function Func_pesel_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2971">Keyword_pesel_identification_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2971">A keyword from Keyword_pesel_identification_number is found.</span></span>
- <span data-ttu-id="abc05-2972">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2972">The checksum passes.</span></span>

```xml
<!-- Poland National ID (PESEL) -->      
<Entity id="E3AAF206-4297-412F-9E06-BA8487E22456" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_pesel_identification_number" />
          <Match idRef="Keyword_pesel_identification_number" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2973">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2973">Keywords</span></span>

#### <a name="keyword_pesel_identification_number"></a><span data-ttu-id="abc05-2974">Keyword_pesel_identification_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2974">Keyword_pesel_identification_number</span></span>

- <span data-ttu-id="abc05-2975">Nr PESEL</span><span class="sxs-lookup"><span data-stu-id="abc05-2975">Nr PESEL</span></span>
- <span data-ttu-id="abc05-2976">PESEL</span><span class="sxs-lookup"><span data-stu-id="abc05-2976">PESEL</span></span>   

   
## <a name="poland-passport"></a><span data-ttu-id="abc05-2977">폴란드 여권</span><span class="sxs-lookup"><span data-stu-id="abc05-2977">Poland Passport</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2978">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2978">Format</span></span>

<span data-ttu-id="abc05-2979">2개 문자와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2979">Two letters and seven digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2980">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2980">Pattern</span></span>

<span data-ttu-id="abc05-2981">2개의 문자(대/소문자 구분 안 함)와 7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2981">Two letters (not case sensitive) followed by seven digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-2982">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-2982">Checksum</span></span>

<span data-ttu-id="abc05-2983">예</span><span class="sxs-lookup"><span data-stu-id="abc05-2983">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-2984">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-2984">Definition</span></span>

<span data-ttu-id="abc05-2985">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2985">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-2986">Func_polish_passport_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2986">The function Func_polish_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-2987">Keyword_polish_national_id_passport_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2987">A keyword from Keyword_polish_national_id_passport_number is found.</span></span>
- <span data-ttu-id="abc05-2988">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-2988">The checksum passes.</span></span>

```xml
<!-- Poland Passport Number -->
<Entity id="03937FB5-D2B6-4487-B61F-0F8BFF7C3517" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_polish_passport_number" />
          <Match idRef="Keyword_polish_national_id_passport_number" />
      </Pattern>
</Entity>
</Version>
```

### <a name="keywords"></a><span data-ttu-id="abc05-2989">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-2989">Keywords</span></span>

#### <a name="keyword_polish_national_id_passport_number"></a><span data-ttu-id="abc05-2990">Keyword_polish_national_id_passport_number</span><span class="sxs-lookup"><span data-stu-id="abc05-2990">Keyword_polish_national_id_passport_number</span></span>

- <span data-ttu-id="abc05-2991">U r i (zportu)</span><span class="sxs-lookup"><span data-stu-id="abc05-2991">Numer paszportu</span></span>
- <span data-ttu-id="abc05-2992">Veiligheid.</span><span class="sxs-lookup"><span data-stu-id="abc05-2992">Nr.</span></span> <span data-ttu-id="abc05-2993">고 zportu</span><span class="sxs-lookup"><span data-stu-id="abc05-2993">Paszportu</span></span>
- <span data-ttu-id="abc05-2994">고 zport</span><span class="sxs-lookup"><span data-stu-id="abc05-2994">Paszport</span></span>

   
## <a name="portugal-citizen-card-number"></a><span data-ttu-id="abc05-2995">포르투갈 시민 카드 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-2995">Portugal Citizen Card Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-2996">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-2996">Format</span></span>

<span data-ttu-id="abc05-2997">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2997">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-2998">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-2998">Pattern</span></span>

<span data-ttu-id="abc05-2999">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-2999">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3000">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3000">Checksum</span></span>

<span data-ttu-id="abc05-3001">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3001">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3002">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3002">Definition</span></span>

<span data-ttu-id="abc05-3003">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3003">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3004">정규식 Regex_portugal_citizen_card 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3004">The regular expression Regex_portugal_citizen_card finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3005">Keyword_portugal_citizen_card에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3005">A keyword from Keyword_portugal_citizen_card is found.</span></span>

```xml
<!-- Portugal Citizen Card Number -->
<Entity id="91a7ece2-add4-4986-9a15-c84544d81ecd" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_portugal_citizen_card"/>
     <Match idRef="Keyword_portugal_citizen_card"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3006">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3006">Keywords</span></span>

#### <a name="keyword_portugal_citizen_card"></a><span data-ttu-id="abc05-3007">Keyword_portugal_citizen_card</span><span class="sxs-lookup"><span data-stu-id="abc05-3007">Keyword_portugal_citizen_card</span></span>

- <span data-ttu-id="abc05-3008">Citizen Card</span><span class="sxs-lookup"><span data-stu-id="abc05-3008">Citizen Card</span></span>
- <span data-ttu-id="abc05-3009">National ID Card</span><span class="sxs-lookup"><span data-stu-id="abc05-3009">National ID Card</span></span>
- <span data-ttu-id="abc05-3010">참조란</span><span class="sxs-lookup"><span data-stu-id="abc05-3010">CC</span></span>
- <span data-ttu-id="abc05-3011">Cartão de Cidadão</span><span class="sxs-lookup"><span data-stu-id="abc05-3011">Cartão de Cidadão</span></span>
- <span data-ttu-id="abc05-3012">Bilhete de Identidade</span><span class="sxs-lookup"><span data-stu-id="abc05-3012">Bilhete de Identidade</span></span>
   
## <a name="saudi-arabia-national-id"></a><span data-ttu-id="abc05-3013">사우디 아라비아 국가 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-3013">Saudi Arabia National ID</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3014">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3014">Format</span></span>

<span data-ttu-id="abc05-3015">10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3015">10 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3016">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3016">Pattern</span></span>

<span data-ttu-id="abc05-3017">10자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3017">10 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3018">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3018">Checksum</span></span>

<span data-ttu-id="abc05-3019">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3019">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3020">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3020">Definition</span></span>

<span data-ttu-id="abc05-3021">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3021">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3022">Regex_saudi_arabia_national_id 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3022">The regular expression Regex_saudi_arabia_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3023">Keyword_saudi_arabia_national_id의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3023">A keyword from Keyword_saudi_arabia_national_id is found.</span></span>

```xml
<!-- Saudi Arabia National ID -->
<Entity id="8c5a0ba8-404a-41a3-8871-746aa21ee6c0" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_saudi_arabia_national_id" />
        <Any minMatches="1">
          <Match idRef="Keyword_saudi_arabia_national_id" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3024">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3024">Keywords</span></span>

#### <a name="keyword_saudi_arabia_national_id"></a><span data-ttu-id="abc05-3025">Keyword_saudi_arabia_national_id</span><span class="sxs-lookup"><span data-stu-id="abc05-3025">Keyword_saudi_arabia_national_id</span></span>

- <span data-ttu-id="abc05-3026">Identification Card</span><span class="sxs-lookup"><span data-stu-id="abc05-3026">Identification Card</span></span> 
- <span data-ttu-id="abc05-3027">I card number</span><span class="sxs-lookup"><span data-stu-id="abc05-3027">I card number</span></span> 
- <span data-ttu-id="abc05-3028">ID number</span><span class="sxs-lookup"><span data-stu-id="abc05-3028">ID number</span></span> 
- <span data-ttu-id="abc05-3029">الوطنية الهوية بطاقة رقم</span><span class="sxs-lookup"><span data-stu-id="abc05-3029">الوطنية الهوية بطاقة رقم</span></span> 

   
## <a name="singapore-national-registration-identity-card-nric-number"></a><span data-ttu-id="abc05-3030">싱가포르 NRIC(국가 등록 ID 카드) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3030">Singapore National Registration Identity Card (NRIC) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3031">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3031">Format</span></span>

<span data-ttu-id="abc05-3032">9개의 문자 및 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3032">Nine letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3033">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3033">Pattern</span></span>

- <span data-ttu-id="abc05-3034">9개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3034">Nine letters and digits:</span></span>
- <span data-ttu-id="abc05-3035">문자 "F", "G", "S" 또는 "T"(대/소문자 구분 안 함) </span><span class="sxs-lookup"><span data-stu-id="abc05-3035">The letter "F", "G", "S", or "T" (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-3036">7자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3036">Seven digits</span></span> 
- <span data-ttu-id="abc05-3037">알파벳 검사 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3037">An alphabetic check digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3038">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3038">Checksum</span></span>

<span data-ttu-id="abc05-3039">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3039">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3040">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3040">Definition</span></span>

<span data-ttu-id="abc05-3041">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3041">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3042">정규식 Regex_singapore_nric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3042">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3043">Keyword_singapore_nric에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3043">A keyword from Keyword_singapore_nric is found.</span></span>
- <span data-ttu-id="abc05-3044">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3044">The checksum passes.</span></span>

<span data-ttu-id="abc05-3045">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3045">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3046">정규식 Regex_singapore_nric 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3046">The regular expression Regex_singapore_nric finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3047">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3047">The checksum passes.</span></span>

```xml
<!-- Singapore National Registration Identity Card (NRIC) Number -->
<Entity id="cead390a-dd83-4856-9751-fb6dc98c34da" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Regex_singapore_nric"/>
     <Match idRef="Keyword_singapore_nric"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_singapore_nric"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3048">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3048">Keywords</span></span>
   
#### <a name="keyword_singapore_nric"></a><span data-ttu-id="abc05-3049">Keyword_singapore_nric</span><span class="sxs-lookup"><span data-stu-id="abc05-3049">Keyword_singapore_nric</span></span>

- <span data-ttu-id="abc05-3050">National Registration Identity Card</span><span class="sxs-lookup"><span data-stu-id="abc05-3050">National Registration Identity Card</span></span> 
- <span data-ttu-id="abc05-3051">Identity Card Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3051">Identity Card Number</span></span> 
- <span data-ttu-id="abc05-3052">NRIC</span><span class="sxs-lookup"><span data-stu-id="abc05-3052">NRIC</span></span> 
- <span data-ttu-id="abc05-3053">비용</span><span class="sxs-lookup"><span data-stu-id="abc05-3053">IC</span></span> 
- <span data-ttu-id="abc05-3054">Foreign Identification Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3054">Foreign Identification Number</span></span> 
- <span data-ttu-id="abc05-3055">삭제할</span><span class="sxs-lookup"><span data-stu-id="abc05-3055">FIN</span></span> 
- <span data-ttu-id="abc05-3056">身份证</span><span class="sxs-lookup"><span data-stu-id="abc05-3056">身份证</span></span> 
- <span data-ttu-id="abc05-3057">身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-3057">身份證</span></span> 
   
## <a name="south-africa-identification-number"></a><span data-ttu-id="abc05-3058">남아프리카 공화국 식별 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3058">South Africa Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3059">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3059">Format</span></span>

<span data-ttu-id="abc05-3060">공백을 포함할 수 있는 13자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3060">13 digits that may contain spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3061">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3061">Pattern</span></span>

<span data-ttu-id="abc05-3062">13자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3062">13 digits:</span></span>
- <span data-ttu-id="abc05-3063">생년월일에 해당하는 YYMMDD 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-3063">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="abc05-3064">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3064">Four digits</span></span> 
- <span data-ttu-id="abc05-3065">1자리 시민권 표시 </span><span class="sxs-lookup"><span data-stu-id="abc05-3065">A single-digit citizenship indicator</span></span> 
- <span data-ttu-id="abc05-3066">숫자 "8" 또는 "9" </span><span class="sxs-lookup"><span data-stu-id="abc05-3066">The digit "8" or "9"</span></span> 
- <span data-ttu-id="abc05-3067">체크섬 숫자에 해당하는 1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3067">One digit which is a checksum digit</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3068">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3068">Checksum</span></span>

<span data-ttu-id="abc05-3069">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3069">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3070">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3070">Definition</span></span>

<span data-ttu-id="abc05-3071">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3071">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3072">Func_south_africa_identification_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3072">The function Func_south_africa_identification_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3073">Keyword_south_africa_identification_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3073">A keyword from Keyword_south_africa_identification_number is found.</span></span>
- <span data-ttu-id="abc05-3074">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3074">The checksum passes.</span></span>

```xml
<!-- South Africa Identification Number -->
<Entity id="e2adf7cb-8ea6-4048-a2ed-d89eb65f2780" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_africa_identification_number"/>
     <Match idRef="Keyword_south_africa_identification_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3075">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3075">Keywords</span></span>
   
#### <a name="keyword_south_africa_identification_number"></a><span data-ttu-id="abc05-3076">Keyword_south_africa_identification_number</span><span class="sxs-lookup"><span data-stu-id="abc05-3076">Keyword_south_africa_identification_number</span></span>

- <span data-ttu-id="abc05-3077">Identity card</span><span class="sxs-lookup"><span data-stu-id="abc05-3077">Identity card</span></span>
- <span data-ttu-id="abc05-3078">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-3078">ID</span></span>
- <span data-ttu-id="abc05-3079">확인과</span><span class="sxs-lookup"><span data-stu-id="abc05-3079">Identification</span></span> 
   
## <a name="south-korea-resident-registration-number"></a><span data-ttu-id="abc05-3080">한국 주민 등록 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3080">South Korea Resident Registration Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3081">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3081">Format</span></span>

<span data-ttu-id="abc05-3082">하이픈을 포함하는 13자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3082">13 digits containing a hyphen</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3083">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3083">Pattern</span></span>

<span data-ttu-id="abc05-3084">13자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3084">13 digits:</span></span>
- <span data-ttu-id="abc05-3085">생년월일에 해당하는 YYMMDD 형식의 6자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-3085">Six digits in the format YYMMDD which are the date of birth</span></span> 
- <span data-ttu-id="abc05-3086">하이픈</span><span class="sxs-lookup"><span data-stu-id="abc05-3086">A hyphen</span></span> 
- <span data-ttu-id="abc05-3087">세기 및 성별에 따라 결정되는 1자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-3087">One digit determined by the century and gender</span></span> 
- <span data-ttu-id="abc05-3088">4자리 출생 지역 코드 </span><span class="sxs-lookup"><span data-stu-id="abc05-3088">Four-digit region-of-birth code</span></span> 
- <span data-ttu-id="abc05-3089">앞 번호가 동일한 사람을 구분하기 위해 사용되는 1자리 숫자 </span><span class="sxs-lookup"><span data-stu-id="abc05-3089">One digit used to differentiate people for whom the preceding numbers are identical</span></span> 
- <span data-ttu-id="abc05-3090">검사 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3090">A check digit.</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3091">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3091">Checksum</span></span>

<span data-ttu-id="abc05-3092">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3092">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3093">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3093">Definition</span></span>

<span data-ttu-id="abc05-3094">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3094">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3095">Func_south_korea_resident_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3095">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3096">Keyword_south_korea_resident_number에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3096">A keyword from Keyword_south_korea_resident_number is found.</span></span>
- <span data-ttu-id="abc05-3097">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3097">The checksum passes.</span></span>

<span data-ttu-id="abc05-3098">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3098">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3099">Func_south_korea_resident_number 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3099">The function Func_south_korea_resident_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3100">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3100">The checksum passes.</span></span>

```xml
<!-- South Korea Resident Registration Number -->
<Entity id="5b802e18-ba80-44c4-bc83-bf2ad36ae36a" recommendedConfidence="85" patternsProximity="300">
  <Pattern confidenceLevel="85">
     <IdMatch idRef="Func_south_korea_resident_number"/>
     <Match idRef="Keyword_south_korea_resident_number"/>
  </Pattern>
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Func_south_korea_resident_number"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3101">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3101">Keywords</span></span>
   
#### <a name="keyword_south_korea_resident_number"></a><span data-ttu-id="abc05-3102">Keyword_south_korea_resident_number</span><span class="sxs-lookup"><span data-stu-id="abc05-3102">Keyword_south_korea_resident_number</span></span>

- <span data-ttu-id="abc05-3103">National ID card</span><span class="sxs-lookup"><span data-stu-id="abc05-3103">National ID card</span></span> 
- <span data-ttu-id="abc05-3104">Citizen's Registration Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3104">Citizen's Registration Number</span></span> 
- <span data-ttu-id="abc05-3105">Jumin deungnok beonho</span><span class="sxs-lookup"><span data-stu-id="abc05-3105">Jumin deungnok beonho</span></span> 
- <span data-ttu-id="abc05-3106">RRN</span><span class="sxs-lookup"><span data-stu-id="abc05-3106">RRN</span></span> 
- <span data-ttu-id="abc05-3107">주민등록번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3107">주민등록번호</span></span>
   
## <a name="spain-social-security-number-ssn"></a><span data-ttu-id="abc05-3108">스페인 SSN(사회 보장 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-3108">Spain Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3109">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3109">Format</span></span>

<span data-ttu-id="abc05-3110">11-12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3110">11-12 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3111">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3111">Pattern</span></span>

<span data-ttu-id="abc05-3112">11-12 자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3112">11-12 digits:</span></span>
- <span data-ttu-id="abc05-3113">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3113">Two digits</span></span> 
- <span data-ttu-id="abc05-3114">정방향 슬래시 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-3114">A forward slash (optional)</span></span> 
- <span data-ttu-id="abc05-3115">7-8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3115">7-8 digits</span></span> 
- <span data-ttu-id="abc05-3116">정방향 슬래시 1개(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-3116">A forward slash (optional)</span></span> 
- <span data-ttu-id="abc05-3117">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3117">Two digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3118">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3118">Checksum</span></span>

<span data-ttu-id="abc05-3119">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3119">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3120">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3120">Definition</span></span>

<span data-ttu-id="abc05-3121">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3121">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3122">Func_spanish_social_security_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3122">The function Func_spanish_social_security_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3123">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3123">The checksum passes.</span></span>

```xml
<!-- Spain SSN -->
<Entity id="5df987c0-8eae-4bce-ace7-b316347f3070" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_spanish_social_security_number" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3124">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3124">Keywords</span></span>

<span data-ttu-id="abc05-3125">없음</span><span class="sxs-lookup"><span data-stu-id="abc05-3125">None</span></span>

## <a name="sql-server-connection-string"></a><span data-ttu-id="abc05-3126">SQL Server 연결 문자열</span><span class="sxs-lookup"><span data-stu-id="abc05-3126">SQL Server Connection String</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3127">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3127">Format</span></span>

<span data-ttu-id="abc05-3128">아래 패턴에 설명 된 문자 및 문자열이 뒤에 오는 "User Id", "User ID", "uid" 또는 "UserId"입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3128">The string "User Id", "User ID", "uid", or "UserId" followed by the characters and strings outlined in the pattern below.</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3129">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3129">Pattern</span></span>

- <span data-ttu-id="abc05-3130">문자열 "User Id", "User ID", "uid" 또는 "UserId"</span><span class="sxs-lookup"><span data-stu-id="abc05-3130">The string "User Id", "User ID", "uid", or "UserId"</span></span>
- <span data-ttu-id="abc05-3131">1-200에서 대/소문자, 숫자, 기호, 특수 문자 또는 공백 사이의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-3131">Any combination of between 1-200 lower- or uppercase letters, digits, symbols, special characters, or spaces</span></span>
- <span data-ttu-id="abc05-3132">문자열 "Password" 또는 "pwd" (여기에서 "pwd" 앞에 소문자 문자가 오지 않음)</span><span class="sxs-lookup"><span data-stu-id="abc05-3132">The string "Password" or "pwd" where "pwd" is not preceded by a lowercase letter</span></span>
- <span data-ttu-id="abc05-3133">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-3133">An equal sign (=)</span></span>
- <span data-ttu-id="abc05-3134">달러 기호 ($), 백분율 기호 (%, 부등호 (>), 기호 (@), 따옴표 ("), 세미콜론 (;), 왼쪽 중괄호 ([) 또는 왼쪽 대괄호 ({))가 아닌 모든 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-3134">Any character that is not a dollar sign ($), percent symbol (%), greater than symbol (>), at symbol (@), quotation mark ("), semicolon (;), left brace ([), or left bracket ({)</span></span>
- <span data-ttu-id="abc05-3135">세미콜론 (;), 슬래시 (/) 또는 따옴표 (")가 아닌 7-128 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-3135">Any combination of 7-128 characters that are not a semicolon (;), forward slash (/), or quotation mark (")</span></span>
- <span data-ttu-id="abc05-3136">세미콜론 (;) 또는 따옴표 (")</span><span class="sxs-lookup"><span data-stu-id="abc05-3136">A semicolon (;) or quotation mark (")</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3137">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3137">Checksum</span></span>

<span data-ttu-id="abc05-3138">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3138">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3139">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3139">Definition</span></span>

<span data-ttu-id="abc05-3140">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3140">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3141">정규식 CEP_Regex_SQLServerConnectionString 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3141">The regular expression CEP_Regex_SQLServerConnectionString finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3142">CEP_GlobalFilter의 키워드를 찾을 수 **없습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-3142">A keyword from CEP_GlobalFilter is **not** found.</span></span>
- <span data-ttu-id="abc05-3143">정규식 CEP_PasswordPlaceHolder에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-3143">The regular expression CEP_PasswordPlaceHolder does **not** find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3144">정규식 CEP_CommonExampleKeywords에서 해당 패턴과 일치 하는 콘텐츠 **를 찾지 않습니다** .</span><span class="sxs-lookup"><span data-stu-id="abc05-3144">The regular expression CEP_CommonExampleKeywords does **not** find content that matches the pattern.</span></span>

```sql
<!---SQL Server Connection String>
<Entity id="e76b6205-d3cb-46f2-bd63-c90153f2f97d" patternsProximity="300" recommendedConfidence="85">
  <Pattern confidenceLevel="85">
        <IdMatch idRef="CEP_Regex_SQLServerConnectionString" />
        <Any minMatches="0" maxMatches="0">
            <Match idRef="CEP_GlobalFilter" />
            <Match idRef="CEP_PasswordPlaceHolder" />
            <Match idRef="CEP_CommonExampleKeywords" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3145">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3145">Keywords</span></span>

#### <a name="cep_globalfilter"></a><span data-ttu-id="abc05-3146">CEP_GlobalFilter</span><span class="sxs-lookup"><span data-stu-id="abc05-3146">CEP_GlobalFilter</span></span>

- <span data-ttu-id="abc05-3147">일부 암호</span><span class="sxs-lookup"><span data-stu-id="abc05-3147">some-password</span></span>
- <span data-ttu-id="abc05-3148">somepassword</span><span class="sxs-lookup"><span data-stu-id="abc05-3148">somepassword</span></span>
- <span data-ttu-id="abc05-3149">secretPassword</span><span class="sxs-lookup"><span data-stu-id="abc05-3149">secretPassword</span></span>
- <span data-ttu-id="abc05-3150">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3150">sample</span></span>

#### <a name="cep_passwordplaceholder"></a><span data-ttu-id="abc05-3151">CEP_PasswordPlaceHolder</span><span class="sxs-lookup"><span data-stu-id="abc05-3151">CEP_PasswordPlaceHolder</span></span>

<span data-ttu-id="abc05-3152">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3152">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-3153">암호나 pwd에 0-2 공백, 등호 (=), 0-2 공백 및 별표 (\*)-----------------------</span><span class="sxs-lookup"><span data-stu-id="abc05-3153">Password or pwd followed by 0-2 spaces, an equal sign (=), 0-2 spaces, and an asterisk (\*) --OR--</span></span>
- <span data-ttu-id="abc05-3154">암호나 pwd 뒤에 다음이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3154">Password or pwd followed by:</span></span>
    - <span data-ttu-id="abc05-3155">등호 (=)</span><span class="sxs-lookup"><span data-stu-id="abc05-3155">Equal sign (=)</span></span>
    - <span data-ttu-id="abc05-3156">보다 작음 기호 (<)</span><span class="sxs-lookup"><span data-stu-id="abc05-3156">Less than symbol (<)</span></span>
    - <span data-ttu-id="abc05-3157">대문자나 소문자, digits, 별표 (\*), 하이픈 (-), 밑줄 (_) 또는 공백 문자인 1-200 문자의 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-3157">Any combination of 1-200 characters that are upper- or lowercase letters, digits, an asterisk (\*), hyphen (-), underline (_), or whitespace character</span></span>
    - <span data-ttu-id="abc05-3158">보다 큼 기호 (>)</span><span class="sxs-lookup"><span data-stu-id="abc05-3158">Greater than symbol (>)</span></span>

#### <a name="cep_commonexamplekeywords"></a><span data-ttu-id="abc05-3159">CEP_CommonExampleKeywords</span><span class="sxs-lookup"><span data-stu-id="abc05-3159">CEP_CommonExampleKeywords</span></span>

<span data-ttu-id="abc05-3160">기술적으로이 중요 한 정보 유형은 키워드 목록이 아니라 정규식을 사용 하 여 이러한 키워드를 식별 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3160">(Note that technically, this sensitive information type identifies these keywords by using a regular expression, not a keyword list.)</span></span>

- <span data-ttu-id="abc05-3161">극동</span><span class="sxs-lookup"><span data-stu-id="abc05-3161">contoso</span></span>
- <span data-ttu-id="abc05-3162">fabrikam</span><span class="sxs-lookup"><span data-stu-id="abc05-3162">fabrikam</span></span>
- <span data-ttu-id="abc05-3163">대양</span><span class="sxs-lookup"><span data-stu-id="abc05-3163">northwind</span></span>
- <span data-ttu-id="abc05-3164">샌드박스</span><span class="sxs-lookup"><span data-stu-id="abc05-3164">sandbox</span></span>
- <span data-ttu-id="abc05-3165">용 onebox</span><span class="sxs-lookup"><span data-stu-id="abc05-3165">onebox</span></span>
- <span data-ttu-id="abc05-3166">로컬</span><span class="sxs-lookup"><span data-stu-id="abc05-3166">localhost</span></span>
- <span data-ttu-id="abc05-3167">127.0.0.1</span><span class="sxs-lookup"><span data-stu-id="abc05-3167">127.0.0.1</span></span>
- <span data-ttu-id="abc05-3168">testacs입니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3168">testacs.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-3169">ccw</span><span class="sxs-lookup"><span data-stu-id="abc05-3169">com</span></span>
- <span data-ttu-id="abc05-3170">s-int</span><span class="sxs-lookup"><span data-stu-id="abc05-3170">s-int.</span></span><!--no-hyperlink--><span data-ttu-id="abc05-3171">투자</span><span class="sxs-lookup"><span data-stu-id="abc05-3171">net</span></span>

## <a name="sweden-national-id"></a><span data-ttu-id="abc05-3172">스웨덴 국가 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-3172">Sweden National ID</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3173">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3173">Format</span></span>

<span data-ttu-id="abc05-3174">10 또는 12자리 숫자와 선택적 구분 기호</span><span class="sxs-lookup"><span data-stu-id="abc05-3174">10 or 12 digits and an optional delimiter</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3175">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3175">Pattern</span></span>

<span data-ttu-id="abc05-3176">10 또는 12자리 숫자와 선택적 구분 기호:</span><span class="sxs-lookup"><span data-stu-id="abc05-3176">10 or 12 digits and an optional delimiter:</span></span>
- <span data-ttu-id="abc05-3177">2-4자리 숫자(선택 사항)</span><span class="sxs-lookup"><span data-stu-id="abc05-3177">2-4 digits (optional)</span></span> 
- <span data-ttu-id="abc05-3178">YYMMDD 날짜 형식의 6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3178">Six digits in date format YYMMDD</span></span> 
- <span data-ttu-id="abc05-3179">구분 기호 "-" 또는 "+"(선택 사항) 및</span><span class="sxs-lookup"><span data-stu-id="abc05-3179">Delimiter of "-" or "+" (optional), plus</span></span>
- <span data-ttu-id="abc05-3180">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3180">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3181">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3181">Checksum</span></span>

<span data-ttu-id="abc05-3182">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3182">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3183">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3183">Definition</span></span>

<span data-ttu-id="abc05-3184">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3184">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3185">Func_swedish_national_identifier 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3185">The function Func_swedish_national_identifier finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3186">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3186">The checksum passes.</span></span>

```xml
<!-- Sweden National ID -->
<Entity id="f69aaf40-79be-4fac-8f05-fd1910d272c8" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_swedish_national_identifier" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3187">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3187">Keywords</span></span>

<span data-ttu-id="abc05-3188">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3188">No</span></span>
   
## <a name="sweden-passport-number"></a><span data-ttu-id="abc05-3189">스웨덴 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3189">Sweden Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3190">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3190">Format</span></span>

<span data-ttu-id="abc05-3191">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3191">Eight digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3192">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3192">Pattern</span></span>

<span data-ttu-id="abc05-3193">8자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3193">Eight consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3194">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3194">Checksum</span></span>

<span data-ttu-id="abc05-3195">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3195">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3196">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3196">Definition</span></span>

<span data-ttu-id="abc05-3197">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3197">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3198">Regex_sweden_passport_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3198">The regular expression Regex_sweden_passport_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3199">다음 중 하나가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3199">One of the following is true:</span></span>
    - <span data-ttu-id="abc05-3200">Keyword_passport의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3200">A keyword from Keyword_passport is found.</span></span>
    - <span data-ttu-id="abc05-3201">Keyword_sweden_passport의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3201">A keyword from Keyword_sweden_passport is found.</span></span>

```xml
<!-- Sweden Passport Number -->
<Entity id="ba4e7456-55a9-4d89-9140-c33673553526" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_sweden_passport_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_passport" />
          <Match idRef="Keyword_sweden_passport" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3202">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3202">Keywords</span></span>
   
#### <a name="keyword_sweden_passport"></a><span data-ttu-id="abc05-3203">Keyword_sweden_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-3203">Keyword_sweden_passport</span></span>

- <span data-ttu-id="abc05-3204">visa requirements</span><span class="sxs-lookup"><span data-stu-id="abc05-3204">visa requirements</span></span> 
- <span data-ttu-id="abc05-3205">Alien Registration Card</span><span class="sxs-lookup"><span data-stu-id="abc05-3205">Alien Registration Card</span></span> 
- <span data-ttu-id="abc05-3206">Schengen visas</span><span class="sxs-lookup"><span data-stu-id="abc05-3206">Schengen visas</span></span> 
- <span data-ttu-id="abc05-3207">Schengen visa</span><span class="sxs-lookup"><span data-stu-id="abc05-3207">Schengen visa</span></span> 
- <span data-ttu-id="abc05-3208">Visa Processing</span><span class="sxs-lookup"><span data-stu-id="abc05-3208">Visa Processing</span></span> 
- <span data-ttu-id="abc05-3209">Visa Type</span><span class="sxs-lookup"><span data-stu-id="abc05-3209">Visa Type</span></span> 
- <span data-ttu-id="abc05-3210">Single Entry</span><span class="sxs-lookup"><span data-stu-id="abc05-3210">Single Entry</span></span> 
- <span data-ttu-id="abc05-3211">Multiple Entry</span><span class="sxs-lookup"><span data-stu-id="abc05-3211">Multiple Entry</span></span> 
- <span data-ttu-id="abc05-3212">G3 Processing Fees</span><span class="sxs-lookup"><span data-stu-id="abc05-3212">G3 Processing Fees</span></span> 

#### <a name="keyword_passport"></a><span data-ttu-id="abc05-3213">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-3213">Keyword_passport</span></span>

- <span data-ttu-id="abc05-3214">Passport Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3214">Passport Number</span></span> 
- <span data-ttu-id="abc05-3215">Passport No</span><span class="sxs-lookup"><span data-stu-id="abc05-3215">Passport No</span></span> 
- <span data-ttu-id="abc05-3216">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-3216">Passport #</span></span> 
- <span data-ttu-id="abc05-3217">여권 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3217">Passport#</span></span> 
- <span data-ttu-id="abc05-3218">PassportID</span><span class="sxs-lookup"><span data-stu-id="abc05-3218">PassportID</span></span> 
- <span data-ttu-id="abc05-3219">Passportno</span><span class="sxs-lookup"><span data-stu-id="abc05-3219">Passportno</span></span> 
- <span data-ttu-id="abc05-3220">passportnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-3220">passportnumber</span></span> 
- <span data-ttu-id="abc05-3221">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-3221">パスポート</span></span> 
- <span data-ttu-id="abc05-3222">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-3222">パスポート番号</span></span> 
- <span data-ttu-id="abc05-3223">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-3223">パスポートのNum</span></span> 
- <span data-ttu-id="abc05-3224">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="abc05-3224">パスポート＃</span></span> 
- <span data-ttu-id="abc05-3225">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="abc05-3225">Numéro de passeport</span></span> 
- <span data-ttu-id="abc05-3226">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="abc05-3226">Passeport n °</span></span> 
- <span data-ttu-id="abc05-3227">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="abc05-3227">Passeport Non</span></span> 
- <span data-ttu-id="abc05-3228">Passeport #</span><span class="sxs-lookup"><span data-stu-id="abc05-3228">Passeport #</span></span> 
- <span data-ttu-id="abc05-3229">포트 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3229">Passeport#</span></span> 
- <span data-ttu-id="abc05-3230">지/포트 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-3230">PasseportNon</span></span> 
- <span data-ttu-id="abc05-3231">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="abc05-3231">Passeportn °</span></span> 
   
## <a name="swift-code"></a><span data-ttu-id="abc05-3232">SWIFT 코드</span><span class="sxs-lookup"><span data-stu-id="abc05-3232">SWIFT Code</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3233">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3233">Format</span></span>

<span data-ttu-id="abc05-3234">4개의 문자, 5-31개 문자 또는 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3234">Four letters followed by 5-31 letters or digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3235">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3235">Pattern</span></span>

<span data-ttu-id="abc05-3236">4개의 문자, 5-31개 문자 또는 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3236">Four letters followed by 5-31 letters or digits:</span></span>
- <span data-ttu-id="abc05-3237">4문자 은행 코드(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-3237">Four-letter bank code (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-3238">선택적 공백 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-3238">An optional space</span></span> 
- <span data-ttu-id="abc05-3239">4-28개 문자 또는 숫자[BBAN(기본 은행 계좌 번호)]</span><span class="sxs-lookup"><span data-stu-id="abc05-3239">4-28 letters or digits (the Basic Bank Account Number (BBAN))</span></span> 
- <span data-ttu-id="abc05-3240">선택적 공백 1개</span><span class="sxs-lookup"><span data-stu-id="abc05-3240">An optional space</span></span> 
- <span data-ttu-id="abc05-3241">1-3개 문자 또는 숫자(BBAN의 나머지)</span><span class="sxs-lookup"><span data-stu-id="abc05-3241">1-3 letters or digits (remainder of the BBAN)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3242">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3242">Checksum</span></span>

<span data-ttu-id="abc05-3243">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3243">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3244">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3244">Definition</span></span>

<span data-ttu-id="abc05-3245">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3245">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3246">Regex_swift 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3246">The regular expression Regex_swift finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3247">Keyword_swift의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3247">A keyword from Keyword_swift is found.</span></span>

```xml
<Entity id="cb2ab58c-9cb8-4c81-baf8-a4e106791df4" patternsProximity="300" recommendedConfidence="75">
<Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_swift" />
        <Match idRef="Keyword_swift" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3248">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3248">Keywords</span></span>
   
#### <a name="keyword_swift"></a><span data-ttu-id="abc05-3249">Keyword_swift</span><span class="sxs-lookup"><span data-stu-id="abc05-3249">Keyword_swift</span></span>

- <span data-ttu-id="abc05-3250">international organization for standardization 9362</span><span class="sxs-lookup"><span data-stu-id="abc05-3250">international organization for standardization 9362</span></span> 
- <span data-ttu-id="abc05-3251">iso 9362</span><span class="sxs-lookup"><span data-stu-id="abc05-3251">iso 9362</span></span> 
- <span data-ttu-id="abc05-3252">iso9362</span><span class="sxs-lookup"><span data-stu-id="abc05-3252">iso9362</span></span> 
- <span data-ttu-id="abc05-3253">swift\#</span><span class="sxs-lookup"><span data-stu-id="abc05-3253">swift\#</span></span> 
- <span data-ttu-id="abc05-3254">swiftcode</span><span class="sxs-lookup"><span data-stu-id="abc05-3254">swiftcode</span></span> 
- <span data-ttu-id="abc05-3255">swiftnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-3255">swiftnumber</span></span> 
- <span data-ttu-id="abc05-3256">swiftroutingnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-3256">swiftroutingnumber</span></span> 
- <span data-ttu-id="abc05-3257">swift code</span><span class="sxs-lookup"><span data-stu-id="abc05-3257">swift code</span></span> 
- <span data-ttu-id="abc05-3258">swift number #</span><span class="sxs-lookup"><span data-stu-id="abc05-3258">swift number #</span></span> 
- <span data-ttu-id="abc05-3259">swift routing number</span><span class="sxs-lookup"><span data-stu-id="abc05-3259">swift routing number</span></span> 
- <span data-ttu-id="abc05-3260">bic number</span><span class="sxs-lookup"><span data-stu-id="abc05-3260">bic number</span></span> 
- <span data-ttu-id="abc05-3261">bic code</span><span class="sxs-lookup"><span data-stu-id="abc05-3261">bic code</span></span> 
- <span data-ttu-id="abc05-3262">bic\#</span><span class="sxs-lookup"><span data-stu-id="abc05-3262">bic \#</span></span> 
- <span data-ttu-id="abc05-3263">bic\#</span><span class="sxs-lookup"><span data-stu-id="abc05-3263">bic\#</span></span> 
- <span data-ttu-id="abc05-3264">bank identifier code</span><span class="sxs-lookup"><span data-stu-id="abc05-3264">bank identifier code</span></span> 
- <span data-ttu-id="abc05-3265">標準化 9362</span><span class="sxs-lookup"><span data-stu-id="abc05-3265">標準化9362</span></span> 
- <span data-ttu-id="abc05-3266">迅速＃</span><span class="sxs-lookup"><span data-stu-id="abc05-3266">迅速＃</span></span> 
- <span data-ttu-id="abc05-3267">SWIFTコード</span><span class="sxs-lookup"><span data-stu-id="abc05-3267">SWIFTコード</span></span> 
- <span data-ttu-id="abc05-3268">SWIFT番号</span><span class="sxs-lookup"><span data-stu-id="abc05-3268">SWIFT番号</span></span> 
- <span data-ttu-id="abc05-3269">迅速なルーティング番号</span><span class="sxs-lookup"><span data-stu-id="abc05-3269">迅速なルーティング番号</span></span> 
- <span data-ttu-id="abc05-3270">BIC番号</span><span class="sxs-lookup"><span data-stu-id="abc05-3270">BIC番号</span></span> 
- <span data-ttu-id="abc05-3271">BICコード</span><span class="sxs-lookup"><span data-stu-id="abc05-3271">BICコード</span></span> 
- <span data-ttu-id="abc05-3272">銀行識別コードのための国際組織</span><span class="sxs-lookup"><span data-stu-id="abc05-3272">銀行識別コードのための国際組織</span></span> 
- <span data-ttu-id="abc05-3273">Organisation internationale de normalisation 9362</span><span class="sxs-lookup"><span data-stu-id="abc05-3273">Organisation internationale de normalisation 9362</span></span> 
- <span data-ttu-id="abc05-3274">rapide\#</span><span class="sxs-lookup"><span data-stu-id="abc05-3274">rapide \#</span></span> 
- <span data-ttu-id="abc05-3275">code SWIFT</span><span class="sxs-lookup"><span data-stu-id="abc05-3275">code SWIFT</span></span> 
- <span data-ttu-id="abc05-3276">le numéro de swift</span><span class="sxs-lookup"><span data-stu-id="abc05-3276">le numéro de swift</span></span> 
- <span data-ttu-id="abc05-3277">swift numéro d'acheminement</span><span class="sxs-lookup"><span data-stu-id="abc05-3277">swift numéro d'acheminement</span></span> 
- <span data-ttu-id="abc05-3278">le numéro BIC</span><span class="sxs-lookup"><span data-stu-id="abc05-3278">le numéro BIC</span></span> 
- <span data-ttu-id="abc05-3279">\#BIC</span><span class="sxs-lookup"><span data-stu-id="abc05-3279">\# BIC</span></span> 
- <span data-ttu-id="abc05-3280">code identificateur de banque</span><span class="sxs-lookup"><span data-stu-id="abc05-3280">code identificateur de banque</span></span> 
   
## <a name="taiwan-national-id"></a><span data-ttu-id="abc05-3281">대만 국가 ID</span><span class="sxs-lookup"><span data-stu-id="abc05-3281">Taiwan National ID</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3282">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3282">Format</span></span>

<span data-ttu-id="abc05-3283">1개의 문자, 9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3283">One letter (in English) followed by nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3284">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3284">Pattern</span></span>

<span data-ttu-id="abc05-3285">1개의 문자, 9자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3285">One letter (in English) followed by nine digits:</span></span>
- <span data-ttu-id="abc05-3286">1개 문자(영문, 대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-3286">One letter (in English, not case sensitive)</span></span> 
- <span data-ttu-id="abc05-3287">숫자 "1" 또는 "2"</span><span class="sxs-lookup"><span data-stu-id="abc05-3287">The digit "1" or "2"</span></span> 
- <span data-ttu-id="abc05-3288">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3288">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3289">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3289">Checksum</span></span>

<span data-ttu-id="abc05-3290">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3290">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3291">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3291">Definition</span></span>

<span data-ttu-id="abc05-3292">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3292">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3293">Func_taiwanese_national_id 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3293">The function Func_taiwanese_national_id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3294">Keyword_taiwanese_national_id의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3294">A keyword from Keyword_taiwanese_national_id is found.</span></span>
- <span data-ttu-id="abc05-3295">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3295">The checksum passes.</span></span>

```xml
<!-- Taiwanese National ID -->
<Entity id="4C7BFC34-8DD1-421D-8FB7-6C6182C2AF03" patternsProximity="300" recommendedConfidence="85">
      <Pattern confidenceLevel="85">
          <IdMatch idRef="Func_taiwanese_national_id" />
          <Match idRef="Keyword_taiwanese_national_id" />
      </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3296">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3296">Keywords</span></span>

#### <a name="keyword_taiwanese_national_id"></a><span data-ttu-id="abc05-3297">Keyword_taiwanese_national_id</span><span class="sxs-lookup"><span data-stu-id="abc05-3297">Keyword_taiwanese_national_id</span></span>

- <span data-ttu-id="abc05-3298">身份證字號</span><span class="sxs-lookup"><span data-stu-id="abc05-3298">身份證字號</span></span> 
- <span data-ttu-id="abc05-3299">身份證</span><span class="sxs-lookup"><span data-stu-id="abc05-3299">身份證</span></span> 
- <span data-ttu-id="abc05-3300">身份證號碼</span><span class="sxs-lookup"><span data-stu-id="abc05-3300">身份證號碼</span></span> 
- <span data-ttu-id="abc05-3301">身份證號</span><span class="sxs-lookup"><span data-stu-id="abc05-3301">身份證號</span></span> 
- <span data-ttu-id="abc05-3302">身分證字號</span><span class="sxs-lookup"><span data-stu-id="abc05-3302">身分證字號</span></span> 
- <span data-ttu-id="abc05-3303">身分證</span><span class="sxs-lookup"><span data-stu-id="abc05-3303">身分證</span></span> 
- <span data-ttu-id="abc05-3304">身分證號碼</span><span class="sxs-lookup"><span data-stu-id="abc05-3304">身分證號碼</span></span> 
- <span data-ttu-id="abc05-3305">身份證號</span><span class="sxs-lookup"><span data-stu-id="abc05-3305">身份證號</span></span> 
- <span data-ttu-id="abc05-3306">身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="abc05-3306">身分證統一編號</span></span> 
- <span data-ttu-id="abc05-3307">國民身分證統一編號</span><span class="sxs-lookup"><span data-stu-id="abc05-3307">國民身分證統一編號</span></span> 
- <span data-ttu-id="abc05-3308">簽名</span><span class="sxs-lookup"><span data-stu-id="abc05-3308">簽名</span></span> 
- <span data-ttu-id="abc05-3309">蓋章</span><span class="sxs-lookup"><span data-stu-id="abc05-3309">蓋章</span></span> 
- <span data-ttu-id="abc05-3310">簽名或蓋章</span><span class="sxs-lookup"><span data-stu-id="abc05-3310">簽名或蓋章</span></span> 
- <span data-ttu-id="abc05-3311">簽章</span><span class="sxs-lookup"><span data-stu-id="abc05-3311">簽章</span></span>   
   
## <a name="taiwan-passport-number"></a><span data-ttu-id="abc05-3312">	대만 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3312">Taiwan Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3313">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3313">Format</span></span>

- <span data-ttu-id="abc05-3314">생체 인식 여권 번호: 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3314">Biometric passport number: Nine digits</span></span>
- <span data-ttu-id="abc05-3315">비-생체 인식 여권 번호: 9 자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3315">Non-biometric passport number: Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3316">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3316">Pattern</span></span>
<span data-ttu-id="abc05-3317">생체 인식 여권 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-3317">Biometric passport number:</span></span>
- <span data-ttu-id="abc05-3318">숫자 "3" </span><span class="sxs-lookup"><span data-stu-id="abc05-3318">The digit "3"</span></span> 
- <span data-ttu-id="abc05-3319">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3319">Eight digits</span></span>

<span data-ttu-id="abc05-3320">비-생체 인식 여권 번호:</span><span class="sxs-lookup"><span data-stu-id="abc05-3320">Non-biometric passport number:</span></span>
- <span data-ttu-id="abc05-3321">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3321">Nine digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3322">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3322">Checksum</span></span>

<span data-ttu-id="abc05-3323">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3323">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3324">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3324">Definition</span></span>

<span data-ttu-id="abc05-3325">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3325">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3326">정규식 Regex_taiwan_passport 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3326">The regular expression Regex_taiwan_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3327">Keyword_taiwan_passport에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3327">A keyword from Keyword_taiwan_passport is found.</span></span>

```xml
<!-- Taiwan Passport Number -->
<Entity id="e7251cb4-4c2c-41df-963e-924eb3dae04a" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_passport"/>
     <Match idRef="Keyword_taiwan_passport"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3328">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3328">Keywords</span></span>

#### <a name="keyword_taiwan_passport"></a><span data-ttu-id="abc05-3329">Keyword_taiwan_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-3329">Keyword_taiwan_passport</span></span>

- <span data-ttu-id="abc05-3330">ROC passport number</span><span class="sxs-lookup"><span data-stu-id="abc05-3330">ROC passport number</span></span> 
- <span data-ttu-id="abc05-3331">Passport number</span><span class="sxs-lookup"><span data-stu-id="abc05-3331">Passport number</span></span> 
- <span data-ttu-id="abc05-3332">Passport no</span><span class="sxs-lookup"><span data-stu-id="abc05-3332">Passport no</span></span> 
- <span data-ttu-id="abc05-3333">Passport Num</span><span class="sxs-lookup"><span data-stu-id="abc05-3333">Passport Num</span></span> 
- <span data-ttu-id="abc05-3334">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-3334">Passport #</span></span> 
- <span data-ttu-id="abc05-3335">护照</span><span class="sxs-lookup"><span data-stu-id="abc05-3335">护照</span></span> 
- <span data-ttu-id="abc05-3336">中華民國護照</span><span class="sxs-lookup"><span data-stu-id="abc05-3336">中華民國護照</span></span> 
- <span data-ttu-id="abc05-3337">Zhōnghuá Mínguó hùzhào</span><span class="sxs-lookup"><span data-stu-id="abc05-3337">Zhōnghuá Mínguó hùzhào</span></span>
   
## <a name="taiwan-resident-certificate-arctarc-number"></a><span data-ttu-id="abc05-3338">대만 거주 인증(ARC/TARC) 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3338">Taiwan Resident Certificate (ARC/TARC) Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3339">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3339">Format</span></span>

<span data-ttu-id="abc05-3340">10개의 문자 및 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3340">10 letters and digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3341">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3341">Pattern</span></span>

<span data-ttu-id="abc05-3342">10개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3342">10 letters and digits:</span></span>
- <span data-ttu-id="abc05-3343">2문자(대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-3343">Two letters (not case sensitive)</span></span> 
- <span data-ttu-id="abc05-3344">8자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3344">Eight digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3345">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3345">Checksum</span></span>

<span data-ttu-id="abc05-3346">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3346">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3347">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3347">Definition</span></span>

<span data-ttu-id="abc05-3348">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3348">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3349">정규식 Regex_taiwan_resident_certificate 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3349">The regular expression Regex_taiwan_resident_certificate finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3350">Keyword_taiwan_resident_certificate에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3350">A keyword from Keyword_taiwan_resident_certificate is found.</span></span>

```xml
<!-- Taiwan Resident Certificate (ARC/TARC) -->
<Entity id="48269fec-05ea-46ea-b326-f5623a58c6e9" recommendedConfidence="75" patternsProximity="300">
  <Pattern confidenceLevel="75">
     <IdMatch idRef="Regex_taiwan_resident_certificate"/>
     <Match idRef="Keyword_taiwan_resident_certificate"/>
  </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3351">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3351">Keywords</span></span>

#### <a name="keyword_taiwan_resident_certificate"></a><span data-ttu-id="abc05-3352">Keyword_taiwan_resident_certificate</span><span class="sxs-lookup"><span data-stu-id="abc05-3352">Keyword_taiwan_resident_certificate</span></span>

- <span data-ttu-id="abc05-3353">Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="abc05-3353">Resident Certificate</span></span> 
- <span data-ttu-id="abc05-3354">Resident Cert</span><span class="sxs-lookup"><span data-stu-id="abc05-3354">Resident Cert</span></span> 
- <span data-ttu-id="abc05-3355">Resident Cert.</span><span class="sxs-lookup"><span data-stu-id="abc05-3355">Resident Cert.</span></span> 
- <span data-ttu-id="abc05-3356">Identification card</span><span class="sxs-lookup"><span data-stu-id="abc05-3356">Identification card</span></span> 
- <span data-ttu-id="abc05-3357">Alien Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="abc05-3357">Alien Resident Certificate</span></span> 
- <span data-ttu-id="abc05-3358">ARC</span><span class="sxs-lookup"><span data-stu-id="abc05-3358">ARC</span></span> 
- <span data-ttu-id="abc05-3359">Taiwan Area Resident Certificate</span><span class="sxs-lookup"><span data-stu-id="abc05-3359">Taiwan Area Resident Certificate</span></span> 
- <span data-ttu-id="abc05-3360">TARC</span><span class="sxs-lookup"><span data-stu-id="abc05-3360">TARC</span></span> 
- <span data-ttu-id="abc05-3361">居留證</span><span class="sxs-lookup"><span data-stu-id="abc05-3361">居留證</span></span> 
- <span data-ttu-id="abc05-3362">外僑居留證</span><span class="sxs-lookup"><span data-stu-id="abc05-3362">外僑居留證</span></span> 
- <span data-ttu-id="abc05-3363">台灣地區居留證</span><span class="sxs-lookup"><span data-stu-id="abc05-3363">台灣地區居留證</span></span> 

## <a name="thai-population-identification-code"></a><span data-ttu-id="abc05-3364">태국어 인구 식별 코드</span><span class="sxs-lookup"><span data-stu-id="abc05-3364">Thai Population Identification Code</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3365">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3365">Format</span></span>

<span data-ttu-id="abc05-3366">13자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3366">13 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3367">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3367">Pattern</span></span>

<span data-ttu-id="abc05-3368">13자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3368">13 digits:</span></span>
- <span data-ttu-id="abc05-3369">첫 번째 숫자가 0 또는 9가 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-3369">First digit is not 0 or 9</span></span> 
- <span data-ttu-id="abc05-3370">12자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3370">12 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3371">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3371">Checksum</span></span>

<span data-ttu-id="abc05-3372">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3372">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3373">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3373">Definition</span></span>

<span data-ttu-id="abc05-3374">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3374">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3375">Func_Thai_Citizen_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3375">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3376">Keyword_Thai_Citizen_Id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3376">A keyword from Keyword_Thai_Citizen_Id is found.</span></span>

<span data-ttu-id="abc05-3377">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3377">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3378">Func_Thai_Citizen_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3378">The function Func_Thai_Citizen_Id finds content that matches the pattern.</span></span>

```xml
<!-- Thai Citizen ID -->
-<Entity id="44ca9e86-ead7-4c5d-884a-e2eaa401515e" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
      <Match idRef="Keyword_Thai_Citizen_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Thai_Citizen_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3379">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3379">Keywords</span></span>

#### <a name="keyword_thai_citizen_id"></a><span data-ttu-id="abc05-3380">Keyword_Thai_Citizen_Id</span><span class="sxs-lookup"><span data-stu-id="abc05-3380">Keyword_Thai_Citizen_Id</span></span>

- <span data-ttu-id="abc05-3381">ID Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3381">ID Number</span></span>
- <span data-ttu-id="abc05-3382">Id 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3382">Identification Number</span></span>
- <span data-ttu-id="abc05-3383">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="abc05-3383">บัตรประชาชน</span></span>
- <span data-ttu-id="abc05-3384">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="abc05-3384">รหัสบัตรประชาชน</span></span>
- <span data-ttu-id="abc05-3385">บัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="abc05-3385">บัตรประชาชน</span></span>
- <span data-ttu-id="abc05-3386">รหัสบัตรประชาชน</span><span class="sxs-lookup"><span data-stu-id="abc05-3386">รหัสบัตรประชาชน</span></span>
  
## <a name="turkish-national-identification-number"></a><span data-ttu-id="abc05-3387">터키어 국가 식별 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3387">Turkish National Identification Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3388">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3388">Format</span></span>

<span data-ttu-id="abc05-3389">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3389">11 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3390">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3390">Pattern</span></span>

<span data-ttu-id="abc05-3391">11자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3391">11 digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3392">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3392">Checksum</span></span>

<span data-ttu-id="abc05-3393">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3393">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3394">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3394">Definition</span></span>

<span data-ttu-id="abc05-3395">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3395">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3396">Func_Turkish_National_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3396">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3397">Keyword_Turkish_National_Id에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3397">A keyword from Keyword_Turkish_National_Id is found.</span></span>

<span data-ttu-id="abc05-3398">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3398">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3399">Func_Turkish_National_Id 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3399">The function Func_Turkish_National_Id finds content that matches the pattern.</span></span>

```xml
<!-- Turkish National Identity -->
-<Entity id="fb621f20-3876-4cfc-acec-8c8e73ca32c7" recommendedConfidence="75" patternsProximity="300">
   -<Pattern confidenceLevel="85">
      <IdMatch idRef="Func_Turkish_National_Id"/>
      <Match idRef="Keyword_Turkish_National_Id"/>
   </Pattern>
   -<Pattern confidenceLevel="75">
      <IdMatch idRef="Func_Turkish_National_Id"/>
   </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3400">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3400">Keywords</span></span>

#### <a name="keyword_turkish_national_id"></a><span data-ttu-id="abc05-3401">Keyword_Turkish_National_Id</span><span class="sxs-lookup"><span data-stu-id="abc05-3401">Keyword_Turkish_National_Id</span></span>

- <span data-ttu-id="abc05-3402">TC Kimlik 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3402">TC Kimlik No</span></span>
- <span data-ttu-id="abc05-3403">TC Kimlik numarası</span><span class="sxs-lookup"><span data-stu-id="abc05-3403">TC Kimlik numarası</span></span>
- <span data-ttu-id="abc05-3404">Vatandaşlık numarası</span><span class="sxs-lookup"><span data-stu-id="abc05-3404">Vatandaşlık numarası</span></span>
- <span data-ttu-id="abc05-3405">Vatandaşlık 아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3405">Vatandaşlık no</span></span>

## <a name="uk-drivers-license-number"></a><span data-ttu-id="abc05-p144">영국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-p144">U.K. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3408">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3408">Format</span></span>

<span data-ttu-id="abc05-3409">지정된 형식의 18개 문자 및 숫자 조합</span><span class="sxs-lookup"><span data-stu-id="abc05-3409">Combination of 18 letters and digits in the specified format</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3410">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3410">Pattern</span></span>

<span data-ttu-id="abc05-3411">18개의 문자 및 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3411">18 letters and digits:</span></span>
- <span data-ttu-id="abc05-3412">5개 문자(대/소문자 구분 안 함) 또는 문자 대신 숫자 "9" 사용</span><span class="sxs-lookup"><span data-stu-id="abc05-3412">Five letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="abc05-3413">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3413">One digit</span></span> 
- <span data-ttu-id="abc05-3414">날짜 형식의 5 자리 숫자 MMDDY 생년월일 (드라이버가 암 인 경우 50이 고 62 51은 01부터 12까지)로 증가 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3414">Five digits in the date format MMDDY for date of birth (7th character is incremented by 50 if driver is female, i.e. 51 to 62 instead of 01 to 12)</span></span>
- <span data-ttu-id="abc05-3415">2개 문자(대/소문자 구분 안 함) 또는 문자 대신 숫자 "9" 사용</span><span class="sxs-lookup"><span data-stu-id="abc05-3415">Two letters (not case sensitive) or the digit "9" in place of a letter</span></span> 
- <span data-ttu-id="abc05-3416">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3416">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3417">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3417">Checksum</span></span>

<span data-ttu-id="abc05-3418">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3418">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3419">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3419">Definition</span></span>

<span data-ttu-id="abc05-3420">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3420">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3421">Func_uk_drivers_license 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3421">The function Func_uk_drivers_license finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3422">Keyword_uk_drivers_license의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3422">A keyword from Keyword_uk_drivers_license is found.</span></span>
- <span data-ttu-id="abc05-3423">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3423">The checksum passes.</span></span>

```xml
<!-- U.K. Driver's License Number -->
<Entity id="f93de4be-d94c-40df-a8be-461738047551" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_drivers_license" />
        <Match idRef="Keyword_uk_drivers_license" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3424">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3424">Keywords</span></span>

#### <a name="keyword_uk_drivers_license"></a><span data-ttu-id="abc05-3425">Keyword_uk_drivers_license</span><span class="sxs-lookup"><span data-stu-id="abc05-3425">Keyword_uk_drivers_license</span></span>

- <span data-ttu-id="abc05-3426">DVLA</span><span class="sxs-lookup"><span data-stu-id="abc05-3426">DVLA</span></span> 
- <span data-ttu-id="abc05-3427">light vans</span><span class="sxs-lookup"><span data-stu-id="abc05-3427">light vans</span></span> 
- <span data-ttu-id="abc05-3428">quadbikes</span><span class="sxs-lookup"><span data-stu-id="abc05-3428">quadbikes</span></span> 
- <span data-ttu-id="abc05-3429">motor cars</span><span class="sxs-lookup"><span data-stu-id="abc05-3429">motor cars</span></span> 
- <span data-ttu-id="abc05-3430">125cc</span><span class="sxs-lookup"><span data-stu-id="abc05-3430">125cc</span></span> 
- <span data-ttu-id="abc05-3431">sidecar</span><span class="sxs-lookup"><span data-stu-id="abc05-3431">sidecar</span></span> 
- <span data-ttu-id="abc05-3432">tricycles</span><span class="sxs-lookup"><span data-stu-id="abc05-3432">tricycles</span></span> 
- <span data-ttu-id="abc05-3433">motorcycles</span><span class="sxs-lookup"><span data-stu-id="abc05-3433">motorcycles</span></span> 
- <span data-ttu-id="abc05-3434">photocard licence</span><span class="sxs-lookup"><span data-stu-id="abc05-3434">photocard licence</span></span> 
- <span data-ttu-id="abc05-3435">learner drivers</span><span class="sxs-lookup"><span data-stu-id="abc05-3435">learner drivers</span></span> 
- <span data-ttu-id="abc05-3436">licence holder</span><span class="sxs-lookup"><span data-stu-id="abc05-3436">licence holder</span></span> 
- <span data-ttu-id="abc05-3437">licence holders</span><span class="sxs-lookup"><span data-stu-id="abc05-3437">licence holders</span></span> 
- <span data-ttu-id="abc05-3438">driving licences</span><span class="sxs-lookup"><span data-stu-id="abc05-3438">driving licences</span></span> 
- <span data-ttu-id="abc05-3439">driving licence</span><span class="sxs-lookup"><span data-stu-id="abc05-3439">driving licence</span></span> 
- <span data-ttu-id="abc05-3440">dual control car</span><span class="sxs-lookup"><span data-stu-id="abc05-3440">dual control car</span></span> 
   
## <a name="uk-electoral-roll-number"></a><span data-ttu-id="abc05-p145">영국 선거 롤 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-p145">U.K. Electoral Roll Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3443">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3443">Format</span></span>

<span data-ttu-id="abc05-3444">2개의 문자, 1-4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3444">Two letters followed by 1-4 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3445">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3445">Pattern</span></span>

<span data-ttu-id="abc05-3446">2개의 문자(대/소문자 구분 안 함)와 1-4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3446">Two letters (not case sensitive) followed by 1-4 numbers</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3447">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3447">Checksum</span></span>

<span data-ttu-id="abc05-3448">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3448">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3449">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3449">Definition</span></span>

<span data-ttu-id="abc05-3450">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3450">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3451">Regex_uk_electoral 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3451">The regular expression Regex_uk_electoral finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3452">Keyword_uk_electoral의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3452">A keyword from Keyword_uk_electoral is found.</span></span>

```xml
<!-- U.K. Electoral Number -->
<Entity id="a3eea206-dc0c-4f06-9e22-aa1be3059963" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_uk_electoral" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_electoral" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3453">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3453">Keywords</span></span>

#### <a name="keyword_uk_electoral"></a><span data-ttu-id="abc05-3454">Keyword_uk_electoral</span><span class="sxs-lookup"><span data-stu-id="abc05-3454">Keyword_uk_electoral</span></span>

- <span data-ttu-id="abc05-3455">council nomination</span><span class="sxs-lookup"><span data-stu-id="abc05-3455">council nomination</span></span> 
- <span data-ttu-id="abc05-3456">nomination form</span><span class="sxs-lookup"><span data-stu-id="abc05-3456">nomination form</span></span> 
- <span data-ttu-id="abc05-3457">electoral register</span><span class="sxs-lookup"><span data-stu-id="abc05-3457">electoral register</span></span> 
- <span data-ttu-id="abc05-3458">electoral roll</span><span class="sxs-lookup"><span data-stu-id="abc05-3458">electoral roll</span></span>

   
## <a name="uk-national-health-service-number"></a><span data-ttu-id="abc05-p146">영국 국립 보건 서비스 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-p146">U.K. National Health Service Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3461">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3461">Format</span></span>

<span data-ttu-id="abc05-3462">공백으로 구분된 10-17자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3462">10-17 digits separated by spaces</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3463">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3463">Pattern</span></span>

<span data-ttu-id="abc05-3464">10-17자리 숫자:</span><span class="sxs-lookup"><span data-stu-id="abc05-3464">10-17 digits:</span></span>
- <span data-ttu-id="abc05-3465">3 또는 10자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3465">Either 3 or 10 digits</span></span> 
- <span data-ttu-id="abc05-3466">공백</span><span class="sxs-lookup"><span data-stu-id="abc05-3466">A space</span></span> 
- <span data-ttu-id="abc05-3467">3자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3467">Three digits</span></span> 
- <span data-ttu-id="abc05-3468">공백</span><span class="sxs-lookup"><span data-stu-id="abc05-3468">A space</span></span> 
- <span data-ttu-id="abc05-3469">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3469">Four digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3470">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3470">Checksum</span></span>

<span data-ttu-id="abc05-3471">예</span><span class="sxs-lookup"><span data-stu-id="abc05-3471">Yes</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3472">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3472">Definition</span></span>

<span data-ttu-id="abc05-3473">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3473">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3474">Func_uk_nhs_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3474">The function Func_uk_nhs_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3475">다음 중 하나가 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3475">One of the following is true:</span></span>
    - <span data-ttu-id="abc05-3476">Keyword_uk_nhs_number의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3476">A keyword from Keyword_uk_nhs_number is found.</span></span>
    - <span data-ttu-id="abc05-3477">Keyword_uk_nhs_number1의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3477">A keyword from Keyword_uk_nhs_number1 is found.</span></span>
    - <span data-ttu-id="abc05-3478">Keyword_uk_nhs_number_dob의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3478">A keyword from Keyword_uk_nhs_number_dob is found.</span></span>
- <span data-ttu-id="abc05-3479">체크섬이 통과됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3479">The checksum passes.</span></span>

```xml
<!-- U.K. NHS Number -->
<Entity id="3192014e-2a16-44e9-aa69-4b20375c9a78" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nhs_number" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nhs_number" />
          <Match idRef="Keyword_uk_nhs_number1" />
          <Match idRef="Keyword_uk_nhs_number_dob" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3480">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3480">Keywords</span></span>
   
#### <a name="keyword_uk_nhs_number"></a><span data-ttu-id="abc05-3481">Keyword_uk_nhs_number</span><span class="sxs-lookup"><span data-stu-id="abc05-3481">Keyword_uk_nhs_number</span></span>

- <span data-ttu-id="abc05-3482">국립 보건 서비스</span><span class="sxs-lookup"><span data-stu-id="abc05-3482">national health service</span></span> 
- <span data-ttu-id="abc05-3483">nhs</span><span class="sxs-lookup"><span data-stu-id="abc05-3483">nhs</span></span> 
- <span data-ttu-id="abc05-3484">health services authority</span><span class="sxs-lookup"><span data-stu-id="abc05-3484">health services authority</span></span> 
- <span data-ttu-id="abc05-3485">health authority</span><span class="sxs-lookup"><span data-stu-id="abc05-3485">health authority</span></span>

#### <a name="keyword_uk_nhs_number1"></a><span data-ttu-id="abc05-3486">Keyword_uk_nhs_number1</span><span class="sxs-lookup"><span data-stu-id="abc05-3486">Keyword_uk_nhs_number1</span></span>

- <span data-ttu-id="abc05-3487">patient id</span><span class="sxs-lookup"><span data-stu-id="abc05-3487">patient id</span></span> 
- <span data-ttu-id="abc05-3488">patient identification</span><span class="sxs-lookup"><span data-stu-id="abc05-3488">patient identification</span></span> 
- <span data-ttu-id="abc05-3489">patient no</span><span class="sxs-lookup"><span data-stu-id="abc05-3489">patient no</span></span> 
- <span data-ttu-id="abc05-3490">patient number</span><span class="sxs-lookup"><span data-stu-id="abc05-3490">patient number</span></span>

#### <a name="keyword_uk_nhs_number_dob"></a><span data-ttu-id="abc05-3491">Keyword_uk_nhs_number_dob</span><span class="sxs-lookup"><span data-stu-id="abc05-3491">Keyword_uk_nhs_number_dob</span></span>

- <span data-ttu-id="abc05-3492">G</span><span class="sxs-lookup"><span data-stu-id="abc05-3492">GP</span></span> 
- <span data-ttu-id="abc05-3493">DOB</span><span class="sxs-lookup"><span data-stu-id="abc05-3493">DOB</span></span> 
- <span data-ttu-id="abc05-3494">D. O. B</span><span class="sxs-lookup"><span data-stu-id="abc05-3494">D.O.B</span></span> 
- <span data-ttu-id="abc05-3495">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="abc05-3495">Date of Birth</span></span> 
- <span data-ttu-id="abc05-3496">Birth Date</span><span class="sxs-lookup"><span data-stu-id="abc05-3496">Birth Date</span></span> 
   
## <a name="uk-national-insurance-number-nino"></a><span data-ttu-id="abc05-p147">영국 NINO(국민 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-p147">U.K. National Insurance Number (NINO)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3499">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3499">Format</span></span>

<span data-ttu-id="abc05-3500">공백 또는 대시로 구분 된 7 자 또는 9 자</span><span class="sxs-lookup"><span data-stu-id="abc05-3500">7 characters or 9 characters separated by spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3501">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3501">Pattern</span></span>

<span data-ttu-id="abc05-3502">다음과 같은 두 가지 패턴을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3502">Two possible patterns:</span></span>

- <span data-ttu-id="abc05-3503">두 문자 (유효한 NINOs이 접두사의 특정 문자만 사용 하며이 패턴의 유효성 검사는 대/소문자를 구분 하지 않음)</span><span class="sxs-lookup"><span data-stu-id="abc05-3503">Two letters (valid NINOs use only certain characters in this prefix, which this pattern validates; not case sensitive)</span></span>
- <span data-ttu-id="abc05-3504">6자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3504">Six digits</span></span>
- <span data-ttu-id="abc05-3505">' A ', ' B ', ' C ' 또는 ' d ' (접두사와 마찬가지로 접미사에서는 특정 문자만 허용 되며 대/소문자 구분 안 함)</span><span class="sxs-lookup"><span data-stu-id="abc05-3505">Either 'A', 'B', 'C', or 'D' (like the prefix, only certain characters are allowed in the suffix; not case sensitive)</span></span>

<span data-ttu-id="abc05-3506">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-3506">OR</span></span>

- <span data-ttu-id="abc05-3507">2 개 문자</span><span class="sxs-lookup"><span data-stu-id="abc05-3507">Two letters</span></span>
- <span data-ttu-id="abc05-3508">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3508">A space or dash</span></span>
- <span data-ttu-id="abc05-3509">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3509">Two digits</span></span>
- <span data-ttu-id="abc05-3510">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3510">A space or dash</span></span>
- <span data-ttu-id="abc05-3511">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3511">Two digits</span></span>
- <span data-ttu-id="abc05-3512">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3512">A space or dash</span></span>
- <span data-ttu-id="abc05-3513">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3513">Two digits</span></span>
- <span data-ttu-id="abc05-3514">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3514">A space or dash</span></span>
- <span data-ttu-id="abc05-3515">' A ', ' B ', ' C ' 또는 ' d ' 중 하나</span><span class="sxs-lookup"><span data-stu-id="abc05-3515">Either 'A', 'B', 'C', or 'D'</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3516">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3516">Checksum</span></span>

<span data-ttu-id="abc05-3517">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3517">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3518">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3518">Definition</span></span>

<span data-ttu-id="abc05-3519">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3519">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3520">Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3520">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3521">Keyword_uk_nino의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3521">A keyword from Keyword_uk_nino is found.</span></span>

<span data-ttu-id="abc05-3522">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3522">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3523">Func_uk_nino 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3523">The function Func_uk_nino finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3524">Keyword_uk_nino의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3524">No keyword from Keyword_uk_nino is found.</span></span>

```xml
<!-- U.K. NINO -->
<Entity id="16c07343-c26f-49d2-a987-3daf717e94cc" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="1">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>    
     <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_uk_nino" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_uk_nino" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3525">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3525">Keywords</span></span>

#### <a name="keyword_uk_nino"></a><span data-ttu-id="abc05-3526">Keyword_uk_nino</span><span class="sxs-lookup"><span data-stu-id="abc05-3526">Keyword_uk_nino</span></span>

- <span data-ttu-id="abc05-3527">national insurance number</span><span class="sxs-lookup"><span data-stu-id="abc05-3527">national insurance number</span></span> 
- <span data-ttu-id="abc05-3528">national insurance contributions</span><span class="sxs-lookup"><span data-stu-id="abc05-3528">national insurance contributions</span></span> 
- <span data-ttu-id="abc05-3529">protection act</span><span class="sxs-lookup"><span data-stu-id="abc05-3529">protection act</span></span> 
- <span data-ttu-id="abc05-3530">소유권</span><span class="sxs-lookup"><span data-stu-id="abc05-3530">insurance</span></span> 
- <span data-ttu-id="abc05-3531">social security number</span><span class="sxs-lookup"><span data-stu-id="abc05-3531">social security number</span></span> 
- <span data-ttu-id="abc05-3532">insurance application</span><span class="sxs-lookup"><span data-stu-id="abc05-3532">insurance application</span></span> 
- <span data-ttu-id="abc05-3533">medical application</span><span class="sxs-lookup"><span data-stu-id="abc05-3533">medical application</span></span> 
- <span data-ttu-id="abc05-3534">social insurance</span><span class="sxs-lookup"><span data-stu-id="abc05-3534">social insurance</span></span> 
- <span data-ttu-id="abc05-3535">medical attention</span><span class="sxs-lookup"><span data-stu-id="abc05-3535">medical attention</span></span> 
- <span data-ttu-id="abc05-3536">social security</span><span class="sxs-lookup"><span data-stu-id="abc05-3536">social security</span></span> 
- <span data-ttu-id="abc05-3537">great britain</span><span class="sxs-lookup"><span data-stu-id="abc05-3537">great britain</span></span> 
- <span data-ttu-id="abc05-3538">소유권</span><span class="sxs-lookup"><span data-stu-id="abc05-3538">insurance</span></span>    
   
## <a name="us--uk-passport-number"></a><span data-ttu-id="abc05-p148">미국/영국 여권 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-p148">U.S. / U.K. Passport Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3541">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3541">Format</span></span>

<span data-ttu-id="abc05-3542">9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3542">Nine digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3543">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3543">Pattern</span></span>

<span data-ttu-id="abc05-3544">9자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3544">Nine consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3545">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3545">Checksum</span></span>

<span data-ttu-id="abc05-3546">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3546">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3547">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3547">Definition</span></span>

<span data-ttu-id="abc05-3548">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3548">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3549">Func_usa_uk_passport 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3549">The function Func_usa_uk_passport finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3550">Keyword_passport의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3550">A keyword from Keyword_passport is found.</span></span>

```xml
<Entity id="178ec42a-18b4-47cc-85c7-d62c92fd67f8" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_usa_uk_passport" />
        <Match idRef="Keyword_passport" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3551">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3551">Keywords</span></span>

#### <a name="keyword_passport"></a><span data-ttu-id="abc05-3552">Keyword_passport</span><span class="sxs-lookup"><span data-stu-id="abc05-3552">Keyword_passport</span></span>

- <span data-ttu-id="abc05-3553">Passport Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3553">Passport Number</span></span> 
- <span data-ttu-id="abc05-3554">Passport No</span><span class="sxs-lookup"><span data-stu-id="abc05-3554">Passport No</span></span> 
- <span data-ttu-id="abc05-3555">Passport #</span><span class="sxs-lookup"><span data-stu-id="abc05-3555">Passport #</span></span> 
- <span data-ttu-id="abc05-3556">여권 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3556">Passport#</span></span> 
- <span data-ttu-id="abc05-3557">PassportID</span><span class="sxs-lookup"><span data-stu-id="abc05-3557">PassportID</span></span> 
- <span data-ttu-id="abc05-3558">Passportno</span><span class="sxs-lookup"><span data-stu-id="abc05-3558">Passportno</span></span> 
- <span data-ttu-id="abc05-3559">passportnumber</span><span class="sxs-lookup"><span data-stu-id="abc05-3559">passportnumber</span></span> 
- <span data-ttu-id="abc05-3560">パスポート</span><span class="sxs-lookup"><span data-stu-id="abc05-3560">パスポート</span></span> 
- <span data-ttu-id="abc05-3561">パスポート番号</span><span class="sxs-lookup"><span data-stu-id="abc05-3561">パスポート番号</span></span> 
- <span data-ttu-id="abc05-3562">パスポートのNum</span><span class="sxs-lookup"><span data-stu-id="abc05-3562">パスポートのNum</span></span> 
- <span data-ttu-id="abc05-3563">パスポート＃</span><span class="sxs-lookup"><span data-stu-id="abc05-3563">パスポート＃</span></span> 
- <span data-ttu-id="abc05-3564">Numéro de passeport</span><span class="sxs-lookup"><span data-stu-id="abc05-3564">Numéro de passeport</span></span> 
- <span data-ttu-id="abc05-3565">Passeport n °</span><span class="sxs-lookup"><span data-stu-id="abc05-3565">Passeport n °</span></span> 
- <span data-ttu-id="abc05-3566">Passeport Non</span><span class="sxs-lookup"><span data-stu-id="abc05-3566">Passeport Non</span></span> 
- <span data-ttu-id="abc05-3567">Passeport #</span><span class="sxs-lookup"><span data-stu-id="abc05-3567">Passeport #</span></span> 
- <span data-ttu-id="abc05-3568">포트 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3568">Passeport#</span></span> 
- <span data-ttu-id="abc05-3569">지/포트 아님</span><span class="sxs-lookup"><span data-stu-id="abc05-3569">PasseportNon</span></span> 
- <span data-ttu-id="abc05-3570">Passeportn °</span><span class="sxs-lookup"><span data-stu-id="abc05-3570">Passeportn °</span></span> 
   
## <a name="us-bank-account-number"></a><span data-ttu-id="abc05-3571">미국 은행 계좌 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3571">U.S. Bank Account Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3572">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3572">Format</span></span>

<span data-ttu-id="abc05-3573">8-17자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3573">8-17 digits</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3574">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3574">Pattern</span></span>

<span data-ttu-id="abc05-3575">8-17자리 연속 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3575">8-17 consecutive digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3576">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3576">Checksum</span></span>

<span data-ttu-id="abc05-3577">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3577">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3578">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3578">Definition</span></span>

<span data-ttu-id="abc05-3579">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3579">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3580">Regex_usa_bank_account_number 정규식이 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3580">The regular expression Regex_usa_bank_account_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3581">Keyword_usa_Bank_Account의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3581">A keyword from Keyword_usa_Bank_Account is found.</span></span>

```xml
<!-- U.S. Bank Account Number -->
<Entity id="a2ce32a8-f935-4bb6-8e96-2a5157672e2c" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Regex_usa_bank_account_number" />
        <Match idRef="Keyword_usa_Bank_Account" />
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3582">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3582">Keywords</span></span>

#### <a name="keyword_usa_bank_account"></a><span data-ttu-id="abc05-3583">Keyword_usa_Bank_Account</span><span class="sxs-lookup"><span data-stu-id="abc05-3583">Keyword_usa_Bank_Account</span></span>

- <span data-ttu-id="abc05-3584">Checking Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3584">Checking Account Number</span></span> 
- <span data-ttu-id="abc05-3585">Checking Account</span><span class="sxs-lookup"><span data-stu-id="abc05-3585">Checking Account</span></span> 
- <span data-ttu-id="abc05-3586">Checking Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-3586">Checking Account #</span></span> 
- <span data-ttu-id="abc05-3587">Checking Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3587">Checking Acct Number</span></span> 
- <span data-ttu-id="abc05-3588">Checking Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-3588">Checking Acct #</span></span> 
- <span data-ttu-id="abc05-3589">Checking Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3589">Checking Acct No.</span></span> 
- <span data-ttu-id="abc05-3590">Checking Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3590">Checking Account No.</span></span> 
- <span data-ttu-id="abc05-3591">Bank Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3591">Bank Account Number</span></span> 
- <span data-ttu-id="abc05-3592">Bank Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-3592">Bank Account #</span></span> 
- <span data-ttu-id="abc05-3593">Bank Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3593">Bank Acct Number</span></span> 
- <span data-ttu-id="abc05-3594">Bank Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-3594">Bank Acct #</span></span> 
- <span data-ttu-id="abc05-3595">Bank Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3595">Bank Acct No.</span></span> 
- <span data-ttu-id="abc05-3596">Bank Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3596">Bank Account No.</span></span> 
- <span data-ttu-id="abc05-3597">Savings Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3597">Savings Account Number</span></span> 
- <span data-ttu-id="abc05-3598">Savings Account.</span><span class="sxs-lookup"><span data-stu-id="abc05-3598">Savings Account.</span></span> 
- <span data-ttu-id="abc05-3599">Savings Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-3599">Savings Account #</span></span> 
- <span data-ttu-id="abc05-3600">Savings Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3600">Savings Acct Number</span></span> 
- <span data-ttu-id="abc05-3601">Savings Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-3601">Savings Acct #</span></span> 
- <span data-ttu-id="abc05-3602">Savings Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3602">Savings Acct No.</span></span> 
- <span data-ttu-id="abc05-3603">Savings Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3603">Savings Account No.</span></span> 
- <span data-ttu-id="abc05-3604">Debit Account Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3604">Debit Account Number</span></span> 
- <span data-ttu-id="abc05-3605">Debit Account</span><span class="sxs-lookup"><span data-stu-id="abc05-3605">Debit Account</span></span> 
- <span data-ttu-id="abc05-3606">Debit Account #</span><span class="sxs-lookup"><span data-stu-id="abc05-3606">Debit Account #</span></span> 
- <span data-ttu-id="abc05-3607">Debit Acct Number</span><span class="sxs-lookup"><span data-stu-id="abc05-3607">Debit Acct Number</span></span> 
- <span data-ttu-id="abc05-3608">Debit Acct #</span><span class="sxs-lookup"><span data-stu-id="abc05-3608">Debit Acct #</span></span> 
- <span data-ttu-id="abc05-3609">Debit Acct No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3609">Debit Acct No.</span></span> 
- <span data-ttu-id="abc05-3610">Debit Account No.</span><span class="sxs-lookup"><span data-stu-id="abc05-3610">Debit Account No.</span></span> 
   
## <a name="us-drivers-license-number"></a><span data-ttu-id="abc05-3611">미국 운전 면허 번호</span><span class="sxs-lookup"><span data-stu-id="abc05-3611">U.S. Driver's License Number</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3612">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3612">Format</span></span>

<span data-ttu-id="abc05-3613">주마다 다릅니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3613">Depends on the state</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3614">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3614">Pattern</span></span>

<span data-ttu-id="abc05-3615">주마다 다릅니다(예: 뉴욕).</span><span class="sxs-lookup"><span data-stu-id="abc05-3615">Depends on the state -- for example, New York:</span></span>
- <span data-ttu-id="abc05-3616">Ddd ddd ddd와 같이 9 자리 숫자는 일치 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3616">Nine digits formatted like ddd ddd ddd will match.</span></span>
- <span data-ttu-id="abc05-3617">Ddddddddd와 같은 9 자리 숫자가 일치 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3617">Nine digits like ddddddddd will not match.</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3618">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3618">Checksum</span></span>

<span data-ttu-id="abc05-3619">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3619">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3620">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3620">Definition</span></span>

<span data-ttu-id="abc05-3621">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3621">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3622">Func_new_york_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3622">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3623">Keyword_[state_name]_drivers_license_name의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3623">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="abc05-3624">Keyword_us_drivers_license에서 키워드가 발견 되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3624">A keyword from Keyword_us_drivers_license is found.</span></span>

<span data-ttu-id="abc05-3625">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3625">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3626">Func_new_york_drivers_license_number 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3626">The function Func_new_york_drivers_license_number finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3627">Keyword_[state_name]_drivers_license_name의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3627">A keyword from Keyword_[state_name]_drivers_license_name is found.</span></span>
- <span data-ttu-id="abc05-3628">Keyword_us_drivers_license_abbreviations의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3628">A keyword from Keyword_us_drivers_license_abbreviations is found.</span></span>
- <span data-ttu-id="abc05-3629">Keyword_us_drivers_license의 키워드가 발견되지 않았습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3629">No keyword from Keyword_us_drivers_license is found.</span></span>

```xml
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license" />
    </Pattern>
    <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_new_york_drivers_license_number" />
        <Match idRef="Keyword_new_york_drivers_license_name" />
        <Match idRef="Keyword_us_drivers_license_abbreviations" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Keyword_us_drivers_license" />
        </Any>
    </Pattern>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3630">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3630">Keywords</span></span>

#### <a name="keyword_us_drivers_license_abbreviations"></a><span data-ttu-id="abc05-3631">Keyword_us_drivers_license_abbreviations</span><span class="sxs-lookup"><span data-stu-id="abc05-3631">Keyword_us_drivers_license_abbreviations</span></span>

- <span data-ttu-id="abc05-3632">DL</span><span class="sxs-lookup"><span data-stu-id="abc05-3632">DL</span></span> 
- <span data-ttu-id="abc05-3633">된다</span><span class="sxs-lookup"><span data-stu-id="abc05-3633">DLS</span></span> 
- <span data-ttu-id="abc05-3634">CDL</span><span class="sxs-lookup"><span data-stu-id="abc05-3634">CDL</span></span> 
- <span data-ttu-id="abc05-3635">CDLS</span><span class="sxs-lookup"><span data-stu-id="abc05-3635">CDLS</span></span> 
- <span data-ttu-id="abc05-3636">ID</span><span class="sxs-lookup"><span data-stu-id="abc05-3636">ID</span></span> 
- <span data-ttu-id="abc05-3637">번호가</span><span class="sxs-lookup"><span data-stu-id="abc05-3637">IDs</span></span> 
- <span data-ttu-id="abc05-3638">DL #</span><span class="sxs-lookup"><span data-stu-id="abc05-3638">DL#</span></span> 
- <span data-ttu-id="abc05-3639">된다 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3639">DLS#</span></span> 
- <span data-ttu-id="abc05-3640">CDL #</span><span class="sxs-lookup"><span data-stu-id="abc05-3640">CDL#</span></span> 
- <span data-ttu-id="abc05-3641">CDLS #</span><span class="sxs-lookup"><span data-stu-id="abc05-3641">CDLS#</span></span> 
- <span data-ttu-id="abc05-3642">I #</span><span class="sxs-lookup"><span data-stu-id="abc05-3642">ID#</span></span>
- <span data-ttu-id="abc05-3643">번호가 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3643">IDs#</span></span> 
- <span data-ttu-id="abc05-3644">ID number</span><span class="sxs-lookup"><span data-stu-id="abc05-3644">ID number</span></span> 
- <span data-ttu-id="abc05-3645">ID numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-3645">ID numbers</span></span> 
- <span data-ttu-id="abc05-3646">LIC</span><span class="sxs-lookup"><span data-stu-id="abc05-3646">LIC</span></span> 
- <span data-ttu-id="abc05-3647">LIC #</span><span class="sxs-lookup"><span data-stu-id="abc05-3647">LIC#</span></span> 

#### <a name="keyword_us_drivers_license"></a><span data-ttu-id="abc05-3648">Keyword_us_drivers_license</span><span class="sxs-lookup"><span data-stu-id="abc05-3648">Keyword_us_drivers_license</span></span>

- <span data-ttu-id="abc05-3649">DriverLic</span><span class="sxs-lookup"><span data-stu-id="abc05-3649">DriverLic</span></span> 
- <span data-ttu-id="abc05-3650">DriverLics</span><span class="sxs-lookup"><span data-stu-id="abc05-3650">DriverLics</span></span> 
- <span data-ttu-id="abc05-3651">DriverLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-3651">DriverLicense</span></span> 
- <span data-ttu-id="abc05-3652">DriverLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3652">DriverLicenses</span></span> 
- <span data-ttu-id="abc05-3653">Driver Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-3653">Driver Lic</span></span> 
- <span data-ttu-id="abc05-3654">Driver Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-3654">Driver Lics</span></span> 
- <span data-ttu-id="abc05-3655">Driver License</span><span class="sxs-lookup"><span data-stu-id="abc05-3655">Driver License</span></span> 
- <span data-ttu-id="abc05-3656">Driver Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3656">Driver Licenses</span></span> 
- <span data-ttu-id="abc05-3657">DriversLic</span><span class="sxs-lookup"><span data-stu-id="abc05-3657">DriversLic</span></span> 
- <span data-ttu-id="abc05-3658">DriversLics</span><span class="sxs-lookup"><span data-stu-id="abc05-3658">DriversLics</span></span> 
- <span data-ttu-id="abc05-3659">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-3659">DriversLicense</span></span> 
- <span data-ttu-id="abc05-3660">드라이버 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-3660">DriversLicenses</span></span> 
- <span data-ttu-id="abc05-3661">Drivers Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-3661">Drivers Lic</span></span> 
- <span data-ttu-id="abc05-3662">Drivers Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-3662">Drivers Lics</span></span> 
- <span data-ttu-id="abc05-3663">Drivers License</span><span class="sxs-lookup"><span data-stu-id="abc05-3663">Drivers License</span></span> 
- <span data-ttu-id="abc05-3664">Drivers Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3664">Drivers Licenses</span></span> 
- <span data-ttu-id="abc05-3665">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-3665">Driver'Lic</span></span> 
- <span data-ttu-id="abc05-3666">Driver'Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-3666">Driver'Lics</span></span> 
- <span data-ttu-id="abc05-3667">Driver' 라이선스</span><span class="sxs-lookup"><span data-stu-id="abc05-3667">Driver'License</span></span> 
- <span data-ttu-id="abc05-3668">Driver'Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3668">Driver'Licenses</span></span> 
- <span data-ttu-id="abc05-3669">Driver' Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-3669">Driver' Lic</span></span> 
- <span data-ttu-id="abc05-3670">Driver' Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-3670">Driver' Lics</span></span> 
- <span data-ttu-id="abc05-3671">Driver' License</span><span class="sxs-lookup"><span data-stu-id="abc05-3671">Driver' License</span></span> 
- <span data-ttu-id="abc05-3672">Driver' Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3672">Driver' Licenses</span></span>
- <span data-ttu-id="abc05-3673">Driver'sLic</span><span class="sxs-lookup"><span data-stu-id="abc05-3673">Driver'sLic</span></span> 
- <span data-ttu-id="abc05-3674">Drivers (Slics)</span><span class="sxs-lookup"><span data-stu-id="abc05-3674">Driver'sLics</span></span> 
- <span data-ttu-id="abc05-3675">Driver'sLicense</span><span class="sxs-lookup"><span data-stu-id="abc05-3675">Driver'sLicense</span></span> 
- <span data-ttu-id="abc05-3676">Driver'sLicenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3676">Driver'sLicenses</span></span> 
- <span data-ttu-id="abc05-3677">Driver's Lic</span><span class="sxs-lookup"><span data-stu-id="abc05-3677">Driver's Lic</span></span> 
- <span data-ttu-id="abc05-3678">Driver's Lics</span><span class="sxs-lookup"><span data-stu-id="abc05-3678">Driver's Lics</span></span> 
- <span data-ttu-id="abc05-3679">Driver's License</span><span class="sxs-lookup"><span data-stu-id="abc05-3679">Driver's License</span></span> 
- <span data-ttu-id="abc05-3680">Driver's Licenses</span><span class="sxs-lookup"><span data-stu-id="abc05-3680">Driver's Licenses</span></span> 
- <span data-ttu-id="abc05-3681">identification number</span><span class="sxs-lookup"><span data-stu-id="abc05-3681">identification number</span></span> 
- <span data-ttu-id="abc05-3682">identification numbers</span><span class="sxs-lookup"><span data-stu-id="abc05-3682">identification numbers</span></span> 
- <span data-ttu-id="abc05-3683">identification #</span><span class="sxs-lookup"><span data-stu-id="abc05-3683">identification #</span></span> 
- <span data-ttu-id="abc05-3684">id card</span><span class="sxs-lookup"><span data-stu-id="abc05-3684">id card</span></span> 
- <span data-ttu-id="abc05-3685">id cards</span><span class="sxs-lookup"><span data-stu-id="abc05-3685">id cards</span></span> 
- <span data-ttu-id="abc05-3686">identification card</span><span class="sxs-lookup"><span data-stu-id="abc05-3686">identification card</span></span> 
- <span data-ttu-id="abc05-3687">identification cards</span><span class="sxs-lookup"><span data-stu-id="abc05-3687">identification cards</span></span> 
- <span data-ttu-id="abc05-3688">DriverLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-3688">DriverLic#</span></span> 
- <span data-ttu-id="abc05-3689">DriverLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-3689">DriverLics#</span></span> 
- <span data-ttu-id="abc05-3690">DriverLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-3690">DriverLicense#</span></span> 
- <span data-ttu-id="abc05-3691">DriverLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-3691">DriverLicenses#</span></span> 
- <span data-ttu-id="abc05-3692">Driver Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-3692">Driver Lic#</span></span> 
- <span data-ttu-id="abc05-3693">Driver Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-3693">Driver Lics#</span></span> 
- <span data-ttu-id="abc05-3694">Driver License#</span><span class="sxs-lookup"><span data-stu-id="abc05-3694">Driver License#</span></span> 
- <span data-ttu-id="abc05-3695">Driver Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-3695">Driver Licenses#</span></span> 
- <span data-ttu-id="abc05-3696">DriversLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-3696">DriversLic#</span></span> 
- <span data-ttu-id="abc05-3697">DriversLics #</span><span class="sxs-lookup"><span data-stu-id="abc05-3697">DriversLics#</span></span> 
- <span data-ttu-id="abc05-3698">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3698">DriversLicense#</span></span> 
- <span data-ttu-id="abc05-3699">드라이버 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3699">DriversLicenses#</span></span> 
- <span data-ttu-id="abc05-3700">Drivers Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-3700">Drivers Lic#</span></span> 
- <span data-ttu-id="abc05-3701">Drivers Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-3701">Drivers Lics#</span></span> 
- <span data-ttu-id="abc05-3702">Drivers License#</span><span class="sxs-lookup"><span data-stu-id="abc05-3702">Drivers License#</span></span> 
- <span data-ttu-id="abc05-3703">Drivers Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-3703">Drivers Licenses#</span></span> 
- <span data-ttu-id="abc05-3704">Driver' Lic #</span><span class="sxs-lookup"><span data-stu-id="abc05-3704">Driver'Lic#</span></span> 
- <span data-ttu-id="abc05-3705">Driver'Lics #</span><span class="sxs-lookup"><span data-stu-id="abc05-3705">Driver'Lics#</span></span> 
- <span data-ttu-id="abc05-3706">Driver' 라이선스 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3706">Driver'License#</span></span> 
- <span data-ttu-id="abc05-3707">Driver'Licenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-3707">Driver'Licenses#</span></span> 
- <span data-ttu-id="abc05-3708">Driver' Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-3708">Driver' Lic#</span></span> 
- <span data-ttu-id="abc05-3709">Driver' Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-3709">Driver' Lics#</span></span> 
- <span data-ttu-id="abc05-3710">Driver' License#</span><span class="sxs-lookup"><span data-stu-id="abc05-3710">Driver' License#</span></span> 
- <span data-ttu-id="abc05-3711">Driver' Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-3711">Driver' Licenses#</span></span> 
- <span data-ttu-id="abc05-3712">Driver'sLic #</span><span class="sxs-lookup"><span data-stu-id="abc05-3712">Driver'sLic#</span></span> 
- <span data-ttu-id="abc05-3713">Drivers (Slics) #</span><span class="sxs-lookup"><span data-stu-id="abc05-3713">Driver'sLics#</span></span> 
- <span data-ttu-id="abc05-3714">Driver'sLicense #</span><span class="sxs-lookup"><span data-stu-id="abc05-3714">Driver'sLicense#</span></span> 
- <span data-ttu-id="abc05-3715">Driver'sLicenses #</span><span class="sxs-lookup"><span data-stu-id="abc05-3715">Driver'sLicenses#</span></span> 
- <span data-ttu-id="abc05-3716">Driver's Lic#</span><span class="sxs-lookup"><span data-stu-id="abc05-3716">Driver's Lic#</span></span> 
- <span data-ttu-id="abc05-3717">Driver's Lics#</span><span class="sxs-lookup"><span data-stu-id="abc05-3717">Driver's Lics#</span></span> 
- <span data-ttu-id="abc05-3718">Driver's License#</span><span class="sxs-lookup"><span data-stu-id="abc05-3718">Driver's License#</span></span> 
- <span data-ttu-id="abc05-3719">Driver's Licenses#</span><span class="sxs-lookup"><span data-stu-id="abc05-3719">Driver's Licenses#</span></span> 
- <span data-ttu-id="abc05-3720">id card#</span><span class="sxs-lookup"><span data-stu-id="abc05-3720">id card#</span></span> 
- <span data-ttu-id="abc05-3721">id cards#</span><span class="sxs-lookup"><span data-stu-id="abc05-3721">id cards#</span></span> 
- <span data-ttu-id="abc05-3722">identification card#</span><span class="sxs-lookup"><span data-stu-id="abc05-3722">identification card#</span></span> 
- <span data-ttu-id="abc05-3723">identification cards#</span><span class="sxs-lookup"><span data-stu-id="abc05-3723">identification cards#</span></span> 


#### <a name="keyword_state_name_drivers_license_name"></a><span data-ttu-id="abc05-3724">Keyword_ [state_name] _drivers_license_name</span><span class="sxs-lookup"><span data-stu-id="abc05-3724">Keyword_[state_name]_drivers_license_name</span></span>

- <span data-ttu-id="abc05-3725">주 약어(예: "NY")</span><span class="sxs-lookup"><span data-stu-id="abc05-3725">State abbreviation (for example, "NY")</span></span> 
- <span data-ttu-id="abc05-3726">주 이름(예: "New York")</span><span class="sxs-lookup"><span data-stu-id="abc05-3726">State name (for example, "New York")</span></span>    
   
## <a name="us-individual-taxpayer-identification-number-itin"></a><span data-ttu-id="abc05-3727">미국 ITIN(개인 납세자 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-3727">U.S. Individual Taxpayer Identification Number (ITIN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3728">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3728">Format</span></span>

<span data-ttu-id="abc05-3729">"9"로 시작되고, "7" 또는 "8"을 4번째 숫자로 포함하고, 경우에 따라 공백이나 대시로 서식이 지정된 9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3729">Nine digits that start with a "9" and contain a "7" or "8" as the fourth digit, optionally formatted with spaces or dashes</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3730">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3730">Pattern</span></span>

<span data-ttu-id="abc05-3731">서식이</span><span class="sxs-lookup"><span data-stu-id="abc05-3731">Formatted:</span></span>
- <span data-ttu-id="abc05-3732">"9"자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3732">The digit "9"</span></span> 
- <span data-ttu-id="abc05-3733">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3733">Two digits</span></span> 
- <span data-ttu-id="abc05-3734">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3734">A space or dash</span></span> 
- <span data-ttu-id="abc05-3735">"7" 또는 "8"</span><span class="sxs-lookup"><span data-stu-id="abc05-3735">A "7" or "8"</span></span> 
- <span data-ttu-id="abc05-3736">1자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3736">A digit</span></span> 
- <span data-ttu-id="abc05-3737">공백 또는 대시</span><span class="sxs-lookup"><span data-stu-id="abc05-3737">A space, or dash</span></span> 
- <span data-ttu-id="abc05-3738">4자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3738">Four digits</span></span>

<span data-ttu-id="abc05-3739">서식</span><span class="sxs-lookup"><span data-stu-id="abc05-3739">Unformatted:</span></span>
- <span data-ttu-id="abc05-3740">"9"자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3740">The digit "9"</span></span> 
- <span data-ttu-id="abc05-3741">2자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3741">Two digits</span></span> 
- <span data-ttu-id="abc05-3742">"7" 또는 "8"</span><span class="sxs-lookup"><span data-stu-id="abc05-3742">A "7" or "8"</span></span> 
- <span data-ttu-id="abc05-3743">5자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3743">Five digits</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3744">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3744">Checksum</span></span>

<span data-ttu-id="abc05-3745">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3745">No</span></span>

### <a name="definition"></a><span data-ttu-id="abc05-3746">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3746">Definition</span></span>

<span data-ttu-id="abc05-3747">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3747">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3748">Func_formatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3748">The function Func_formatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3749">다음 중 하나 이상이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3749">At least one of the following is true:</span></span>
    - <span data-ttu-id="abc05-3750">Keyword_itin의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3750">A keyword from Keyword_itin is found.</span></span>
    - <span data-ttu-id="abc05-3751">Func_us_address 함수가 올바른 날짜 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3751">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="abc05-3752">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3752">The function Func_us_date finds a date in the right date format.</span></span>
    - <span data-ttu-id="abc05-3753">Keyword_itin_collaborative의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3753">A keyword from Keyword_itin_collaborative is found.</span></span>

<span data-ttu-id="abc05-3754">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3754">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3755">Func_unformatted_itin 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3755">The function Func_unformatted_itin finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3756">다음 중 하나 이상이 충족됩니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3756">At least one of the following is true:</span></span>
    - <span data-ttu-id="abc05-3757">Keyword_itin_collaborative의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3757">A keyword from Keyword_itin_collaborative is found.</span></span>
    - <span data-ttu-id="abc05-3758">Func_us_address 함수가 올바른 날짜 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3758">The function Func_us_address finds an address in the right date format.</span></span>
    - <span data-ttu-id="abc05-3759">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3759">The function Func_us_date finds a date in the right date format.</span></span>

```xml
<!-- U.S. Individual Taxpayer Identification Number (ITIN) -->
<Entity id="e55e2a32-f92d-4985-a35d-a0b269eb687b" patternsProximity="300" recommendedConfidence="75">
    <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_formatted_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
          <Match idRef="Keyword_itin_collaborative" />
        </Any>
    </Pattern>
    <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_itin" />
        <Match idRef="Keyword_itin" />
        <Any minMatches="1">
          <Match idRef="Keyword_itin_collaborative" />
          <Match idRef="Func_us_address" />
          <Match idRef="Func_us_date" />
        </Any>
    </Pattern>
</Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3760">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3760">Keywords</span></span>

#### <a name="keyword_itin"></a><span data-ttu-id="abc05-3761">Keyword_itin</span><span class="sxs-lookup"><span data-stu-id="abc05-3761">Keyword_itin</span></span>

- <span data-ttu-id="abc05-3762">taxpayer</span><span class="sxs-lookup"><span data-stu-id="abc05-3762">taxpayer</span></span> 
- <span data-ttu-id="abc05-3763">tax id</span><span class="sxs-lookup"><span data-stu-id="abc05-3763">tax id</span></span> 
- <span data-ttu-id="abc05-3764">tax identification</span><span class="sxs-lookup"><span data-stu-id="abc05-3764">tax identification</span></span> 
- <span data-ttu-id="abc05-3765">itin</span><span class="sxs-lookup"><span data-stu-id="abc05-3765">itin</span></span> 
- <span data-ttu-id="abc05-3766">ssn</span><span class="sxs-lookup"><span data-stu-id="abc05-3766">ssn</span></span> 
- <span data-ttu-id="abc05-3767">언급</span><span class="sxs-lookup"><span data-stu-id="abc05-3767">tin</span></span> 
- <span data-ttu-id="abc05-3768">social security</span><span class="sxs-lookup"><span data-stu-id="abc05-3768">social security</span></span> 
- <span data-ttu-id="abc05-3769">tax payer</span><span class="sxs-lookup"><span data-stu-id="abc05-3769">tax payer</span></span> 
- <span data-ttu-id="abc05-3770">itins</span><span class="sxs-lookup"><span data-stu-id="abc05-3770">itins</span></span> 
- <span data-ttu-id="abc05-3771">taxid</span><span class="sxs-lookup"><span data-stu-id="abc05-3771">taxid</span></span> 
- <span data-ttu-id="abc05-3772">individual taxpayer</span><span class="sxs-lookup"><span data-stu-id="abc05-3772">individual taxpayer</span></span> 

#### <a name="keyword_itin_collaborative"></a><span data-ttu-id="abc05-3773">Keyword_itin_collaborative</span><span class="sxs-lookup"><span data-stu-id="abc05-3773">Keyword_itin_collaborative</span></span>

- <span data-ttu-id="abc05-3774">License</span><span class="sxs-lookup"><span data-stu-id="abc05-3774">License</span></span> 
- <span data-ttu-id="abc05-3775">DL</span><span class="sxs-lookup"><span data-stu-id="abc05-3775">DL</span></span> 
- <span data-ttu-id="abc05-3776">DOB</span><span class="sxs-lookup"><span data-stu-id="abc05-3776">DOB</span></span> 
- <span data-ttu-id="abc05-3777">생년월일</span><span class="sxs-lookup"><span data-stu-id="abc05-3777">Birthdate</span></span> 
- <span data-ttu-id="abc05-3778">생일</span><span class="sxs-lookup"><span data-stu-id="abc05-3778">Birthday</span></span> 
- <span data-ttu-id="abc05-3779">Date of Birth</span><span class="sxs-lookup"><span data-stu-id="abc05-3779">Date of Birth</span></span> 
   
## <a name="us-social-security-number-ssn"></a><span data-ttu-id="abc05-3780">미국 SSN(사회 보험 번호)</span><span class="sxs-lookup"><span data-stu-id="abc05-3780">U.S. Social Security Number (SSN)</span></span>

### <a name="format"></a><span data-ttu-id="abc05-3781">형식일</span><span class="sxs-lookup"><span data-stu-id="abc05-3781">Format</span></span>

<span data-ttu-id="abc05-3782">서식 있는 패턴 또는 서식 없는 패턴으로 표시될 수 있는 9자리 숫자</span><span class="sxs-lookup"><span data-stu-id="abc05-3782">9 digits, which may be in a formatted or unformatted pattern</span></span>

> [!NOTE]
> <span data-ttu-id="abc05-3783">Mid가 2011 이전에 실행 된 경우 SSN은 특정 범위 내에서 번호의 특정 부분이 유효한 지 확인 하는 강력한 서식을 사용 해야 하지만 검사 값은 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3783">If issued before mid-2011, an SSN has strong formatting where certain parts of the number must fall within certain ranges to be valid (but there's no checksum).</span></span>

### <a name="pattern"></a><span data-ttu-id="abc05-3784">패턴</span><span class="sxs-lookup"><span data-stu-id="abc05-3784">Pattern</span></span>

<span data-ttu-id="abc05-3785">다음의 네 가지 패턴에서 SSNs를 검색 하는 함수는 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3785">Four functions look for SSNs in four different patterns:</span></span>
- <span data-ttu-id="abc05-3786">Func_ssn는 대시 또는 공백으로 서식이 지정 된 2011 이전 수준의 서식으로 SSNs를 찾습니다 (ddd-dd-dddd 또는 ddd dd dddd).</span><span class="sxs-lookup"><span data-stu-id="abc05-3786">Func_ssn finds SSNs with pre-2011 strong formatting that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="abc05-3787">Func_unformatted_ssn는 형식이 지정 되지 않은 2011 이전 형식으로 서식이 지정 된 SSNs를 찾고 (ddddddddd)</span><span class="sxs-lookup"><span data-stu-id="abc05-3787">Func_unformatted_ssn finds SSNs with pre-2011 strong formatting that are unformatted as nine consecutive digits (ddddddddd)</span></span>
- <span data-ttu-id="abc05-3788">Func_randomized_formatted_ssn는 대시 또는 공백으로 서식이 지정 된 post-2011 SSNs를 찾습니다 (ddd-dd-dddd 또는 ddd dd dddd).</span><span class="sxs-lookup"><span data-stu-id="abc05-3788">Func_randomized_formatted_ssn finds post-2011 SSNs that are formatted with dashes or spaces (ddd-dd-dddd OR ddd dd dddd)</span></span>
- <span data-ttu-id="abc05-3789">Func_randomized_unformatted_ssn는 형식 없는 2011 SSNs를 찾습니다 (ddddddddd).</span><span class="sxs-lookup"><span data-stu-id="abc05-3789">Func_randomized_unformatted_ssn finds post-2011 SSNs that are unformatted as nine consecutive digits (ddddddddd)</span></span>

### <a name="checksum"></a><span data-ttu-id="abc05-3790">제외</span><span class="sxs-lookup"><span data-stu-id="abc05-3790">Checksum</span></span>

<span data-ttu-id="abc05-3791">아니요</span><span class="sxs-lookup"><span data-stu-id="abc05-3791">No</span></span>


### <a name="definition"></a><span data-ttu-id="abc05-3792">정의</span><span class="sxs-lookup"><span data-stu-id="abc05-3792">Definition</span></span>

<span data-ttu-id="abc05-3793">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 85% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3793">A DLP policy is 85% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3794">Func_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3794">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3795">Keyword_ssn의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3795">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="abc05-3796">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3796">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-3797">Func_us_address 함수가 올바른 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3797">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="abc05-3798">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 75% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3798">A DLP policy is 75% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3799">Func_unformatted_ssn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3799">The function Func_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3800">Keyword_ssn의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3800">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="abc05-3801">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3801">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-3802">Func_us_address 함수가 올바른 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3802">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="abc05-3803">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 65% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3803">A DLP policy is 65% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3804">Func_randomized_formatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3804">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3805">Keyword_ssn의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3805">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="abc05-3806">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3806">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-3807">Func_us_address 함수가 올바른 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3807">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="abc05-3808">DLP 정책은 다음과 같은 경우 이러한 유형의 중요한 정보가 300자 이내의 접근성으로 검색되었음을 55% 신뢰합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3808">A DLP policy is 55% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3809">Func_randomized_unformatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3809">The function Func_randomized_unformatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3810">Keyword_ssn의 키워드가 발견되었습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3810">A keyword from Keyword_ssn is found.</span></span>
- <span data-ttu-id="abc05-3811">Func_us_date 함수가 올바른 날짜 형식의 날짜를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3811">The function Func_us_date finds a date in the right date format.</span></span>
- <span data-ttu-id="abc05-3812">Func_us_address 함수가 올바른 형식의 주소를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3812">The function Func_us_address finds an address in the right format.</span></span>

<span data-ttu-id="abc05-3813">DLP 정책은 300 문자에 근접 한 경우이 유형의 중요 한 정보를 검색 한다는 것을 40% 확신 합니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3813">A DLP policy is 40% confident that it's detected this type of sensitive information if, within a proximity of 300 characters:</span></span>
- <span data-ttu-id="abc05-3814">Func_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3814">The function Func_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3815">Func_unformatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3815">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3816">Func_randomized_unformatted_ssn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3816">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3817">Keyword_ssn의 키워드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3817">A keyword from Keyword_ssn is not found.</span></span>
 
<span data-ttu-id="abc05-3818">또는</span><span class="sxs-lookup"><span data-stu-id="abc05-3818">Or</span></span>

- <span data-ttu-id="abc05-3819">Func_randomized_formatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3819">The function Func_randomized_formatted_ssn finds content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3820">Func_unformatted_ssn 함수가 해당 패턴과 일치하는 콘텐츠를 찾지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3820">The function Func_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3821">Func_randomized_unformatted_ssn 함수가 해당 패턴과 일치 하는 콘텐츠를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3821">The function Func_randomized_unformatted_ssn does not find content that matches the pattern.</span></span>
- <span data-ttu-id="abc05-3822">Keyword_ssn의 키워드를 찾을 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="abc05-3822">A keyword from Keyword_ssn is not found.</span></span>

```xml
<!-- U.S. Social Security Number (SSN) -->
  <Entity id="a44669fe-0d48-453d-a9b1-2cc83f2cba77" patternsProximity="300" recommendedConfidence="75">
      <Pattern confidenceLevel="85">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="75">
        <IdMatch idRef="Func_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="65">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="1">
          <Match idRef="Keyword_ssn" />
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="55">
        <IdMatch idRef="Func_randomized_unformatted_ssn" />
        <Match idRef="Keyword_ssn" />
        <Any minMatches="1">
          <Match idRef="Func_us_date" />
          <Match idRef="Func_us_address" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
      <Pattern confidenceLevel="40">
        <IdMatch idRef="Func_randomized_formatted_ssn" />
        <Any minMatches="0" maxMatches="0">
          <Match idRef="Func_unformatted_ssn" />
          <Match idRef="Func_randomized_unformatted_ssn" />
          <Match idRef="Keyword_ssn" />
        </Any>
      </Pattern>
    </Entity>
```

### <a name="keywords"></a><span data-ttu-id="abc05-3823">키워드</span><span class="sxs-lookup"><span data-stu-id="abc05-3823">Keywords</span></span>

#### <a name="keyword_ssn"></a><span data-ttu-id="abc05-3824">Keyword_ssn</span><span class="sxs-lookup"><span data-stu-id="abc05-3824">Keyword_ssn</span></span>

- <span data-ttu-id="abc05-3825">Social Security</span><span class="sxs-lookup"><span data-stu-id="abc05-3825">Social Security</span></span> 
- <span data-ttu-id="abc05-3826">Social Security#</span><span class="sxs-lookup"><span data-stu-id="abc05-3826">Social Security#</span></span> 
- <span data-ttu-id="abc05-3827">Soc Sec</span><span class="sxs-lookup"><span data-stu-id="abc05-3827">Soc Sec</span></span> 
- <span data-ttu-id="abc05-3828">SSN</span><span class="sxs-lookup"><span data-stu-id="abc05-3828">SSN</span></span> 
- <span data-ttu-id="abc05-3829">있는 SSN</span><span class="sxs-lookup"><span data-stu-id="abc05-3829">SSNS</span></span> 
- <span data-ttu-id="abc05-3830">SSN #</span><span class="sxs-lookup"><span data-stu-id="abc05-3830">SSN#</span></span> 
- <span data-ttu-id="abc05-3831">대비 #</span><span class="sxs-lookup"><span data-stu-id="abc05-3831">SS#</span></span> 
- <span data-ttu-id="abc05-3832">생길</span><span class="sxs-lookup"><span data-stu-id="abc05-3832">SSID</span></span> 
   

