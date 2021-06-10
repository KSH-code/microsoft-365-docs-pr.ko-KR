---
title: 문서 라이브러리에 문서 이해 모델 적용
ms.author: efrene
author: efrene
manager: pamgreen
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Normal
description: SharePoint 문서 라이브러리에 게시된 모델을 적용하는 방법 알아보기
ms.openlocfilehash: cda9de43d0139c52f950527eb75d050602005fd2
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843297"
---
# <a name="apply-a-document-understanding-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="2bf04-103">Microsoft SharePoint 구문에서 문서 이해 모델 적용</span><span class="sxs-lookup"><span data-stu-id="2bf04-103">Apply a document understanding model in Microsoft SharePoint Syntex</span></span>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CSoL]

</br>

<span data-ttu-id="2bf04-104">문서 이해 모델을 게시한 후, Microsoft 365 테넌트에서 하나 이상의 SharePoint 문서 라이브러리에 이를 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-104">After publishing your document understanding model, you can apply it to one or more SharePoint document library in your Microsoft 365 tenant.</span></span>

> [!NOTE]
> <span data-ttu-id="2bf04-105">액세스할 수 있는 문서 라이브러리에만 모델을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-105">You are only able to apply the model to document libraries that you have access to.</span></span>


## <a name="apply-your-model-to-a-document-library"></a><span data-ttu-id="2bf04-106">문서 라이브러리에 모델을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-106">Apply your model to a document library.</span></span>

<span data-ttu-id="2bf04-107">SharePoint 문서 라이브러리에 모델 적용하기:</span><span class="sxs-lookup"><span data-stu-id="2bf04-107">To apply your model to to a SharePoint document library:</span></span>

1. <span data-ttu-id="2bf04-108">모델 홈페이지의 **라이브러리에 모델 적용** 타일에서 **모델 게시** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-108">On model home page, on the **Apply model to libraries** tile, select **Publish model**.</span></span> <span data-ttu-id="2bf04-109">또는 **이 모델 라이브러리** 섹션에서 **+라이브러리 추가** 를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-109">Or you can select  **+Add Library** in the **Libraries with this model** section.</span></span> </br>

    ![라이브러리에 모델 추가](../media/content-understanding/apply-to-library.png)</br>

2. <span data-ttu-id="2bf04-111">그런 다음, 모델을 적용하려는 문서 라이브러리가 포함된 SharePoint 사이트를 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-111">You can then select the SharePoint site that contains the document library that you want to apply the model to.</span></span> <span data-ttu-id="2bf04-112">사이트가 목록에 표시되지 않는 경우, 검색 상자를 사용하여 찾습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-112">If the site does not show in the list, use the search box to find it.</span></span></br>

    ![사이트 선택](../media/content-understanding/site-search.png)</br>

    > [!NOTE]
    > <span data-ttu-id="2bf04-114">모델을 적용할 문서 라이브러리에 대한 *목록 관리* 권한 또는 *편집* 권한이 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-114">You must have *Manage List* permissions or *Edit* rights to the document library you are applying the model to.</span></span></br>

3. <span data-ttu-id="2bf04-115">사이트를 선택한 후, 모델을 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-115">After selecting the site, select the document library to which you want to apply the model.</span></span> <span data-ttu-id="2bf04-116">샘플에서 *Contoso 사례 추적* 사이트의 *Documents* 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-116">In the sample, select the *Documents* document library from the *Contoso Case Tracking* site.</span></span></br>

    ![문서 라이브러리 선택](../media/content-understanding/select-doc-library.png)</br>

4. <span data-ttu-id="2bf04-118">모델이 콘텐츠 유형에 연결되어 있으므로 라이브러리에 적용하면 추출한 레이블이 열로 표시되는 컨텐츠 유형 및 보기가 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-118">Since the model is associated to a content type, when you apply it to the library it will add the content type and its view with the labels you extracted showing as columns.</span></span> <span data-ttu-id="2bf04-119">이 보기는 기본적으로 라이브러리의 기본 보기이지만, **고급 설정** 을 선택하고 **이 새 보기를 기본값으로 설정** 을 선택 취소하여 선택적으로 기본 보기가되지 않도록 선택할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-119">This view is the library's default view by default, but you can optionally choose to not have it be the default view by selecting **Advanced settings** and deselecting **Set this new view as default**.</span></span></br>

    ![라이브러리 보기](../media/content-understanding/library-view.png)</br>

5. <span data-ttu-id="2bf04-121">라이브러리에 모델을 적용하려면 **추가** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-121">Select **Add** to apply the model to the library.</span></span> 
6. <span data-ttu-id="2bf04-122">모델 홈페이지의 **모델이있는 라이브러리** 섹션에서 나열된 SharePoint 사이트의 URL이 표시되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-122">On the model home page, in the **Libraries with this model** section, you should see the URL to the SharePoint site listed.</span></span></br>

    ![선택된 라이브러리](../media/content-understanding/selected-library.png)</br>

7. <span data-ttu-id="2bf04-124">문서 라이브러리로 이동하여 모델의 문서 라이브러리 보기에 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-124">Go to your document library and make sure you are in the model's document library view.</span></span> <span data-ttu-id="2bf04-125">문서 라이브러리 이름 옆에 있는 정보 단추를 선택하면 문서 라이브러리에 모델이 적용되었다는 메시지가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-125">Notice that if you select the information button next to the document library name, a message notes that the document library has a model applied to it.</span></span>

    ![정보 보기](../media/content-understanding/info-du.png)</br> 

    <span data-ttu-id="2bf04-127">**활성 모델 보기** 선택하여 문서 라이브러리에 적용된 모델에 대한 세부 정보를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-127">You can the select **View active models** to see details about any models that are applied to the document library.</span></span>

