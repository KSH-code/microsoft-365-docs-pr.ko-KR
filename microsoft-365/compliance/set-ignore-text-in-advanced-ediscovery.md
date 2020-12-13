---
title: Advanced eDiscovery에서 분석에 텍스트 무시 옵션 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 44055727-56e8-42d7-9dc3-fb942f3901cc
description: Advanced eDiscovery에서 분석 및 프로세스 모듈을 사용할 때 특정 텍스트를 무시하는 규칙을 정의하는 방법을 학습합니다.
ms.openlocfilehash: f61724e3964ff4ba7f099dbfb4411e19db258adc
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663473"
---
# <a name="set-ignore-text-option-for-analyze-in-advanced-ediscovery-classic"></a><span data-ttu-id="94ed4-103">Advanced eDiscovery(클래식)에서 분석에 대한 텍스트 무시 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="94ed4-103">Set Ignore Text option for Analyze in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="94ed4-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="94ed4-106">텍스트 무시 기능은 전체 또는 다음 고급 eDiscovery 모듈에 적용할 수 있습니다. 분석(중복에 가까운 항목, 전자 메일 스레드, 테마) 및 연결성.</span><span class="sxs-lookup"><span data-stu-id="94ed4-106">The Ignore Text feature can be applied to all or any of the following Advanced eDiscovery modules: Analyze (Near-duplicates, Email Threads, Themes) and Relevance.</span></span> <span data-ttu-id="94ed4-107">무시된 텍스트는 해당 텍스트와는 무관하게 표시된 파일에 나타나지 않습니다. 분석/계산에서는 무시된 텍스트를 삭제합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-107">Ignored text will not appear in files displayed in Relevance, and the analysis/calculations will discard the ignored text.</span></span>
  
<span data-ttu-id="94ed4-108">이미 실행된 모듈에 대해 텍스트 무시 기능을 이전에 정의한 경우 이제 텍스트 무시 설정이 수정되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-108">If the Ignore Text feature was previously defined for modules that have already run, the Ignore Text setting will now be protected from being modified.</span></span> <span data-ttu-id="94ed4-109">그러나 Relevance 모듈의 텍스트 무시 기능은 변경될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-109">However, the Ignore Text feature for the Relevance module can still be changed at any time.</span></span>
  
## <a name="how-ignore-text-filters-are-applied"></a><span data-ttu-id="94ed4-110">텍스트 필터 무시 적용 방법</span><span class="sxs-lookup"><span data-stu-id="94ed4-110">How Ignore Text filters are applied</span></span>

<span data-ttu-id="94ed4-111">여러 무시 텍스트 필터는 입력된 순서대로 적용됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-111">Multiple Ignore Text filters are applied in the order that they were entered.</span></span> <span data-ttu-id="94ed4-112">적용 순서를 변경하려면 해당 순서를 삭제하고 원하는 순서로 다시 입력해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-112">To change the order in which they are applied, they must be deleted and re-entered in the desired order.</span></span>
  
<span data-ttu-id="94ed4-113">예를 들어 텍스트 콘텐츠가 "DAVE BOB ALICE CAROL EVE"이면 다음은 텍스트 무시 항목의 샘플과 이러한 항목이 생성하는 결과입니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-113">For example, if the text content is: "DAVE BOB ALICE CAROL EVE", the following are samples of Ignore Text entries and the results these entries produce:</span></span>

