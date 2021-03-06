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
description: SharePoint Syntex에서 모델을 교육할 때 접근성 모드를 사용하는 방법을 학습합니다.
ms.openlocfilehash: 5f6e9d542f3d41dbddacd54b1b379910dcb0c9dc
ms.sourcegitcommit: babbba2b5bf69fd3facde2905ec024b753dcd1b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/06/2021
ms.locfileid: "50515151"
---
# <a name="sharepoint-syntex-accessibility-mode"></a><span data-ttu-id="d4d26-103">SharePoint Syntex 접근성 모드</span><span class="sxs-lookup"><span data-stu-id="d4d26-103">SharePoint Syntex accessibility mode</span></span>

<span data-ttu-id="d4d26-104">[SharePoint Syntex에서](index.md)사용자는 예제 문서로 작업할 때 모든 모델 교육 단계(레이블, 교육, 테스트)에서 접근성 모드를 켜는 기능을 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-104">In [SharePoint Syntex](index.md), users can turn on accessibility mode in all stages of model training (label, train, test) when working with example documents.</span></span> <span data-ttu-id="d4d26-105">접근성 모드를 사용하면 저시계 사용자가 문서 뷰어에서 항목을 탐색하고 레이블을 지정하면 키보드 접근성을 보다 쉽게 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-105">Using accessibility mode can help low-sight users to have easier keyboard accessibility as they navigate and label items in the document viewer.</span></span>

<span data-ttu-id="d4d26-106">이렇게 하면 사용자가 키보드를 사용하여 문서 뷰어의 텍스트를 탐색하고 선택한 값뿐만 아니라 선택한 텍스트에서 레이블 지정 또는 레이블 제거와 같은 작업이나 추가 예제 문서로 모델을 학습할 때 예측된 레이블 값에 대한 설명을 들을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-106">This helps users to use their keyboards to navigate through text in the document viewer and to hear a narration of not only the selected values, but also of actions (such as labeling or removing labeling from selected text), or predicted label values as you train the model with additional example documents.</span></span> 


![접근성 모드](../media/content-understanding/accessibility-mode.png)

## <a name="requirements"></a><span data-ttu-id="d4d26-108">요구 사항</span><span class="sxs-lookup"><span data-stu-id="d4d26-108">Requirements</span></span>

<span data-ttu-id="d4d26-109">내레이션의 오디오를 들으하려면 Windows 10 [](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) 시스템의 내레이터 설정에서 내레이터 앱을 켜야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-109">To hear the audio of the narration, make sure to turn on the [Narrator App](https://support.microsoft.com/windows/complete-guide-to-narrator-e4397a0d-ef4f-b386-d8ae-c172f109bdb1) in your Narrator settings on your Windows 10 system.</span></span>

![내레이터 켜기](../media/content-understanding/narrator-settings.png)

## <a name="labeling-for-keyboard-users"></a><span data-ttu-id="d4d26-111">키보드 사용자를 위한 레이블 지정</span><span class="sxs-lookup"><span data-stu-id="d4d26-111">Labeling for keyboard users</span></span>

<span data-ttu-id="d4d26-112">접근성 모드를 사용하는 키보드 사용자의 경우 뷰어의 예제 문서에서 텍스트에 레이블을 지정하는 경우 다음 키를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-112">For keyboard users using accessibility mode, if you are labeling text in an example document in the viewer, you can use the following keys:</span></span>

- <span data-ttu-id="d4d26-113">탭: 앞으로 이동하고 다음 단어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-113">Tab: Moves you forward and selects the next word.</span></span>
- <span data-ttu-id="d4d26-114">Tab + Shift: 뒤로 이동하여 이전 단어를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-114">Tab + Shift: Moves you backwards and selects the previous word.</span></span>
- <span data-ttu-id="d4d26-115">Enter: 레이블을 지정하거나 선택한 단어에서 레이블을 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-115">Enter: Label or removes a label from the selected word.</span></span>
- <span data-ttu-id="d4d26-116">오른쪽 화살표: 선택한 단어의 개별 문자 앞으로 이동</span><span class="sxs-lookup"><span data-stu-id="d4d26-116">Right arrow: Moves you forward through individual characters in a selected word.</span></span>
- <span data-ttu-id="d4d26-117">왼쪽 화살표: 선택한 단어의 개별 문자를 뒤로 움직입니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-117">Left arrow: Moves you backward through individual characters in a selected word.</span></span>

