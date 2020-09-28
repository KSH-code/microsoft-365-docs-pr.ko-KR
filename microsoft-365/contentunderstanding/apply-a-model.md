---
title: 문서 라이브러리에 문서 이해 모델 적용
ms.author: efrene
author: efrene
manager: pamgreen
ms.date: 8/1/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: SharePoint 문서 라이브러리에 게시 된 모델을 적용 하는 방법 알아보기
ms.openlocfilehash: c693fa08bf3103eca01e01774e8f8b1d9e783b07
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295493"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="73275-103">Microsoft SharePoint Syntex에서 문서 이해 모델 적용</span><span class="sxs-lookup"><span data-stu-id="73275-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="73275-104">이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다.</span><span class="sxs-lookup"><span data-stu-id="73275-104">The content in this article is for the the Project Cortex Private Preview.</span></span> <span data-ttu-id="73275-105">[자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</span><span class="sxs-lookup"><span data-stu-id="73275-105">[Find out more about Project Cortex](https://aka.ms/projectcortex).</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="73275-106">모델 이해 문서를 게시 한 후 Microsoft 365 테 넌 트에서 SharePoint 문서 라이브러리에이를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-106">After publishing your document understanding model, you can apply it to a SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="73275-107">액세스 권한이 있는 문서 라이브러리에만 모델을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-107">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="73275-108">문서 라이브러리에 모델을 적용 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-108">Apply your model to a document library.</span></span>

<span data-ttu-id="73275-109">SharePoint 문서 라이브러리에 모델을 적용 하려면 다음을 수행 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-109">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="73275-110">모델 홈 페이지의 **라이브러리에 모델 적용** 타일에서 **모델 게시**를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-110">From the model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="73275-111">또는 **다음 모델** 의 라이브러리에서 **라이브러리 추가** 섹션을 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-111">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![라이브러리에 모델 추가](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="73275-113">모델을 적용 하려는 문서 라이브러리가 포함 된 SharePoint 사이트를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-113">Select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="73275-114">사이트가 목록에 표시 되지 않으면 검색 상자를 사용 하 여 해당 사이트를 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-114">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![사이트 선택](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="73275-116">모델을 적용할 문서 라이브러리에 대 한 목록 사용 권한 *관리* 또는 *편집* 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-116">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="73275-117">사이트를 선택한 후 모델을 적용할 문서 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-117">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="73275-118">예제에서 *Contoso 사례 추적* 사이트의 *문서* 문서 라이브러리를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-118">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![문서 라이브러리 선택](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="73275-120">모델은 콘텐츠 형식에 연결 되어 있으므로 라이브러리에 적용할 때이를 열로 추출한 레이블로 콘텐츠 형식에 대 한 보기를 만듭니다.</span><span class="sxs-lookup"><span data-stu-id="73275-120">Since the model is associated to a content type, when you apply it to the library it creates a view for the content type with the labels you extracted showing as columns.</span></span> <span data-ttu-id="73275-121">이 보기는 기본적으로 라이브러리의 기본 보기 이며, **고급 설정을** 선택 하 고 **이 새 보기를 기본값으로**선택을 취소 하 여 기본 보기로 설정 하지 않을 수도 있습니다 (선택 사항).</span><span class="sxs-lookup"><span data-stu-id="73275-121">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![라이브러리 보기](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="73275-123">라이브러리에 모델을 적용 하려면 **추가** 를 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-123">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="73275-124">모델 홈 페이지의 **이 모델을 가진 라이브러리** 섹션에서 나열 된 SharePoint 사이트의 URL을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-124">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![선택한 라이브러리](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="73275-126">문서 라이브러리로 이동 하 여 모델의 문서 라이브러리 보기에 있는지 확인 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-126">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="73275-127">문서 라이브러리 이름 옆에 있는 정보 단추를 선택 하면 모델이 문서 라이브러리에 적용 되었음을 알리는 메시지가 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73275-127">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![정보 보기](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="73275-129">문서 라이브러리에 모델을 적용 한 후에는 사이트에 문서 업로드를 시작 하 고 결과를 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-129">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="73275-130">모델은 모델의 연결 된 콘텐츠 형식을 가진 모든 파일을 식별 하 고 보기에 나열 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-130">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="73275-131">모델에 추출기가 있으면 보기에 각 파일에서 추출 하는 데이터의 열이 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73275-131">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="73275-132">문서 라이브러리에 이미 있는 파일에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="73275-132">Apply the model to files already in the document library</span></span>

<span data-ttu-id="73275-133">적용 된 모델을 적용 한 후에 문서 라이브러리에 업로드 된 모든 파일이 처리 되는 동안에는 다음을 수행 하 여 모델을 적용 하기 전에 문서 라이브러리에 이미 있는 파일에서 모델을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="73275-133">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="73275-134">문서 라이브러리에서 모델에 따라 처리할 파일을 선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-134">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="73275-135">파일을 선택한 후 **분류 및 추출** 이 문서 라이브러리 리본 메뉴에 표시 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73275-135">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="73275-136">**분류 및 압축 해제를**선택 합니다.</span><span class="sxs-lookup"><span data-stu-id="73275-136">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="73275-137">선택한 파일이 처리할 큐에 추가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="73275-137">The files you selected will be added to the queue to be processed.</span></span>

      ![분류 및 추출](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="73275-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="73275-139">See Also</span></span>
[<span data-ttu-id="73275-140">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="73275-140">Create a classifier</span></span>](create-a-classifier.md)</br>
[<span data-ttu-id="73275-141">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="73275-141">Create an extractor</span></span>](create-an-extractor.md)</br>
[<span data-ttu-id="73275-142">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="73275-142">Document Understanding overview</span></span>](document-understanding-overview.md)</br>
[<span data-ttu-id="73275-143">양식 처리 모델 만들기</span><span class="sxs-lookup"><span data-stu-id="73275-143">Create a form processing model</span></span>](create-a-form-processing-model.md)  