8. <span data-ttu-id="2bf04-128">**활성 모델** 창에서 문서 라이브러리에 적용된 모델을 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-128">In the **Active models** pane, you can see the models that are applied to the document library.</span></span> <span data-ttu-id="2bf04-129">모델을 선택하여 모델에 대한 설명, 모델 게시자, 모델이 분류된 파일에 보존 레이블을 적용하는 경우와 같은 모델에 대한 자세한 정보를 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-129">Select a model to see more details about it, such as a description of the model, who published the model, and if the model applies a retention label to the files it classifies.</span></span>

    ![활성 모델 창](../media/content-understanding/active-models.png)</br> 

<span data-ttu-id="2bf04-131">문서 라이브러리에 모델을 적용한 후, 사이트에 문서 업로드를 시작하고 결과를 볼 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-131">After applying the model to the document library, you can begin uploading documents to the site and see the results.</span></span>

<span data-ttu-id="2bf04-132">모델은 모델에 연결된 콘텐츠 유형이 있는 모든 파일을 식별하고 보기에 나열합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-132">The model identifies any files with model’s associated content type and lists them in your view.</span></span> <span data-ttu-id="2bf04-133">모델에 추출기가 있는 경우, 각 파일에서 추출하는 데이터에 대한 열이 보기에 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-133">If your model has any extractors, the view displays columns for the data you are extracting from each file.</span></span>

### <a name="apply-the-model-to-files-already-in-the-document-library"></a><span data-ttu-id="2bf04-134">문서 라이브러리에 이미 있는 파일에 모델 적용</span><span class="sxs-lookup"><span data-stu-id="2bf04-134">Apply the model to files already in the document library</span></span>

<span data-ttu-id="2bf04-135">적용된 모델이 문서 라이브러리에 적용된 후 문서 라이브러리에 업로드 한 모든 파일을 처리하는 동안, 다음을 수행하여 모델이 적용되기 전에 문서 라이브러리에 이미 있는 파일에 대해 모델을 실행할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-135">While an applied model processes all files uploaded to the document library after it is applied, you can also do the following to run the model on files that already exists in the document library prior to the model being applied:</span></span>

1. <span data-ttu-id="2bf04-136">문서 라이브러리에서 모델이 처리하려는 파일을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-136">In your document library, select the files that you want to be processed by your model.</span></span>
2. <span data-ttu-id="2bf04-137">파일을 선택한 후 **분류 및 추출** 이 문서 라이브러리 리본에 나타납니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-137">After selecting your files, **Classify and extract** will appear in the document library ribbon.</span></span> <span data-ttu-id="2bf04-138">**분류 및 추출** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-138">Select **Classify and extract**.</span></span>
3. <span data-ttu-id="2bf04-139">선택한 파일이 처리할 큐에 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-139">The files you selected will be added to the queue to be processed.</span></span>

      ![분류 및 추출](../media/content-understanding/extract-classify.png)</br> 

> [!NOTE]
> <span data-ttu-id="2bf04-141">개별 파일을 라이브러리에 복사하여 모델에 적용할 수 있지만 폴더는 적용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-141">You can copy individual files to a library and apply them to a model, but not folders.</span></span>

### <a name="the-classification-date-field"></a><span data-ttu-id="2bf04-142">분류 날짜 필드</span><span class="sxs-lookup"><span data-stu-id="2bf04-142">The Classification Date field</span></span>

<span data-ttu-id="2bf04-143">SharePoint Syntex 문서의 이해 또는 양식 처리 모델을 문서 라이브러리에 적용하면 <b>분류 날짜</b> 필드가 라이브러리 스키마에 포함됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-143">When a SharePoint Syntex document understanding or form processing model is applied to a document library, a <b> Classification date </b> field is included in the library schema.</span></span> <span data-ttu-id="2bf04-144">기본적으로 이 필드는 비어 있지만, 문서가 모델에 의해 처리되고 분류되면 이 필드가 완료 날짜-시간 스탬프로 업데이트됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-144">By default this field is empty, but when documents are processed and classified by a model, this field is updated with a date-time stamp of completion.</span></span> 

   ![분류 날짜 열](../media/content-understanding/class-date-column.png)</br> 

<span data-ttu-id="2bf04-146">분류 날짜 필드는 Syntex 콘텐츠 이해 모델이 파일 처리를 완료하고 "분류 날짜" 필드를 업데이트한 후 Power Automate 흐름을 실행하기 위해 [<b>콘텐츠 이해 모델에 의해 파일이 분류되는 경우</b> 트리거](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model)에서 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-146">The Classification date field is used by the [<b>When a file is classified by a content understanding model</b> trigger](/connectors/sharepointonline/#when-a-file-is-classified-by-a-content-understanding-model) to run a Power Automate flow after a Syntex content understanding model has finished processing a file and updated the "Classification date" field.</span></span>

   ![흐름 트리거](../media/content-understanding/trigger.png)</br>

<span data-ttu-id="2bf04-148"><b>콘텐츠 이해 모델에 의해 파일이 분류되는 경우</b> 트리거를 사용하여 파일에서 추출한 정보로 다른 워크플로를 시작할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2bf04-148">The <b>When a file is classified by a content understanding model</b> trigger can then be used to start another workflow using any  extracted information from the file.</span></span>



## <a name="see-also"></a><span data-ttu-id="2bf04-149">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2bf04-149">See Also</span></span>
[<span data-ttu-id="2bf04-150">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="2bf04-150">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="2bf04-151">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="2bf04-151">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="2bf04-152">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="2bf04-152">Document Understanding overview</span></span>](document-understanding-overview.md)
