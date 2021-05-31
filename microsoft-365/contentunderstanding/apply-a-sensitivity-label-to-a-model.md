---
title: Microsoft SharePoint Syntex에서 모델에 민감도 레이블 적용
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-syntex
localization_priority: Priority
description: SharePoint Syntex에서 모델에 민감도 레이블을 적용하는 방법을 알아봅니다.
ms.openlocfilehash: 799ab3fa0fcdc9af9d227428056d2cd7abeaf539
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706723"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a><span data-ttu-id="648ce-103">Microsoft SharePoint Syntex에서 모델에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="648ce-103">Apply a sensitivity label to a model in Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="648ce-104">Microsoft SharePoint Syntex에서 문서 이해 모델에 [민감도 레이블](../compliance/sensitivity-labels.md)을 쉽게 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-104">You can easily apply a [sensitivity label](../compliance/sensitivity-labels.md) to document understanding models in Microsoft SharePoint Syntex.</span></span> <span data-ttu-id="648ce-105">이 기능은 양식 처리 모델에 아직 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-105">This feature isn't available yet for form processing models.</span></span>

<span data-ttu-id="648ce-106">민감도 레이블을 사용하면 모델이 식별하는 문서에 암호화, 공유 및 조건부 액세스 정책을 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-106">Sensitivity labels let you apply encryption, sharing, and conditional access policies to the documents that your models identify.</span></span> <span data-ttu-id="648ce-107">예를 들어 모델에서 문서 라이브러리에 업로드된 은행 계좌 번호 또는 신용 카드 번호가 포함된 금융 문서를 식별할 뿐만 아니라 *암호화* 민감도 레이블을 적용하여 해당 콘텐츠에 액세스할 수 있는 사용자와 사용 방법을 제한하려고 합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-107">For example, you want your model to not only identify any financial documents that contain bank account numbers or credit card numbers that are uploaded to your document library, but also to apply an *Encryption* sensitivity label to them to restrict who can access that content and how it can be used.</span></span>

<span data-ttu-id="648ce-108">모델의 홈페이지에서 모델 설정을 통해 기존 민감도 레이블을 모델에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-108">You can apply a pre-existing sensitivity label to your model through your model settings on your model's home page.</span></span> <span data-ttu-id="648ce-109">레이블은 모델 설정에서 선택할 수 있도록 이미 게시되어 있어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-109">The label must already be published to be available for selection from model settings.</span></span>

> [!Important]
> <span data-ttu-id="648ce-110">민감도 레이블을 문서 이해 모델에 적용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../business-video/create-sensitivity-labels.md)해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-110">For sensitivity labels to be available to apply to your document understanding models, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).</span></span>

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a><span data-ttu-id="648ce-111">문서 이해 모델에 민감도 레이블 추가</span><span class="sxs-lookup"><span data-stu-id="648ce-111">Add a sensitivity label to a document understanding model</span></span>

1. <span data-ttu-id="648ce-112">모델 홈페이지에서 **모델 설정** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-112">From the model home page, select **Model settings**.</span></span>

   ![모델 설정 옵션이 강조 표시된 모델 페이지의 스크린샷입니다.](../media/content-understanding/sensitivity-model-settings.png)