|<span data-ttu-id="94ed4-114">**텍스트 항목 무시**</span><span class="sxs-lookup"><span data-stu-id="94ed4-114">**Ignore Text entries**</span></span> <br/> |<span data-ttu-id="94ed4-115">**결과**</span><span class="sxs-lookup"><span data-stu-id="94ed4-115">**Results**</span></span> <br/> |
|:-----|:-----|
|<span data-ttu-id="94ed4-116">"ALICE", "BOB CAROL"</span><span class="sxs-lookup"><span data-stu-id="94ed4-116">"ALICE", "BOB CAROL"</span></span>  <br/> |<span data-ttu-id="94ed4-117">"DAVE EVE"</span><span class="sxs-lookup"><span data-stu-id="94ed4-117">"DAVE EVE"</span></span>  <br/> |
|<span data-ttu-id="94ed4-118">"ALICE", "BOB ALICE CAROL"</span><span class="sxs-lookup"><span data-stu-id="94ed4-118">"ALICE", "BOB ALICE CAROL"</span></span>  <br/> |<span data-ttu-id="94ed4-119">"DAVE BOB CAROL EVE"</span><span class="sxs-lookup"><span data-stu-id="94ed4-119">"DAVE BOB CAROL EVE"</span></span>  <br/> |
   
<span data-ttu-id="94ed4-120">두 번째 Ignore 텍스트 항목은 첫 번째 무시 텍스트가 적용된 후와 같이 문자열을 찾을 수 없는 경우 구현되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-120">The second Ignore Text entry is not implemented because the string is not found as such AFTER the first Ignore Text has been applied.</span></span>
  
## <a name="use-regular-expressions-when-defining-ignore-text"></a><span data-ttu-id="94ed4-121">텍스트 무시를 정의할 때 정규식 사용</span><span class="sxs-lookup"><span data-stu-id="94ed4-121">Use regular expressions when defining Ignore Text</span></span>

<span data-ttu-id="94ed4-122">텍스트 무시를 정의할 때 정규식이 지원됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-122">Regular expressions are supported for use when defining Ignore Text.</span></span> <span data-ttu-id="94ed4-123">다음은 정규식 구문과 사용법의 예입니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-123">The following are examples of regular expression syntax and usage:</span></span>
  
- <span data-ttu-id="94ed4-124">시작에서 줄 끝까지 텍스트를 제거(무시)하려면</span><span class="sxs-lookup"><span data-stu-id="94ed4-124">To remove (ignore) text from Begin until the end of a line:</span></span>
    
     `Begin(.*)$`
    
    <span data-ttu-id="94ed4-125">여기서 "Begin"은 줄에서 이 문자열이 처음 나타난 것입니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-125">where "Begin" is the initial occurrence of this string in the line.</span></span>
    
    <span data-ttu-id="94ed4-126">예를 들어 다음 텍스트에 대해 다음을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-126">For example, for the following text:</span></span>
    
    <span data-ttu-id="94ed4-127">**"This is first sentence and first line**</span><span class="sxs-lookup"><span data-stu-id="94ed4-127">**"This is first sentence and first line**</span></span>
    
    <span data-ttu-id="94ed4-128">**This is second sentence and second line"**</span><span class="sxs-lookup"><span data-stu-id="94ed4-128">**This is second sentence and second line"**</span></span>
    
    <span data-ttu-id="94ed4-129">정규식이 먼저(. \* ) $는 다음을 하게됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-129">the Regular Expression first(.\*)$ will result in:</span></span>
    
    <span data-ttu-id="94ed4-130">**"This is**</span><span class="sxs-lookup"><span data-stu-id="94ed4-130">**"This is**</span></span>
    
    <span data-ttu-id="94ed4-131">**This is second sentence and second line"**</span><span class="sxs-lookup"><span data-stu-id="94ed4-131">**This is second sentence and second line"**</span></span>
    
