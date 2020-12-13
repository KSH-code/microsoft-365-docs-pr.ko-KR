---
title: Advanced eDiscovery에서 분석 옵션 설정
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: f6cd6588-f6b6-424a-a9ab-3782b842faee
description: 중복에 가까운 항목, 전자 메일 스레드 및 테마를 포함하여 Advanced eDiscovery에서 분석 프로세스에 대한 옵션을 설정하는 단계를 검토합니다.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ff51402cd79f2966730677a982fa5173b7e9b98
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663503"
---
# <a name="set-analyze-options-in-advanced-ediscovery-classic"></a><span data-ttu-id="67b72-103">Advanced eDiscovery(클래식)에서 분석 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="67b72-103">Set Analyze options in Advanced eDiscovery (classic)</span></span>

> [!NOTE]
> <span data-ttu-id="67b72-p101">Advanced eDiscovery를 사용하려면 Office 365 E3의 고급 준수 추가 기능이나 조직을 위한 E5 구독이 필요합니다. 이 요금제가 없는 상태에서 Advanced eDiscovery를 사용하려는 경우에는 [Office 365 Enterprise E5 평가판을 등록](https://go.microsoft.com/fwlink/p/?LinkID=698279)할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-p101">Advanced eDiscovery requires an Office 365 E3 with the Advanced Compliance add-on or an E5 subscription for your organization. If you don't have that plan and want to try Advanced eDiscovery, you can [sign up for a trial of Office 365 Enterprise E5](https://go.microsoft.com/fwlink/p/?LinkID=698279).</span></span> 
  
<span data-ttu-id="67b72-106">Advanced eDiscovery에서 Analyze를 실행하기 전에 분석 옵션을 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="67b72-106">In Advanced eDiscovery, set the Analyze options prior to running Analyze.</span></span>
  
## <a name="set-analyze-options"></a><span data-ttu-id="67b72-107">분석 옵션 설정</span><span class="sxs-lookup"><span data-stu-id="67b72-107">Set Analyze options</span></span>

<span data-ttu-id="67b72-108">Open **Prepare \> Analyze** \> **Setup**.</span><span class="sxs-lookup"><span data-stu-id="67b72-108">Open **Prepare \> Analyze** \> **Setup**.</span></span> <span data-ttu-id="67b72-109">다음 창이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-109">The following window is displayed.</span></span>
  
![세트 옵션 분석](../media/c3ec7a92-8484-4812-b98c-aa3eb740e5b7.png)
  
 <span data-ttu-id="67b72-111">**중복에 가까운 전자 메일 스레드** 분석을 실행하려는 경우 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-111">**Near-duplicates and email threads** Check this box if you want to run the analysis.</span></span> <span data-ttu-id="67b72-112">이 옵션은 기본적으로 선택되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-112">It is selected by default.</span></span> 
  
 <span data-ttu-id="67b72-113">**문서 유사성** 중복에 가까운 임계값을 입력하거나 기본값인 65%를 수락합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-113">**Document similarity** Enter the Near-duplicates threshold value or accept the default of 65%.</span></span> 
  
 <span data-ttu-id="67b72-114">**테마** 모든 파일을 처리하고 테마를 할당하려면 이 확인란을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-114">**Themes** Check this box to process all files and assign themes to them.</span></span> <span data-ttu-id="67b72-115">기본적으로 이 확인란은 선택되어 있지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-115">By default, this check box is not selected.</span></span> <span data-ttu-id="67b72-116">테마 처리를 수행하려는 경우 다음 옵션을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-116">Enter the following options if you want to perform Themes processing.</span></span>
  
- <span data-ttu-id="67b72-117">**최대 테마 수** 만들 테마 수에 대한 값을 입력하거나 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-117">**Max number of themes** Enter or select a value for the number of themes to create.</span></span> <span data-ttu-id="67b72-118">기본값은 200입니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-118">The default is 200.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="67b72-119">테마 수를 늘리면 성능과 테마를 일반화할 수 있는 능력에 영향을 미치게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-119">Increasing the number of themes affects performance, as well as the ability of a theme to generalize.</span></span> <span data-ttu-id="67b72-120">테마 수가 높을수록 테마 수가 세분화됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-120">The higher the number of themes, the more granular they are.</span></span> <span data-ttu-id="67b72-121">예를 들어 50개 테마 집합에 "바스켓, 스퍼, 클립퍼, 호반" 같은 테마가 포함된 경우 300개의 테마에는 "Spurs", "Clippers", "Lakers"라는 별도의 테마가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-121">For example, if a set of 50 themes include a theme such as "Basketball, Spurs, Clippers, Lakers"; 300 themes may include separate themes: "Spurs", "Clippers", "Lakers".</span></span> <span data-ttu-id="67b72-122">"바스켓"을 인식하지 못하고 ECA에 이 기능을 사용하는 경우 "바스켓"을 보는 것이 유용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-122">If you had no awareness of the theme "Basketball" and use this feature for ECA, seeing the theme "Basketball" could be useful.</span></span> <span data-ttu-id="67b72-123">그러나 처리에 테마가 너무 많을 경우 "바스켓"이라는 단어가 전혀 표시되지 않을 수 있으며, 스퍼와 클립퍼가 부팅을 진행하고 머리에 사용되는 항목이 아니라 검토하기에 좋은 바스켓 테마라는 것을 알지 못합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-123">But, if the processing had too many themes, you may never see the word "Basketball" and may not know that Spurs and Clippers are good Basketball themes to review, rather than items that go on boots and used for hair.</span></span> 
  
- <span data-ttu-id="67b72-124">**추천 테마** 테마 처리를 제어하기 위해 테마 단어를 제안할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-124">**Suggested themes** You can suggest theme words to control Themes processing.</span></span> <span data-ttu-id="67b72-125">Advanced eDiscovery는 이러한 추천 단어에 초점을 맞추고 "최대 테마 수" 설정에 따라 하나 이상의 관련 테마를 만들려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-125">Advanced eDiscovery will focus on these suggested words and try to create one or more relevant themes, based on the "Max number of themes" settings.</span></span> 
    
    <span data-ttu-id="67b72-126">예를 들어 추천 단어가 "컴퓨터"이고 "2"를 "최대 테마 수"로 지정한 경우 Advanced eDiscovery는 단어 "computer"에 관련된 두 개의 테마를 생성하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-126">For example, if the suggested word is "computer", and you specified "2" as the "Max number of Themes", Advanced eDiscovery will try to generate two themes that relate to the word "computer".</span></span> <span data-ttu-id="67b72-127">예를 들어 두 테마는 "컴퓨터 소프트웨어" 및 "컴퓨터 하드웨어"일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-127">The two themes might be "computer software" and "computer hardware", for example.</span></span> 
    
    ![추천된 테마 추가](../media/06e9ffd3-a76c-423b-b450-9e465eb9a02f.png)
  
1. <span data-ttu-id="67b72-129">제안된 테마를 보거나 추가하거나 편집하려면 수정을 **클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="67b72-129">To view, add, or edit suggested themes, click **Modify**.</span></span>
    
2. <span data-ttu-id="67b72-130">추천 테마 **패널에서** 아이콘 추가  아이콘을 클릭하여 ![ ](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 테마를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-130">In the **Suggested themes** panel, click the **Add** ![add icon](../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) icon to add a theme.</span></span> <span data-ttu-id="67b72-131">제안된 **테마 추가 패널에서** 각 단어를 COMMA로 구분하여 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-131">In the **Add suggested theme** panel, add the words, separated by commas.</span></span> 
    
3. <span data-ttu-id="67b72-132">테마 **수에서** 고급 eDiscovery가 이러한 단어에 대해 생성하려고 시도할 테마 수를 결정하는 값을 선택합니다(기본값은 1개 테마).</span><span class="sxs-lookup"><span data-stu-id="67b72-132">In **Number of themes**, select a value to determine the number of themes Advanced eDiscovery will try to generate for these words (default is 1 theme).</span></span>
    
4. <span data-ttu-id="67b72-133">**저장을** 클릭한 다음 대화 상자를 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-133">Click **Save** and then close the dialogue.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="67b72-134">총 테마 수에는 추천 테마가 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-134">The total number of themes includes Suggested Themes.</span></span> <span data-ttu-id="67b72-135">총 추천 테마는 총 테마를 초과할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-135">The total Suggested Themes cannot exceed the total themes.</span></span> <span data-ttu-id="67b72-136">전체 테마를 상대로 추천 테마가 많은 경우 대부분의 테마는 추천 테마 전용이기 때문에 시스템에서 몇 가지 "소설" 테마만 검색됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-136">If there are many Suggested Themes relative to the total themes, only a few "novel" themes will be detected by the system because most of the themes will be dedicated to Suggested Themes.</span></span> 
  
- <span data-ttu-id="67b72-137">**모드** 드롭다운 목록에서 테마 **옵션을** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-137">**Mode** From the drop-down list, select a **Themes** option:</span></span> 
    
  - <span data-ttu-id="67b72-138">**모델 만들기 및** 적용: 파일 세그먼트에서 모델별로 테마를 계산한 다음 여러 모델에 파일을 배포합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-138">**Create and apply model**: Calculates themes by models from a segment of the files and then distributes files among them.</span></span>
    
  - <span data-ttu-id="67b72-139">**모델 만들기:** 파일 세그먼트에서 테마 모델을 계산합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-139">**Create model**: Calculates a themes model from a segment of the files.</span></span> <span data-ttu-id="67b72-140">파일 세분화 적용 프로세스는 다른 시기에 별도로 수행됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-140">The Apply process of dividing files is done separately at another time.</span></span>
    
  - <span data-ttu-id="67b72-141">**모델 적용**: 이 옵션은 이전에 모델을 만들 때만 표시되고 아직 적용되지 않은 경우 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-141">**Apply model**: This option is only shown if a model was created previously and not yet applied.</span></span> <span data-ttu-id="67b72-142">이렇게 하면 테마에 따라 파일이 분할됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-142">This will divide the files based on the themes.</span></span>
    
<span data-ttu-id="67b72-143">무시 텍스트를 [설정하고](set-ignore-text-in-advanced-ediscovery.md) [분석에 대한 고급 설정 분석도](set-analyze-advanced-settings-in-advanced-ediscovery.md) 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-143">You can also [set ignore text](set-ignore-text-in-advanced-ediscovery.md) and [set Analyze advanced settings](set-analyze-advanced-settings-in-advanced-ediscovery.md) for Analyze.</span></span> 
  
<span data-ttu-id="67b72-144">이러한 옵션을 설정한 후  분석하여 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-144">After you've set these options, click **Analyze** to run.</span></span> <span data-ttu-id="67b72-145">[분석 결과 보기가](view-analyze-results-in-advanced-ediscovery.md) 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="67b72-145">[View Analyze results](view-analyze-results-in-advanced-ediscovery.md) are displayed.</span></span> 
  
## <a name="related-topics"></a><span data-ttu-id="67b72-146">관련 항목</span><span class="sxs-lookup"><span data-stu-id="67b72-146">Related topics</span></span>

[<span data-ttu-id="67b72-147">고급 eDiscovery (클래식)</span><span class="sxs-lookup"><span data-stu-id="67b72-147">Advanced eDiscovery (classic)</span></span>](office-365-advanced-ediscovery.md)
  
[<span data-ttu-id="67b72-148">문서 유사성 이해</span><span class="sxs-lookup"><span data-stu-id="67b72-148">Understanding document similarity</span></span>](understand-document-similarity-in-advanced-ediscovery.md)
  
[<span data-ttu-id="67b72-149">무시 텍스트 설정 </span><span class="sxs-lookup"><span data-stu-id="67b72-149">Set Ignore text </span></span>](set-ignore-text-in-advanced-ediscovery.md)
  
[<span data-ttu-id="67b72-150">고급 설정 설정 분석</span><span class="sxs-lookup"><span data-stu-id="67b72-150">Set Analyze advanced settings</span></span>](set-analyze-advanced-settings-in-advanced-ediscovery.md)
  
[<span data-ttu-id="67b72-151">결과 분석 보기</span><span class="sxs-lookup"><span data-stu-id="67b72-151">View Analyze results</span></span>](view-analyze-results-in-advanced-ediscovery.md)

