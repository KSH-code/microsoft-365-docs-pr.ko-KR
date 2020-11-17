---
title: SharePoint Syntex 설정
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
search.appverid: MET150
localization_priority: Priority
description: Project Cortex에서 콘텐츠 이해 설정
ms.openlocfilehash: dfbcc8e41a28e3107b58ac6b8d471e3a2a08d036
ms.sourcegitcommit: e7bf23df4852b78912229d1d38ec475223597f34
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/17/2020
ms.locfileid: "49087574"
---
# <a name="set-up-sharepoint-syntex"></a>SharePoint Syntex 설정

관리자는 Microsoft 365 관리 센터를 사용하여 [Microsoft SharePoint Syntex](index.md)를 설정할 수 있습니다. 

시작하기 전에 다음을 고려해야 합니다.

- Which SharePoint sites will you enable form processing? All of them, some, or select sites?
- 기본 컨텐츠 센터의 이름을 무엇으로 지정하시겠어요?

Microsoft 365 관리 센터에서 초기 설정 후 설정을 변경할 수 있습니다.

Prior to setup, make sure to plan for the best way to set up and configure content understanding in your environment. For example, you need to make considerations about the following names of:

- 양식 처리를 실행하려는 SharePoint 사이트(모든 사이트, 일부 사이트 또는 선택한 사이트)입니다.
- 컨텐츠 센터 및 주 사이트 관리자의 이름입니다.

## <a name="requirements"></a>요구 사항 

> [!NOTE]
> Microsoft 365 관리 센터에 액세스하고 콘텐츠 이해를 설정하려면 글로벌 관리자 또는 SharePoint 관리자 권한이 있어야 합니다.

관리자는 Microsoft 365 관리 센터의 콘텐츠 이해 관리 설정 전반에 걸쳐 설정 후 언제든지 선택한 설정을 변경할 수도 있습니다.

## <a name="to-set-up-sharepoint-syntex"></a>SharePoint Syntex를 설정하려면 다음을 수행합니다.

1. Microsoft365 관리 센터에서 **설정** 을 선택하고 **파일 및 콘텐츠** 섹션을 선택합니다.

2. **파일 및 콘텐츠** 섹션에서 **콘텐츠 이해 자동화** 를 선택합니다.<br/>

3. **콘텐츠 이해 자동화** 페이지에서 **시작하기** 를 클릭하여 설정 프로세스를 살펴봅니다.<br/>

    > [!div class="mx-imgBorder"]
    > ![설치 시작](../media/content-understanding/admin-content-understanding-get-started.png)</br>

4. On the **Configure Form Processing** page, you can choose if you want to let users be able to create form processing models in specific SharePoint document libraries. A menu option will be available in the document library ribbon to **Create a form processing model** in SharePoint document libraries in which it is enabled.
 
     **양식 처리 모델** 을(를) 생성하기 위해 어떤 SharePoint 라이브러리에 표시할 것인지에 대해 다음을 선택할 수 있습니다.</br>
      - **모든 SharePoint 라이브러리** 를 조직의 모든 SharePoint 라이브러리에서 사용할 수 있도록 합니다.</br>
      - **선택한 사이트의 라이브러리만**. 그런 다음 사용할 수 있도록 만들 사이트를 선택하거나 최대 50개 사이트의 목록을 업로드합니다.</br>
      - **사이트에서 SharePoint 라이브러리를 사용하지 않으려면** SharePoint 라이브러리가 없습니다(설치 후 이 라이브러리를 변경할 수 있습니다).

   > [!div class="mx-imgBorder"]
   > ![양식 처리 구성](../media/content-understanding/admin-configforms.png)

   > [!Note]
   > 사이트가 포함된 후 사이트를 제거해도 해당 사이트의 라이브러리에 적용된 기존 모델이나 문서 이해 모델을 라이브러리에 적용하는 기능에는 영향을 미치지 않습니다. 
    
5. **콘텐츠 센터 생성** 페이지에서 사용자가 문서 이해 모델을 생성하고 관리할 수 있는 SharePoint 콘텐츠 센터 사이트를 생성할 수 있습니다.

    1. **사이트 이름** 에 대해 콘텐츠 센터 사이트에 지정할 이름을 입력합니다.
    
    1. The **Site address** will show the URL for your site, based on what you selected for the site name. If you want to change it, click **Edit**.

       > [!div class="mx-imgBorder"]
       > ![콘텐츠 센터 만들기](../media/content-understanding/admin-cu-create-cc.png)</br>

       **다음** 을 선택합니다.

6. On the **Review and finish** page, you can look at your selected setting and choose to make changes. If you are satisfied with your selections, select **Activate**.

7. 확인 페이지에서 **완료** 를 클릭합니다.

8. You'll be returned to your **Automate content understanding** page. From this page, you can select **Manage** to make any changes to your configuration settings. 

## <a name="assign-licenses"></a>라이선스 할당

SharePoint Syntex를 구성한 후에는 SharePoint Syntex 기능을 사용할 사용자에게 라이선스를 할당해야 합니다.

라이선스를 할당하려면 다음을 수행합니다.

1. Microsoft 365 관리 센터의 **사용자** 아래에서 **활성 사용자** 를 클릭합니다.

2. 라이선스를 부여할 사용자를 선택하고 **제품 라이선스 관리** 를 클릭합니다.

3. **추가 할당** 을 선택합니다.

4. Select **SharePoint Syntex**. Under **Apps**, make sure **Common Data Service for SharePoint Syntex**, **SharePoint Syntex**, and **SharePoint Syntex - SPO type** are all selected.

    > [!div class="mx-imgBorder"]
    > ![Microsoft 365 관리 센터의 SharePoint Syntex 라이선스](../media/content-understanding/sharepoint-syntex-licenses.png)

5. **변경 내용 저장** 을 클릭합니다.

## <a name="ai-builder-credits"></a>AI Builder 크레딧

If you have 300 or more SharePoint Syntex licenses for SharePoint Syntex in your organization, you will be allocated one million AI Builder credits. If you have fewer than 300 licenses, you must purchase AI Builder credits in order to use forms processing.

[AI Builder 계산기](https://powerapps.microsoft.com/ai-builder-calculator)을(를) 사용하여 사용자에게 적합한 AI Builder 용량을 추정할 수 있습니다.

[파워 플랫폼 관리 센터](https://admin.powerplatform.microsoft.com/resources/capacity)로 이동하여 크레딧 및 사용량을 확인합니다.

## <a name="see-also"></a>참고 항목

[양식 처리 모델](https://docs.microsoft.com/ai-builder/form-processing-model-overview)을(를) 검토합니다.

[단계별 절차는 다음과 같습니다. 문서 이해 모델(비디오)](https://www.youtube.com/watch?v=DymSHObD-bg)을(를) 작성하는 방법