2. <span data-ttu-id="648ce-114">**모델 설정** 창의 **준수** 섹션에서 **민감도 레이블** 메뉴를 선택하여 모델에 적용할 수 있는 민감도 레이블 목록을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-114">On **Model settings** pane, in the **Compliance** section, select the **Sensitivity label** menu to see a list of sensitivity labels that are available for you to apply to the model.</span></span>

   ![민감도 레이블 메뉴를 보여 주는 모델 설정 창의 스크린샷입니다.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. <span data-ttu-id="648ce-116">모델에 적용할 민감도 레이블을 선택한 다음 **저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-116">Select the sensitivity label you want to apply to the model, and then select **Save**.</span></span>

<span data-ttu-id="648ce-117">모델에 민감도 레이블을 적용한 후 다음 항목에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-117">After you apply the sensitivity label to your model, you can apply it to a:</span></span>

- <span data-ttu-id="648ce-118">새 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="648ce-118">New document library</span></span>
- <span data-ttu-id="648ce-119">모델이 이미 적용된 문서 라이브러리</span><span class="sxs-lookup"><span data-stu-id="648ce-119">Document library to which the model is already applied</span></span>
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a><span data-ttu-id="648ce-120">모델이 이미 적용된 문서 라이브러리에 민감도 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="648ce-120">Apply the sensitivity label to a document library to which the model is already applied</span></span>

<span data-ttu-id="648ce-121">문서 이해 모델이 문서 라이브러리에 이미 적용된 경우 다음을 수행하여 민감도 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-121">If your document understanding model has already been applied to a document library, you can do the following to sync your sensitivity label update to apply it to the document library:</span></span>

1. <span data-ttu-id="648ce-122">모델 홈 페이지의 **이 모델이 있는 라이브러리** 섹션에서 민감도 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-122">On the model home page, in the **Libraries with this model** section, select the document library to which you want to apply the sensitivity label update.</span></span>

2. <span data-ttu-id="648ce-123">**동기화** 를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-123">Select **Sync**.</span></span>

   ![동기화가 강조 표시된 이 모델이 있는 라이브러리 섹션을 보여 주는 스크린샷입니다.](../media/content-understanding/sensitivity-libraries-sync.png)

<span data-ttu-id="648ce-125">업데이트를 적용하고 모델에 동기화한 후 다음 단계를 수행하여 적용되었는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-125">After you apply the update and sync it to your model, you can confirm that it has been applied by doing the following steps:</span></span>

1. <span data-ttu-id="648ce-126">콘텐츠 센터의 **이 모델이 있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-126">In the content center, in the **Libraries with this model** section, select the library to which your updated model was applied.</span></span> 

2. <span data-ttu-id="648ce-127">문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-127">In your document library view, select the information icon to check the model properties.</span></span>

3. <span data-ttu-id="648ce-128">**활성 모델** 목록에서 업데이트된 모델을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-128">In the **Active models** list, select your updated model.</span></span>

4. <span data-ttu-id="648ce-129">**민감도 레이블** 섹션에 적용된 민감도 레이블의 이름이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-129">In the **Sensitivity label** section, you'll see the name of the applied sensitivity label.</span></span>

<span data-ttu-id="648ce-130">문서 라이브러리의 모델 보기 페이지에 새 **민감도 레이블** 열이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-130">On your model's view page in your document library, a new **Sensitivity label** column will display.</span></span> <span data-ttu-id="648ce-131">모델이 콘텐츠 형식에 속하는 것으로 식별하는 파일을 분류하고 라이브러리 보기에 나열할 때 **민감도 레이블** 열에는 모델을 통해 적용된 민감도 레이블의 이름도 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-131">As your model classifies files it identifies as belonging to its content type and lists them in the library view, the **Sensitivity label** column will also display the name of the sensitivity label that has been applied to it through the model.</span></span>

<span data-ttu-id="648ce-132">예를 들어 모델이 식별하는 모든 금융 문서에는 또한 *암호화* 민감도 레이블이 적용되어 권한이 없는 사용자가 액세스할 수 없게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-132">For example, all financial documents that your model identifies also will have the *Encryption* sensitivity label applied to them, preventing them from being accessed by unauthorized people.</span></span> <span data-ttu-id="648ce-133">권한이 없는 사용자가 문서 라이브러리에서 파일에 액세스하려고 하면 적용된 민감도 레이블로 인해 허용되지 않는다는 오류가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="648ce-133">If an attempt is made to access the file from the document library by an unauthorized person, an error will display saying it isn't allowed because of the applied sensitivity label.</span></span>

<!---
## Add a sensitivity label to a form processing model

> [!Important]
> For sensitivity labels to be available to apply to your form processing model, they need to be [created and published in the Microsoft 365 Compliance Center](../business-video/create-sensitivity-labels.md).

You can either apply a sensitivity label to a form processing model when you are creating a model, or apply it to an existing model.

### Add a sensitivity label when you create a form processing model

1. When you [create a new form processing model](create-a-form-processing-model.md), select **Advanced settings**.

2. In **Advanced settings**, in the **Sensitivity label** section, select the menu and then select the sensitivity label you want to apply to the model.

3.  After you've completed your remaining model settings, select **Create** to build your model.

### Add a sensitivity label to an existing form processing model

You can add a sensitivity label to an existing form processing model in different ways:

- Through the **Automate** menu in the document library
- Through the **Active model** settings in the document library 

#### Add a sensitivity label to an existing form processing model through the Automate menu

You can add a sensitivity label to an existing form processing model that you own through the **Automate** menu in the document library in which the model is applied.

1. In your document library to which the form processing model is applied, select the **Automate** menu, select **AI Builder**, and then select **View form processing model details**.

2. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

#### Add a sensitivity label to an existing form processing model in the active model settings

You can add a sensitivity label to an existing form processing model that you own through the **Active model** settings in the document library in which the model is applied.

1. In the SharePoint document library in which the model is applied, select the **View active models** icon, and then select **View active models**.

2. In **Active models**, select the form processing model to which you want to apply the sensitivity label.

3. On the **Model details** pane, in the **Sensitivity label** section, select the sensitivity label you want to apply. Then select **Save**.

   > [!NOTE]
   > You must be the model owner for the **Model settings** pane to be editable. 
--->

## <a name="see-also"></a><span data-ttu-id="648ce-134">참고 항목</span><span class="sxs-lookup"><span data-stu-id="648ce-134">See also</span></span>

[<span data-ttu-id="648ce-135">보존 레이블 적용</span><span class="sxs-lookup"><span data-stu-id="648ce-135">Apply a retention label</span></span>](apply-a-retention-label-to-a-model.md)

[<span data-ttu-id="648ce-136">분류자 만들기</span><span class="sxs-lookup"><span data-stu-id="648ce-136">Create a classifier</span></span>](create-a-classifier.md)

[<span data-ttu-id="648ce-137">추출기 만들기</span><span class="sxs-lookup"><span data-stu-id="648ce-137">Create an extractor</span></span>](create-an-extractor.md)

[<span data-ttu-id="648ce-138">문서 이해 개요</span><span class="sxs-lookup"><span data-stu-id="648ce-138">Document Understanding overview</span></span>](document-understanding-overview.md)