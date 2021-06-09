---
title: 'SharePoint Syntex 접근성 모드 '
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Normal
description: Syntex에서 모델을 교육할 때 접근성 모드를 SharePoint 방법을 학습합니다.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515151"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="7fe4d-103">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="7fe4d-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="7fe4d-104">[Syntex에서 SharePoint](index.md)예제 문서로 작업할 때 모든 모델 교육 단계(레이블, 교육, 테스트)에서 접근성 모드를 켜면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="7fe4d-105">접근성 모드를 사용하면 저시계 사용자가 문서 뷰어에서 항목을 탐색하고 레이블을 지정하면 키보드 접근성을 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="7fe4d-106">이렇게 하면 사용자가 키보드를 사용하여 문서 뷰어의 텍스트를 탐색하고 선택한 값뿐만 아니라 선택한 텍스트에서 레이블 지정 또는 레이블 제거와 같은 작업이나 추가 예제 문서로 모델을 학습할 때 예측된 레이블 값에 대한 설명을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![접근성 모드](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="7fe4d-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="7fe4d-108">Requirements</span></span>

<span data-ttu-id="7fe4d-109">내레이션의 오디오를 재생하려면 내레이터 시스템의 내레이터 [설정에서](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) Windows 10 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![설정 내레이터](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="7fe4d-111">키보드 사용자를 위한 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="7fe4d-111">Labeling for keyboard users</span></span>

<span data-ttu-id="7fe4d-112">접근성 모드를 사용하는 키보드 사용자의 경우 뷰어의 예제 문서에서 텍스트에 레이블을 지정하는 경우 다음 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="7fe4d-113">탭: 앞으로 이동하고 다음 단어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="7fe4d-114">Tab + Shift: 뒤로 이동하여 이전 단어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="7fe4d-115">Enter: 레이블을 지정하거나 선택한 단어에서 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="7fe4d-116">오른쪽 화살표: 선택한 단어의 개별 문자 앞으로 이동</span><span class="sxs-lookup"><span data-stu-id="7fe4d-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="7fe4d-117">왼쪽 화살표: 선택한 단어의 개별 문자를 뒤로 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="7fe4d-118">단일 레이블에 대해 여러 단어에 레이블을 지정하는 경우 각 단어에 레이블을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="7fe4d-119">내레이션</span><span class="sxs-lookup"><span data-stu-id="7fe4d-119">Narration</span></span>

<span data-ttu-id="7fe4d-120">접근성 모드를 내레이터 사용자의 경우 키보드 사용자가 뷰어의 예제 문서를 탐색할 수 있도록 설명된 동일한 키보드 탐색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="7fe4d-121">예제 문서 및 레이블 문자열 값을 탐색할 때 내레이터 다음과 같은 오디오 프롬프트가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="7fe4d-122">키보드를 사용하여 문서 뷰어를 탐색하면 내레이터 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="7fe4d-123">선택한 문자열 내에서 내레이터 화살표 키를 사용하여 문자열의 각 문자를 선택할 때 오디오에 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="7fe4d-124">레이블이 지정된 문자열을 선택하면 내레이터 다음 "레이블이 지정"됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="7fe4d-125">예를 들어 레이블 값이 "Contoso"이면 "Costoso 레이블이 지정"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="7fe4d-126">교육 탭에서 예측된 것으로만 예측된 문자열을 문서 뷰어에서 선택하면 내레이터 오디오에서 값을 설명한 다음 "예측"됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="7fe4d-127">이는 교육에서 사용자가 레이블을 지정한 값과 일치하지 않는 파일의 값을 예측할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="7fe4d-128">교육 탭에서 레이블이 지정되고 예측된 문서 뷰어에서 문자열을 선택하면 내레이터 오디오에 값이 설명된 다음 "레이블이 지정되고 예측됩니다."라는 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="7fe4d-129">이는 교육이 성공하고 예측된 값과 사용자 레이블이 일치할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="7fe4d-130">문자열에 레이블이 지정되거나 뷰어에서 레이블이 제거된 후 내레이터 종료하기 전에 오디오에 변경 내용을 저장해야 하다는 경고가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fe4d-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fe4d-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fe4d-131">See Also</span></span>

[<span data-ttu-id="7fe4d-132">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="7fe4d-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="7fe4d-133">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="7fe4d-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