- <span data-ttu-id="94ed4-132">전자 메일 스레드 끝에 자동으로 삽입된 고지 사항 및 법적 설명을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="94ed4-132">To remove disclaimers and legal statements automatically inserted at the end of email threads:</span></span>
    
     `Begin(.|\s)*End`
    
    <span data-ttu-id="94ed4-133">여기서 "Begin" 및 "End"는 래핑된 텍스트 단락의 시작과 끝에 있는 고유한 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-133">where "Begin" and "End" are unique strings at the beginning and end of a wrapped text paragraph.</span></span> 
    
    <span data-ttu-id="94ed4-134">예를 들어 다음 정규식은 Begin 문자열과 End 문자열 사이의 전자 메일 스레드에 있는 고지 사항 및 법적 설명을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-134">For example, the following regular expression will remove disclaimers and legal statements that were in the email thread between the Begin and End strings:</span></span>
    
    <span data-ttu-id="94ed4-135">**이 메시지에는 기밀 정보(.| \s) 확인이 필요한 경우 하드 카피 \* 버전을 요청하십시오.**</span><span class="sxs-lookup"><span data-stu-id="94ed4-135">**This message contains confidential information (.|\s)\*If verification is required please request a hard-copy version**</span></span>
    
- <span data-ttu-id="94ed4-136">고지사항(특수 문자 포함)을 제거하려면</span><span class="sxs-lookup"><span data-stu-id="94ed4-136">To remove a disclaimer (including special characters):</span></span> 
    
    <span data-ttu-id="94ed4-137">예를 들어 다음 텍스트(여기에 x's로 표시됨)의 경우</span><span class="sxs-lookup"><span data-stu-id="94ed4-137">For example, for the following text (with the disclaimer represented here by x's):</span></span> 
    
    <span data-ttu-id="94ed4-138">**/\*\ 이 메시지에는 기밀 정보가 포함되어 있습니다. xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="94ed4-138">**/\*\ This message contains confidential information. xxxx xxxx**</span></span>
    
    <span data-ttu-id="94ed4-139">**xxxxx xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span><span class="sxs-lookup"><span data-stu-id="94ed4-139">**xxxx xxxx xxxx xxxx xxxx xxxx xxxx**</span></span>
    
    <span data-ttu-id="94ed4-140">\**xxxx xxxx 확인이 필요한 경우 하드 복사 버전을 요청하십시오. /\*\**</span><span class="sxs-lookup"><span data-stu-id="94ed4-140">\**xxxx xxxx If verification is required, please request a hard-copy version. /\*\**</span></span>
    
    <span data-ttu-id="94ed4-141">위의 고지 사항 제거 정규식은 다음을 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-141">the regular expression to remove the above disclaimer should be:</span></span> 
    
    <span data-ttu-id="94ed4-142">**\/\\*\\이 메시지에는 기밀 \. 정보(.| \s) 확인이 필요한 경우 하드 카피 \* 버전을 요청하십시오. \.\/\\*\\**</span><span class="sxs-lookup"><span data-stu-id="94ed4-142">**\/\\*\\ This message contains confidential information\.(.|\s)\* If verification is required please request a hard-copy version\. \/\\*\\**</span></span>
    
- <span data-ttu-id="94ed4-143">정규식 규칙:</span><span class="sxs-lookup"><span data-stu-id="94ed4-143">Regular expression rules:</span></span>
    
  - <span data-ttu-id="94ed4-144">공백, "_" 및 "-"를 제외한 알파벳에 속하지 않는 문자 앞에 \" ".</span><span class="sxs-lookup"><span data-stu-id="94ed4-144">Any characters that are not part of the alphabet except for space(s), "_" and "-" must be preceded by "\".</span></span>
    
  - <span data-ttu-id="94ed4-145">일반 eExpression 필드는 길이 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-145">The regular eExpression field can be unlimited length.</span></span>
    
