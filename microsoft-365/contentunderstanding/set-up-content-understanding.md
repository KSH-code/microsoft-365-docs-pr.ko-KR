---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
ms.reviewer: ssquires
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: admindeeplinkMAC
search.appverid: MET150
localization_priority: Priority
description: SharePoint Syntex 설정
ms.openlocfilehash: 2f77176e2bfd90b4f912379b3b2dcf15b62c7cf4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187988"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex 설정

관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>를 사용하여 [Microsoft SharePoint Syntex](index.md)를 설정할 수 있습니다. 

시작하기 전에 다음을 고려해야 합니다.

- 양식 처리를 사용하도록 설정할 SharePoint 사이트는 무엇인가요? 전부요, 일부인가요, 아니면 특정 사이트인가요?
- 기본 콘텐츠 센터의 이름을 무엇으로 지정하시겠어요?

<a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 초기 설정 후 설정을 변경할 수 있습니다.

설정하기 전에 사용자 환경에서 컨텐츠 이해도를 설정하고 구성하는 최선의 방법을 계획해야 합니다. 예를 들어 다음과 같은 결정을 내려야 합니다.

- 양식 처리를 사용하도록 설정할 SharePoint 사이트(모든 사이트, 일부 사이트 또는 선택한 사이트)입니다.
- 이름 및 관리자 또는 콘텐츠 센터

## <a name="requirements"></a>요구 사항 

> [!NOTE]
> Microsoft 365 관리 센터에 액세스하고 SharePoint Syntex를 설정하려면 글로벌 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.

관리자는 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>의 콘텐츠 이해 관리 설정 전반에 걸쳐 설정 후 언제든지 선택한 설정을 변경할 수도 있습니다.

