---
title: 문서 라이브러리에 문서 이해 모델 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: Priority
description: SharePoint 문서 라이브러리에 게시된 모델을 적용하는 방법 알아보기
ms.openlocfilehash: 771b0f451d404c6e90f62091ca466bfaf34bae39
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338676"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="d5d5c-103">Microsoft SharePoint 구문에서 문서 이해 모델 적용</span><span class="sxs-lookup"><span data-stu-id="d5d5c-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="d5d5c-104">문서 이해 모델을 게시한 후, Microsoft 365 테넌트에서 하나 이상의 SharePoint 문서 라이브러리에 이를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="d5d5c-105">액세스할 수 있는 문서 라이브러리에만 모델을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="d5d5c-106">문서 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-106">Apply your model to a document library.</span></span>

<span data-ttu-id="d5d5c-107">SharePoint 문서 라이브러리에 모델 적용하기:</span><span class="sxs-lookup"><span data-stu-id="d5d5c-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="d5d5c-108">모델 홈페이지의 **라이브러리에 모델 적용** 타일에서 **모델 게시**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="d5d5c-109">또는 **이 모델 라이브러리** 섹션에서 **+라이브러리 추가**를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![라이브러리에 모델 추가](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="d5d5c-111">그런 다음, 모델을 적용하려는 문서 라이브러리가 포함된 SharePoint 사이트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="d5d5c-112">사이트가 목록에 표시되지 않는 경우, 검색 상자를 사용하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![사이트 선택](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="d5d5c-114">모델을 적용할 문서 라이브러리에 대한 *목록 관리* 권한 또는 *편집* 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="d5d5c-115">사이트를 선택한 후, 모델을 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="d5d5c-116">샘플에서 *Contoso 사례 추적* 사이트의 *Documents* 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![문서 라이브러리 선택](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="d5d5c-118">모델이 콘텐츠 유형에 연결되어 있으므로 라이브러리에 적용하면 추출한 레이블이 열로 표시되는 컨텐츠 유형 및 보기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="d5d5c-119">이 보기는 기본적으로 라이브러리의 기본 보기이지만, **고급 설정**을 선택하고 **이 새 보기를 기본값으로 설정**을 선택 취소하여 선택적으로 기본 보기가되지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![라이브러리 보기](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="d5d5c-121">라이브러리에 모델을 적용하려면 **추가**를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="d5d5c-122">모델 홈페이지의 **모델이있는 라이브러리** 섹션에서 나열된 SharePoint 사이트의 URL이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![선택된 라이브러리](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="d5d5c-124">문서 라이브러리로 이동하여 모델의 문서 라이브러리 보기에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="d5d5c-125">문서 라이브러리 이름 옆에 있는 정보 단추를 선택하면 모델이 문서 라이브러리에 적용되었다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-125">Notice that if you select the information button next to the document library name, a message notes that your model has been applied to the document library.</span></span>

    ![정보 보기](../media/content-understanding/info-du.png)</br> 


<span data-ttu-id="d5d5c-127">문서 라이브러리에 모델을 적용한 후, 사이트에 문서 업로드를 시작하고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-127">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="d5d5c-128">모델은 모델에 연결된 콘텐츠 유형이 있는 모든 파일을 식별하고 보기에 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-128">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="d5d5c-129">모델에 추출기가 있는 경우, 각 파일에서 추출하는 데이터에 대한 열이 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-129">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="d5d5c-130">문서 라이브러리에 이미 있는 파일에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="d5d5c-130">Apply the model to files already in the document library</span></span>

<span data-ttu-id="d5d5c-131">적용된 모델이 문서 라이브러리에 적용된 후 문서 라이브러리에 업로드 한 모든 파일을 처리하는 동안, 다음을 수행하여 모델이 적용되기 전에 문서 라이브러리에 이미 있는 파일에 대해 모델을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-131">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="d5d5c-132">문서 라이브러리에서 모델이 처리하려는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-132">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="d5d5c-133">파일을 선택한 후 **분류 및 추출**이 문서 라이브러리 리본에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-133">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="d5d5c-134">**분류 및 추출**을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-134">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="d5d5c-135">선택한 파일이 처리할 큐에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="d5d5c-135">The files you selected will be added to the queue to be processed.</span></span>

      ![분류 및 추출](../media/content-understanding/extract-classify.png)</br> 

## <a name="see-also"></a><span data-ttu-id="d5d5c-137">참고 항목</span><span class="sxs-lookup"><span data-stu-id="d5d5c-137">See Also</span></span>
[<span data-ttu-id="d5d5c-138">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="d5d5c-138">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="d5d5c-139">추출자 만들기</span><span class="sxs-lookup"><span data-stu-id="d5d5c-139">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="d5d5c-140">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="d5d5c-140">Document Understanding overview</span></span>](document-understanding-overview.md)


