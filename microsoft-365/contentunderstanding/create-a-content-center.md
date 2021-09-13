---
title: Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기
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
description: Microsoft SharePoint Syntex에서 콘텐츠 센터를 만드는 방법을 알아봅니다.
ms.openlocfilehash: a50a31d29cc53a70a7e13f9cd83e76933aa39cf8
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59188027"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기


</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

문서 이해 모델을 만들고 관리하려면 먼저 콘텐츠 센터가 있어야 합니다. 콘텐츠 센터는 모델 만들기 인터페이스이자 게시된 모델에 적용된 문서 라이브러리에 대한 정보를 포함하고 있습니다.

   ![문서 라이브러리를 선택합니다.](../media/content-understanding/content-center-page.png)

[설정](set-up-content-understanding.md) 중에 기본 콘텐츠 센터가 만들어집니다. SharePoint 관리자는 필요한 경우 추가 센터를 만들도록 선택할 수도 있습니다. 모든 모델 활동을 롤업하는 환경이라면 단일 콘텐츠 센터로도 괜찮지만 모델에 따라 요구사항과 사용 권한이 다를 경우 조직 내에 여러 부서를 위한 추가 센터가 필요할 수도 있습니다.

또한 SharePoint Syntex를 사용하려는 경우 라이선스를 구입하지 않고 이 문서의 지침을 사용하여 콘텐츠 센터를 만들 수 있습니다. 라이선스가 없는 사용자는 문서 이해 모델을 작성할 수 있지만 문서 라이브러리에 적용할 수는 없습니다.

> [!NOTE]
> [Microsoft 365 Multi-Geo 환경](../enterprise/microsoft-365-multi-geo.md)에서는 중앙 위치에 단일 기본 콘텐츠 센터가 있는 경우 해당 위치 내에서만 모델 작업의 롤업을 제공할 수 있습니다. 현재 다중 지역 환경에서 팜 경계에 걸쳐 모델 활동을 롤업할 수 없습니다. 

## <a name="create-a-content-center"></a>콘텐츠 센터 만들기

SharePoint 관리자는 관리 센터 사이트 프로비전 창에서 [다른 SharePoint 사이트를 만드는 것](/sharepoint/create-site-collection)과 같이 콘텐츠 센터 사이트를 만들 수 있습니다.

새 콘텐츠 센터를 만들려면 다음과 같이 합니다.

1. Microsoft 365 관리 센터에서 [SharePoint 관리 센터 **활성 사이트** 페이지](https://admin.microsoft.com/sharepoint?page=siteManagement&modern=true)로 이동합니다.

2. **활성 사이트** 페이지에서 **만들기** 를 클릭하고 **다른 옵션** 을 선택합니다.

3. **서식 파일 선택** 메뉴에서 **콘텐츠 센터** 를 선택합니다.

4. 새 사이트의 경우 **사이트 이름**, **주 관리자** 및 **언어** 를 입력합니다.</br>

   > [!NOTE] 
   > 사용 가능한 모든 언어로 콘텐츠 센터 사이트를 렌더링하도록 선택할 수 있지만 현재 모델은 영문 파일에 대해서만 만들 수 있습니다. 또한 사이트 형식처럼 사이트가 만들어진 이후에 기본 언어 편집은 불가능합니다.

5. **마침** 을 선택합니다.
 
콘텐츠 센터 사이트를 만든 후에는 SharePoint 관리 센터의 **활성 사이트** 페이지에 표시되는 것을 볼 수 있습니다. 

### <a name="give-access-to-additional-users"></a>추가 사용자에게 액세스 부여
 
사이트를 만든 후에는 다른 사용자에게 표준 [SharePoint 사이트 사용 권한 모델](/sharepoint/modern-experience-sharing-permissions)을 통해 사이트에 액세스를 부여할 수 있습니다.

### <a name="roll-up-of-models-in-the-default-content-center"></a>기본 콘텐츠 센터에서 모델 롤업

SharePoint Syntex에서 설정 중에 처음 생성된 콘텐츠 센터는 *기본 콘텐츠 센터* 입니다. 후속 콘텐츠 센터가 만들어지면 해당 모델이 기본 콘텐츠 센터 보기에 표시됩니다.

![기본 콘텐츠 센터의 모델 라이브러리 스크린샷.](../media/content-understanding/model-library-default-content-center.png)

기본 내용 센터 보기의 **모델** 라이브러리는 작성된 모델을 내용 센터별로 그룹화하여 작성된 모든 문서 이해 모델 및 양식 처리 모델의 요약 보기를 수행합니다.

> [!NOTE]
> 지정된 기본 콘텐츠 센터는 변경할 수 없습니다. 설치하는 동안 항상 만들어진 첫 번째 콘텐츠 센터입니다. 

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)

[추출기 만들기](create-an-extractor.md)

[콘텐츠 센터 만들기](create-a-content-center.md)

[문서 이해 개요](document-understanding-overview.md)

[양식 처리 모델 만들기](create-a-form-processing-model.md)

[모델 적용](apply-a-model.md)