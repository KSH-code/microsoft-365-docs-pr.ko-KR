---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: f0a26f0044e578928730cf4930f1524e86dff9f3
ms.sourcegitcommit: 15be7822220041c25fc52565f1c64d252e442d89
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/28/2020
ms.locfileid: "48294866"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex 설정

관리자는 Microsoft 365 관리 센터를 사용 하 여 설치 및 Microsoft SharePoint Syntex을 설정할 수 있습니다. 

시작 하기 전에 다음 사항을 고려 하십시오.

- 양식 처리를 사용 하도록 설정할 SharePoint 사이트 사이트를 모두 또는 선택 하 시겠습니까?
- 콘텐츠 센터의 이름과 기본 사이트 관리자를 선택 합니다.

Microsoft 365 관리 센터의 초기 설치 후에 설정을 변경할 수 있습니다.

이 문서에서 설명 하는 내용은 Project Cortex 비공개 미리 보기에 대 한 것입니다. [자세한 내용은 Project Cortex를 참조](https://aka.ms/projectcortex)하세요.

설치 전에 환경에서 콘텐츠 이해를 설정 하 고 구성 하는 최상의 방법을 계획 해야 합니다. 예를 들어 다음 이름에 대 한 고려 사항을 고려해 야 합니다.

- 모든 해당, 일부 또는 선택한 사이트의 양식 처리를 사용 하도록 설정 하려는 SharePoint 사이트
- 콘텐츠 센터 및 기본 사이트 관리자의 이름

## <a name="requirements"></a>요구 사항 

> [!NOTE]
> Microsoft 365 관리 센터에 액세스 하 고 콘텐츠 이해를 설정할 수 있으려면 전역 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.

관리자는 설치 후와 Microsoft 365 관리 센터의 콘텐츠를 이해 하는 콘텐츠에 따라 선택한 설정을 언제 든 지 변경할 수도 있습니다.

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex를 설정 하려면

1. Microsoft 365 관리 센터에서 **설치**를 선택 하 고 **조직의 기술 자료** 섹션을 확인 합니다.

2. **조직의 기술 자료** 섹션에서 **콘텐츠 이해 자동화**를 선택 합니다.<br/>

    ![조직 기술 자료 설정 페이지](../media/content-understanding/admin-org-knowledge-options.png)</br>

3. **SharePoint Syntex 자동화** 페이지에서 **시작** 을 클릭 하 여 설정 프로세스를 안내 합니다.<br/>

    ![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. 이미지 태그 설정 페이지에서 [이미지 태그](image-tagging.md)지정을 허용할 것인지 여부를 선택 합니다.

    ![이미지 태그 지정 옵션 스크린샷](../media/content-understanding/admin-content-understanding-setup-image-tagging.png)</br>

5. **양식 처리 구성** 페이지에서는 사용자가 AI Builder를 사용 하 여 특정 SharePoint 문서 라이브러리에서 양식 처리 모델을 만들 수 있도록 할 것인지 여부를 선택할 수 있습니다. 문서 라이브러리 리본 메뉴에서 사용 가능 하도록 설정 된 SharePoint 문서 라이브러리에 **양식 처리 모델을 만들려면** 이 옵션을 사용할 수 있습니다.
 
     **SharePoint 라이브러리에서 양식 처리 모델을 만드는 옵션을 표시 해야 하는**경우 다음을 선택할 수 있습니다.</br>
      - **모든 sharepoint 라이브러리** 를 조직의 모든 sharepoint 라이브러리에서 사용할 수 있도록 하는 데 사용 됩니다.</br>
      - **선택한 사이트의 라이브러리 에서만**사용 가능 하도록 설정할 사이트를 선택 합니다.</br>

   ![양식 처리 구성](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > SharePoint 문서 라이브러리에서이 설정을 사용 하도록 설정 해도 라이브러리에 적용 된 기존 모델이 나 라이브러리에 문서 이해 모델을 적용 하는 기능에는 영향을 주지 않습니다. 
    
6. **콘텐츠 센터 만들기** 페이지에서는 사용자가 문서 이해 모델을 만들고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 만들 수 있습니다. </br>
    a. **사이트 이름**에 콘텐츠 센터 사이트에 지정할 이름을 입력 합니다.</br>
    b. 사이트 **주소** 에는 사이트 이름으로 선택한 사항을 기반으로 하 여 사이트의 URL이 표시 됩니다. 변경 하려면 **편집**을 클릭 합니다.</br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

    **다음**을 선택합니다.

7. **검토 및 마침** 페이지에서 선택한 설정을 확인 하 고 변경 작업을 선택할 수 있습니다. 선택에 만족 하면 **활성화**를 선택 합니다.

8. 확인 페이지에서 **완료**를 클릭 합니다.

9. **콘텐츠 자동화를 이해** 하는 페이지를 반환 합니다. 이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다. 

## <a name="assign-licenses"></a>라이선스 할당

SharePoint Syntex를 구성한 후에는 양식 처리 및 문서 이해 기능을 사용할 사용자에 대 한 라이선스를 할당 해야 합니다.

라이선스를 할당 하려면:

1. Microsoft 365 관리 센터의 **사용자**에서 **활성 사용자**를 클릭 합니다.

2. 라이선스를 부여할 사용자를 선택 하 고 **제품 라이선스 관리**를 클릭 합니다.

3. **추가 할당**을 선택 합니다.

4. **지능형 콘텐츠 서비스**를 선택 합니다. **앱**에서 지능형 콘텐츠 서비스와 **지능형 콘텐츠** 서비스 **에 대 한 공통 데이터 서비스가** 모두 선택 되어 있는지 확인 합니다.

    ![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **변경 내용 저장**을 클릭합니다.

## <a name="ai-builder-credits"></a>AI 건축 제작진

조직에 sharepoint Syntex에 대 한 SharePoint Syntex 라이선스가 300 개 이상 있는 경우 100만 AI Builder 크레딧이 할당 됩니다. 라이선스 수가 300 개 미만이 면 양식 처리를 사용 하기 위해 AI 빌더 제작진을 구입 해야 합니다.

[Ai builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)로 적합 한 ai 작성기 용량을 추정할 수 있습니다.

1. [Power Platform 관리 센터로](https://admin.powerplatform.microsoft.com/resources/capacity) 이동 하 여 크레딧 및 사용 현황을 확인 합니다.

    > [!NOTE]
    > SharePoint 문서 라이브러리에서이 설정을 사용 하도록 설정 해도 라이브러리에 적용 된 기존 모델이 나 라이브러리에 문서 이해 모델을 적용할 수 있는 기능에는 영향을 주지 않습니다. 
    
2. **콘텐츠 센터 만들기** 페이지에서는 사용자가 문서 이해 모델을 만들고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 만들 수 있습니다. </br>
    a. **사이트 이름**에 대해 콘텐츠 센터 사이트에 사용할 이름을 입력 합니다.</br>
    b. 사이트 **주소** 는 사이트 이름을 기반으로 사이트의 URL을 표시 합니다.</br>

    > [!NOTE] 
    > 지원 되는 언어를 선택할 수 있지만 콘텐츠 이해 모델은 영어에만 만들 수 있습니다.</br>

      ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

3. **다음**을 선택합니다.

4. **마침 및 검토** 페이지에서 선택한 설정을 확인 하 고 변경을 선택 합니다. 선택에 만족 하면 **활성화**를 선택 합니다.

5. 사용자가 양식 처리 기본 설정을 추가 하 고 콘텐츠 센터 사이트를 만들었기를 확인 하 여 **정품 인증 된 콘텐츠 이해** 됨 페이지를 표시 합니다. **완료**를 선택합니다.

6. **콘텐츠 자동화를 이해** 하는 페이지를 반환 합니다. 이 페이지에서 **관리** 를 선택 하 여 구성 설정을 변경할 수 있습니다. 

## <a name="see-also"></a>참고 항목

[양식 처리 모델 개요](https://docs.microsoft.com/ai-builder/form-processing-model-overview)

[단계별: 문서 이해 모델을 작성 하는 방법 (비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)

