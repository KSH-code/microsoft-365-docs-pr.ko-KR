---
title: '콘텐츠 이해 설정 (미리 보기) '
description: Project Cortex를 설정 하는 방법
author: efrene
ms.author: efrene
manager: pamgreen
ms.date: 08/1/2020
audience: admin
ms.topic: article
ms.service: ''
search.appverid: ''
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: fca80e45dfa45ee5da9521854c6eebfbd87d8859
ms.sourcegitcommit: 91c82a79962387205c4dd4dd8d61322b79fed55f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/01/2020
ms.locfileid: "46539911"
---
# <a name="set-up-content-understanding-preview"></a>콘텐츠 이해 설정 (미리 보기)

> [!Note] 
> 이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기를 위한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

관리자는 Microsoft 365 관리 센터를 사용 하 여 콘텐츠 이해를 설정 및 구성할 수 있습니다. 

설치 전에 환경에서 콘텐츠 이해를 설정 하 고 구성 하는 최상의 방법을 계획 해야 합니다. 예를 들어 다음과 같은 사항을 고려해 야 합니다.
- 양식 처리를 사용 하도록 설정할 SharePoint 사이트 사이트를 모두 또는 선택 하 시겠습니까?
- 콘텐츠 센터의 이름 및 기본 사이트 관리자 인 사용자

관리자는 설치 후에 Microsoft 365 관리 센터에서 콘텐츠를 이해 하는 방법을 통해 선택한 설정을 언제 든 지 변경할 수도 있습니다.


## <a name="requirements"></a>요구 사항 
Microsoft 365 관리 센터에 액세스 하 고 콘텐츠 이해를 설정할 수 있으려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.


## <a name="to-set-up-content-understanding"></a>콘텐츠 이해를 설정 하려면

1. Microsoft 365 관리 센터에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.
2. **조직의 기술 자료** 섹션에서 **콘텐츠 이해 자동화**를 선택 합니다.<br/>

    ![조직 기술 자료 설정 페이지](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. **콘텐츠 이해 자동화** 페이지에서 **시작** 을 클릭 하 여 설치 프로세스를 안내 합니다.<br/>

    ![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</br>


4. **양식 처리 구성** 페이지에서는 사용자가 AI Builder를 사용 하 여 특정 SharePoint 문서 라이브러리에서 양식 처리 모델을 만들 수 있도록 할 것인지 여부를 선택할 수 있습니다. 문서 라이브러리 리본 메뉴에서 사용 가능 하도록 설정 된 SharePoint 문서 라이브러리에 **양식 처리 모델을 만들려면** 이 옵션을 사용할 수 있습니다.
 
     **SharePoint 라이브러리에서 양식 처리 모델을 만드는 옵션을 표시 해야 하는**경우 다음을 선택할 수 있습니다.</br>
    - **모든 sharepoint 라이브러리** 를 사용 하 여 테 넌 트의 모든 sharepoint 라이브러리에서이를 사용할 수 있도록 합니다.</br>
    - **선택한 사이트의 라이브러리 에서만**사용 가능 하도록 설정할 사이트를 선택 합니다.</br>
    - **SharePoint 라이브러리가 없기** 때문에 사이트에서 현재 사용할 수 없습니다 (설치 후에 변경할 수 있음).
</br>

   ![양식 처리 구성](../media/content-understanding/admin-configforms.png)
</br>

   > [!Note]
   > SharePoint 문서 라이브러리에서이 설정을 사용 하도록 설정 해도 라이브러리에 적용 된 기존 모델이 나 라이브러리에 문서 이해 모델을 적용 하는 기능에는 영향을 주지 않습니다. 

    
5. **콘텐츠 센터 만들기** 페이지에서는 사용자가 문서 이해 모델을 만들고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 만들 수 있습니다. </br>
    a. **사이트 이름**에 콘텐츠 센터 사이트에 지정할 이름을 입력 합니다.</br>
    b. 사이트 **주소** 에는 사이트 이름으로 선택한 사항을 기반으로 하 여 사이트의 URL이 표시 됩니다.</br>

    > [!Note] 
    > 지원 되는 언어를 선택할 수 있지만 콘텐츠 이해 모델은 영어에만 만들 수 있습니다.</br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>


    **다음**을 선택합니다.
6. **마침 및 검토** 페이지에서 선택한 설정을 확인 하 고 변경 작업을 선택할 수 있습니다. 선택에 만족 하면 **활성화**를 선택 합니다.



7. 시스템에서 양식 처리 기본 설정을 추가 하 고 콘텐츠 센터 사이트를 만들기를 확인 하 여 **정품 인증 된 콘텐츠를 이해** 하는 페이지를 표시 합니다. **완료**를 선택합니다.

8. **콘텐츠 자동화를 이해** 하는 페이지를 반환 합니다. 이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다. 

## <a name="see-also"></a>참고 항목



  






