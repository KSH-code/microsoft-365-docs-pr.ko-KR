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
ms.localizationpriority: medium
description: SharePoint Syntex에서 모델에 민감도 레이블을 적용하는 방법을 알아봅니다.
ms.openlocfilehash: 2b0ef2afda8f0a3d5431b8a14bc76dfcc3c3b663
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200200"
---
# <a name="apply-a-sensitivity-label-to-a-model-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex에서 모델에 민감도 레이블 적용

Microsoft SharePoint Syntex에서 문서 이해 모델에 [민감도 레이블](../compliance/sensitivity-labels.md)을 쉽게 적용할 수 있습니다. 이 기능은 양식 처리 모델에 아직 사용할 수 없습니다.

민감도 레이블을 사용하면 모델이 식별하는 문서에 암호화, 공유 및 조건부 액세스 정책을 적용할 수 있습니다. 예를 들어 모델에서 문서 라이브러리에 업로드된 은행 계좌 번호 또는 신용 카드 번호가 포함된 금융 문서를 식별할 뿐만 아니라 *암호화* 민감도 레이블을 적용하여 해당 콘텐츠에 액세스할 수 있는 사용자와 사용 방법을 제한하려고 합니다. SharePoint Syntex 모델은 [레이블 순서](../compliance/apply-sensitivity-label-automatically.md#how-multiple-conditions-are-evaluated-when-they-apply-to-more-than-one-label) 규칙을 적용하고 사용자가 파일에 수동으로 적용한 기존 레이블을 덮어쓰지 않습니다. 

모델의 홈페이지에서 모델 설정을 통해 기존 민감도 레이블을 모델에 적용할 수 있습니다. 레이블은 모델 설정에서 선택할 수 있도록 이미 게시되어 있어야 합니다.

> [!Important]
> 민감도 레이블을 문서 이해 모델에 적용하려면 [Microsoft 365 준수 센터에서 만들고 게시](../business-video/create-sensitivity-labels.md)해야 합니다.

## <a name="add-a-sensitivity-label-to-a-document-understanding-model"></a>문서 이해 모델에 민감도 레이블 추가

1. 모델 홈페이지에서 **모델 설정** 을 선택합니다.

   ![모델 설정 옵션이 강조 표시된 모델 페이지의 스크린샷입니다.](../media/content-understanding/sensitivity-model-settings.png)

2. **모델 설정** 창의 **준수** 섹션에서 **민감도 레이블** 메뉴를 선택하여 모델에 적용할 수 있는 민감도 레이블 목록을 확인합니다.

   ![민감도 레이블 메뉴를 보여 주는 모델 설정 창의 스크린샷입니다.](../media/content-understanding/sensitivity-model-settings-pane.png) 

3. 모델에 적용할 민감도 레이블을 선택한 다음 **저장** 을 선택합니다.

모델에 민감도 레이블을 적용한 후 다음 항목에 적용할 수 있습니다.

- 새 문서 라이브러리
- 모델이 이미 적용된 문서 라이브러리
 
### <a name="apply-the-sensitivity-label-to-a-document-library-to-which-the-model-is-already-applied"></a>모델이 이미 적용된 문서 라이브러리에 민감도 레이블 적용

문서 이해 모델이 문서 라이브러리에 이미 적용된 경우 다음을 수행하여 민감도 레이블 업데이트를 동기화하여 문서 라이브러리에 적용할 수 있습니다.

1. 모델 홈 페이지의 **이 모델이 있는 라이브러리** 섹션에서 민감도 레이블 업데이트를 적용할 문서 라이브러리를 선택합니다.

2. **동기화** 를 선택합니다.

   ![동기화가 강조 표시된 이 모델이 있는 라이브러리 섹션을 보여 주는 스크린샷입니다.](../media/content-understanding/sensitivity-libraries-sync.png)

업데이트를 적용하고 모델에 동기화한 후 다음 단계를 수행하여 적용되었는지 확인할 수 있습니다.

1. 콘텐츠 센터의 **이 모델이 있는 라이브러리** 섹션에서 업데이트된 모델이 적용된 라이브러리를 선택합니다. 

2. 문서 라이브러리 보기에서 정보 아이콘을 선택하여 모델 속성을 확인합니다.

3. **활성 모델** 목록에서 업데이트된 모델을 선택합니다.

4. **민감도 레이블** 섹션에 적용된 민감도 레이블의 이름이 표시됩니다.

문서 라이브러리의 모델 보기 페이지에 새 **민감도 레이블** 열이 표시됩니다. 모델이 콘텐츠 형식에 속하는 것으로 식별하는 파일을 분류하고 라이브러리 보기에 나열할 때 **민감도 레이블** 열에는 모델을 통해 적용된 민감도 레이블의 이름도 표시됩니다.

예를 들어 모델이 식별하는 모든 금융 문서에는 또한 *암호화* 민감도 레이블이 적용되어 권한이 없는 사용자가 액세스할 수 없게 됩니다. 권한이 없는 사용자가 문서 라이브러리에서 파일에 액세스하려고 하면 적용된 민감도 레이블로 인해 허용되지 않는다는 오류가 표시됩니다.

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

## <a name="see-also"></a>참고 항목

[보존 레이블 적용](apply-a-retention-label-to-a-model.md)

[분류자 만들기](create-a-classifier.md)

[추출기 만들기](create-an-extractor.md)

[문서 이해 개요](document-understanding-overview.md)