> [!TIP]
> <span data-ttu-id="94ed4-146">정규식의 설명과 구문에 대한 자세한 내용은 정규식 언어 - 빠른 [참조를 참고합니다.](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx)</span><span class="sxs-lookup"><span data-stu-id="94ed4-146">For an explanation and detailed syntax of regular expressions, see: [Regular Expression Language - Quick Reference](https://msdn.microsoft.com/library/az24scfc%28v=vs.110%29.aspx).</span></span> 
  
## <a name="define-ignore-text-rule"></a><span data-ttu-id="94ed4-147">텍스트 무시 규칙 정의</span><span class="sxs-lookup"><span data-stu-id="94ed4-147">Define Ignore Text rule</span></span>

1. <span data-ttu-id="94ed4-148">분석 옵션 **\> 관리 \>** 탭의 텍스트  무시 섹션에서 아이콘을 클릭하여 규칙을 **+** 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-148">In the **Manage \> Analyze \> Analyze options** tab, in the **Ignore Text** section, click the **+** icon to add a rule.</span></span> 
    
2. <span data-ttu-id="94ed4-149">텍스트 무시 **추가** 대화 상자의 **이름** 필드에 텍스트 무시 규칙의 이름을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-149">In the **Add Ignore Text** dialog, in the **Name** field, type a name for the Ignore Text rule.</span></span> 
    
    ![무시 하는 텍스트 추가](../media/98e5129b-2667-4692-86fa-2d0117187a7f.png)
  
3. <span data-ttu-id="94ed4-151">텍스트 **상자에** 무시할 텍스트를 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-151">In the **Text** box, type the text to be ignored.</span></span> <span data-ttu-id="94ed4-152">텍스트 필드에는 문자 수에 제한이 없습니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-152">The text field allows an unlimited number of characters.</span></span> 
    
    > [!TIP]
    > <span data-ttu-id="94ed4-153">위의 창에 표시된 대로  전구를 클릭하여 텍스트 무시 규칙에 대한 일반적인 구문 지침을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-153">As shown in the window above, click **light bulb** to see common syntax guidelines for the Ignore Text rule.</span></span> 
  
4. <span data-ttu-id="94ed4-154">원하는 경우 **대소문자** 구분 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-154">Select the **Case sensitive** check box, if desired.</span></span> 
    
5. <span data-ttu-id="94ed4-155">적용 **대상** 목록에서 정의를 적용할 Advanced eDiscovery 모듈을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-155">In the **Apply to** list, select the Advanced eDiscovery modules in which to apply the definition.</span></span> 
    
6. <span data-ttu-id="94ed4-156">예제 텍스트에서 테스트를 실행하려면 입력 텍스트 상자에 샘플 텍스트를 **입력하고** 테스트를 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="94ed4-156">If you want a test run on sample text, type sample text in the **Input** text box and click **Test**.</span></span> <span data-ttu-id="94ed4-157">결과는 출력 텍스트 **상자에** 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-157">The results are displayed in the **Output** text box.</span></span> 
    
7. <span data-ttu-id="94ed4-158">확인을 **클릭하여** 텍스트 무시 규칙을 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-158">Click **OK** to save the Ignore Text rule.</span></span> <span data-ttu-id="94ed4-159">정의된 무시 텍스트 규칙이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="94ed4-159">The defined Ignore Text rule is displayed.</span></span> 
    
    ![무시 설정 텍스트 이름](../media/3a788ac3-4a1c-46c9-89bd-7ff32d68ce23.png)
  
## <a name="see-also"></a><span data-ttu-id="94ed4-161">참고 항목</span><span class="sxs-lookup"><span data-stu-id="94ed4-161">See also</span></span>

[<span data-ttu-id="94ed4-162">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="94ed4-162">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="94ed4-163">문서 유사성 이해</span><span class="sxs-lookup"><span data-stu-id="94ed4-163">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="94ed4-164">설정 분석 옵션</span><span class="sxs-lookup"><span data-stu-id="94ed4-164">Setting Analyze options</span></span>](set-analyze-options-in-advanced-ediscovery.md)
  
[<span data-ttu-id="94ed4-165">고급 설정 분석 설정</span><span class="sxs-lookup"><span data-stu-id="94ed4-165">Setting Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="94ed4-166">분석 결과 보기</span><span class="sxs-lookup"><span data-stu-id="94ed4-166">Viewing Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