사용자 지정 Power Platform 환경을 사용하고자 계획한다면 이 환경에서 *Project Cortex용 AI Builder* 앱을 [설치하고](/power-platform/admin/manage-apps#install-an-app-in-the-environment-view) [AI Builder 크레딧](/power-platform/admin/capacity-add-on)을 할당해야 양식 처리 모델을 만들 수 있습니다.

### <a name="licensing"></a>라이선싱

SharePoint Syntex를 사용하려면 조직에 SharePoint Syntex 구독이 있어야 합니다. 각 사용자에게 다음 라이선스가 할당되어 있어야 합니다.

- SharePoint Syntex
- SharePoint Syntex - SPO 유형
- SharePoint Syntex용 일반 데이터 서비스

양식 처리를 사용하려면 AI Builder 크레딧도 필요합니다. 라이선스 사용자가 300명 이상인 경우 매월 AI Builder 크레딧이 할당됩니다.

SharePoint Syntex 라이선스에 대한 자세한 내용은 [SharePoint Syntex 라이선싱](syntex-licensing.md)을 참조하세요.

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex를 설정하려면 다음을 수행합니다.

1. Microsoft365 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2171997" target="_blank">**설정**</a>을 선택하고 **파일 및 콘텐츠** 섹션을 선택합니다.

2. **파일 및 콘텐츠** 섹션에서 **콘텐츠 이해 자동화** 를 선택합니다. 현재 AI Builder 크레딧의 상태는 **한눈에 보기** 섹션에 표시됩니다.<br/>

3. **콘텐츠 이해 자동화** 페이지에서 **시작하기** 를 클릭하여 설정 프로세스를 살펴봅니다. <br/>

    > [!div class="mx-imgBorder"]
    > ![설치 시작.](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. **양식 처리 구성** 페이지에서 사용자가 특정 SharePoint 문서 라이브러리에 양식 처리 모델을 생성할 수 있도록 허용할지 여부를 선택할 수 있습니다. 사용 설정된 해당 Sharepoint 문서 라이브러리 리본에서 **양식 처리 모델을 만들기** 위한 문서 라이브러리 리본의 메뉴 옵션을 사용할 수 있습니다.
 
     **양식 처리 모델** 을(를) 생성하기 위해 어떤 SharePoint 라이브러리에 표시할 것인지에 대해 다음을 선택할 수 있습니다.</br>
      - **모든 SharePoint 라이브러리** 를 조직의 모든 SharePoint 라이브러리에서 사용할 수 있도록 합니다.</br>
      - **선택한 SharePoint 사이트의 라이브러리** 를 선택한 다음, 사용 가능한 사이트를 선택하거나 최대 50개 사이트의 목록을 업로드합니다.</br>
      - **사이트에서 SharePoint 라이브러리를 사용하지 않으려면** SharePoint 라이브러리가 없습니다(설치 후 이 라이브러리를 변경할 수 있습니다).

   > [!div class="mx-imgBorder"]
   > ![양식 처리 사이트 옵션 구성.](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 사이트가 포함된 후 사이트를 제거해도 해당 사이트의 라이브러리에 적용된 기존 모델이나 문서 이해 모델을 라이브러리에 적용하는 기능에는 영향을 미치지 않습니다. 
    
    여러 Power Platform 환경을 구성한 경우 양식 처리에 사용할 환경을 선택할 수 있습니다. (환경이 하나뿐인 경우 이 옵션이 나타나지 않습니다.)

    ![양식 처리 Power Platform 옵션 구성.](../media/content-understanding/setup-power-platform-env.png)

    **Power Platform 환경** 의 경우 다음을 선택할 수 있습니다.
    - **기본 환경 설정을 사용하여** 기본 Power Platform 환경을 사용합니다.
    - **사용자 지정 환경을 사용하여** 사용자 지정 환경을 사용합니다. 목록에서 사용할 환경을 선택합니다. ([사용자 지정 환경의 요구 사항을 참조하세요](/microsoft-365/contentunderstanding/set-up-content-understanding#requirements)).

    **다음** 을 클릭합니다.

5. **콘텐츠 센터 생성** 페이지에서 사용자가 문서 이해 모델을 생성하고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 생성할 수 있습니다. 이전에 SharePoint 관리 센터에서 콘텐츠 센터를 만든 경우 해당 정보가 여기에 표시되며 **다음** 을 선택하면 됩니다.

    1. **사이트 이름** 에 대해 콘텐츠 센터 사이트에 지정할 이름을 입력합니다.
    
    1. **사이트 주소** 는 사이트 이름에 대해 선택한 항목에 따라 사이트의 URL을 표시합니다. 변경하려는 경우 **편집** 을 클릭합니다.

       > [!div class="mx-imgBorder"]
       > ![콘텐츠 센터 만들기.](../media/content-understanding/admin-cu-create-cc.png)</br>

       **다음** 을 선택합니다.

6. **검토 및 마침** 페이지에서 선택한 설정을 보고 변경하도록 선택할 수 있습니다. 원하는 항목을 선택한 경우 **활성화** 를 선택합니다.

7. 확인 페이지에서 **완료** 를 클릭합니다.

8. **콘텐츠 이해 자동화** 페이지로 돌아갑니다. 이 페이지에서 **관리** 를 선택하여 구성 설정을 변경할 수 있습니다. 

## <a name="assign-licenses"></a>라이선스 할당

SharePoint Syntex를 구성한 후에는 SharePoint Syntex 기능을 사용할 사용자에게 라이선스를 할당해야 합니다.

라이선스를 할당하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터의 **사용자** 아래에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">**활성 사용자**</a>를 선택합니다.

2. 라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리** 를 선택합니다.

3. 드롭다운 메뉴에서 **앱** 을 선택합니다.

4. **SharePoint Syntex용 앱 표시** 를 선택합니다. **앱** 에서 **SharePoint Syntex용 일반 데이터 서비스**, **SharePoint Syntex** 및 **SharePoint Syntex - SPO 유형** 이 모두 선택되어 있는지 확인합니다.

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스.](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **변경 사항 저장** 를 클릭합니다.

## <a name="see-also"></a>참고 항목

[양식 처리 모델](/ai-builder/form-processing-model-overview)을(를) 검토합니다.

[단계별 절차는 다음과 같습니다. 문서 이해 모델(비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)을(를) 작성하는 방법

[Power Platform 관리 센터에서 환경 만들기 및 관리](/power-platform/admin/create-environment)
