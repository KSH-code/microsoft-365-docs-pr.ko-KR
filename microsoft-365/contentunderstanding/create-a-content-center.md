---
title: Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기
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
description: 콘텐츠 센터를 만드는 방법을 알아봅니다.
ms.openlocfilehash: 62977bc5a34b041e9e958ff46e0dbc010d6bd822
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48295435"
---
# <a name="create-a-content-center-in-microsoft-sharepoint-syntex"></a>Microsoft SharePoint Syntex에서 콘텐츠 센터 만들기

이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.</br>

</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4CPSF]

</br>

문서 모델을 이해 하 고 관리 하려면 먼저 콘텐츠 센터가 있어야 합니다. 콘텐츠 센터는 모델 만들기 인터페이스 이며, 적용 된 문서 라이브러리에 대 한 정보도 포함 되어 있습니다.</br>

   ![문서 라이브러리 선택](../media/content-understanding/content-center-page.png)</br>

[설치](set-up-content-understanding.md)하는 동안 초기 콘텐츠 센터를 만듭니다. 그러나 SharePoint 관리자는 필요에 따라 추가 센터를 만들도록 선택할 수도 있습니다. 모든 모델 활동의 롤업을 사용할 환경에서 단일 콘텐츠 센터가 발생할 수 있는 경우 조직 내에 여러 부서에 대 한 추가 센터가 있을 수 있으며, 이러한 모델에 대 한 요구 사항과 요구 사항이 서로 다를 수 있습니다.

> [!NOTE]
> SharePoint 관리자는 사이트 서식 파일을 사용 하 여 [다른 sharepoint 사이트를 만드는](https://docs.microsoft.com/sharepoint/create-site-collection) 것 처럼 콘텐츠 센터 사이트를 만들 수 있습니다.

새 콘텐츠 센터를 만들려면 다음을 수행 합니다.

1. Microsoft 365 관리 센터에서 SharePoint 관리 센터로 이동 합니다.
2. SharePoint 관리 센터의 **사이트**아래에서 **활성 사이트**를 선택 합니다.
3. **활성 사이트** 페이지에서 **만들기**를 클릭 한 다음 **기타 옵션**을 선택 합니다.
4. **서식 파일 선택** 메뉴에서 **콘텐츠 센터**를 선택 합니다.
5. 새 사이트의 경우 **사이트 이름**, **기본 관리자**및 **언어**를 제공 합니다.</br>

> [!NOTE] 
> 필요한 경우 콘텐츠 센터 사이트를 선택 하 여 사용 가능한 언어로 렌더링할 수 있습니다. 영어 파일에 대해서만 현재 모델을 만들 수 있습니다.</br>

6. **마침을**선택 합니다.

### <a name="give-access-to-additional-users"></a>추가 사용자에 게 액세스 권한 부여
 
사이트를 만든 후에는 다른 사용자에 게 표준 [SharePoint 사이트 사용 권한 모델](https://docs.microsoft.com/sharepoint/modern-experience-sharing-permissions)을 통해 사이트에 대 한 액세스 권한을 부여할 수 있습니다.

## <a name="see-also"></a>참고 항목
[분류자 만들기](create-a-classifier.md)</br>
[추출기 만들기](create-an-extractor.md)</br>
[콘텐츠 센터 만들기](create-a-content-center.md) 
 [문서 이해 개요](document-understanding-overview.md)</br>
[양식 처리 모델 만들기](create-a-form-processing-model.md)</br>
[모델 적용](apply-a-model.md)    