> [!NOTE]
> <span data-ttu-id="d4d26-118">단일 레이블에 대해 여러 단어에 레이블을 지정하는 경우 각 단어에 레이블을 지정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-118">If you are labeling multiple words for a single label, you need to label each word.</span></span>


## <a name="narration"></a><span data-ttu-id="d4d26-119">내레이션</span><span class="sxs-lookup"><span data-stu-id="d4d26-119">Narration</span></span>

<span data-ttu-id="d4d26-120">내레이터 사용자가 접근성 모드를 사용하는 경우 키보드 사용자가 뷰어의 예제 문서를 탐색할 수 있도록 설명된 동일한 키보드 탐색을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-120">For Narrator users using accessibility mode, use the same keyboard navigation described for keyboard users to go through the example document in the viewer.</span></span>

<span data-ttu-id="d4d26-121">예제 문서 및 레이블 문자열 값을 탐색할 때 내레이터는 사용자에게 다음과 같은 오디오 프롬프트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-121">As you navigate through the sample documents and label string values, Narrator will give user the following audio prompts:</span></span>

- <span data-ttu-id="d4d26-122">키보드를 사용하여 문서 뷰어를 탐색하면 내레이터 오디오에 선택한 문자열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-122">When you use the keyboard to navigate through the document viewer, Narrator audio will state the selected string.</span></span>
- <span data-ttu-id="d4d26-123">선택한 문자열 내에서 내레이터 오디오는 왼쪽 또는 오른쪽 화살표 키를 사용하여 문자열의 각 문자를 선택할 때 해당 문자를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-123">Within a selected string, Narrator audio will state each character in the string as you select them by using the left or right arrow keys.</span></span>
- <span data-ttu-id="d4d26-124">레이블이 지정된 문자열을 선택하면 내레이터가 값을 지정한 다음 "레이블이 지정"됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-124">If you select a string that has been labeled, Narrator will state the value and then "labeled".</span></span>  <span data-ttu-id="d4d26-125">예를 들어 레이블 값이 "Contoso"이면 "Costoso 레이블이 지정"으로 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-125">For example, if the label value is "Contoso", it will state "Costoso labeled".</span></span> 
- <span data-ttu-id="d4d26-126">교육 탭에서 예측된 것으로만 볼 수 있는 문자열을 문서 뷰어에서 선택하면 내레이터 오디오에 값이 설명된 다음 "예측"됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-126">In the training tab, if you select a string in the document viewer that has only been predicted, Narrator audio will state the value, and then "predicted".</span></span> <span data-ttu-id="d4d26-127">이는 교육에서 사용자가 레이블을 지정한 값과 일치하지 않는 파일의 값을 예측할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-127">This occurs when training predicts a value in the file that does not match what has been labeled by the user.</span></span>
- <span data-ttu-id="d4d26-128">교육 탭에서 레이블이 지정되고 예측된 문서 뷰어에서 문자열을 선택하면 내레이터 오디오에서 값을 표시한 다음 "레이블이 지정되고 예측됩니다."라는 설명이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-128">In the training tab, if you select a string in the document viewer that has been labeled and predicted, Narrator audio will state the value, and then "labeled and predicted".</span></span> <span data-ttu-id="d4d26-129">이는 교육이 성공하고 예측된 값과 사용자 레이블이 일치할 때 발생합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-129">This occurs when training is successful and there is a match between a predicted value and the user label.</span></span>



<span data-ttu-id="d4d26-130">문자열에 레이블이 지정되거나 뷰어에서 레이블이 제거되면 내레이터 오디오는 종료하기 전에 변경 내용을 저장하는 경고를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="d4d26-130">After a string is labeled or a label has been removed in the viewer, Narrator audio will warn you to save your changes before you exit.</span></span>

## <a name="see-also"></a><span data-ttu-id="d4d26-131">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d4d26-131">See Also</span></span>

[<span data-ttu-id="d4d26-132">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="d4d26-132">Create an extractor</span></span>](create-an-extractor.md)</br>

[<span data-ttu-id="d4d26-133">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="d4d26-133">Create a classifier</span></span>](create-a-classifier.md)</br>










 


  
  



