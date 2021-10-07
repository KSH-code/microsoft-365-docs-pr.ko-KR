---
title: 온라인 클래식 게시 SharePoint 이미지 최적화
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/18/2019
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c7edb02a-fdab-4f91-9a20-cba01dad28ef
description: 버전 및 스프라이트를 사용하여 온라인 클래식 게시 사이트에서 이미지 성능을 SharePoint 방법을 학습합니다.
ms.openlocfilehash: fe3c698dda06559bf6e104650b6b8bb8d81172fa
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209732"
---
# <a name="image-optimization-for-sharepoint-online-classic-publishing-sites"></a>온라인 클래식 게시 SharePoint 이미지 최적화

웹 페이지의 로드 속도는 이미지, HTML, JavaScript 및 CSS를 포함하여 페이지를 렌더링하는 데 필요한 모든 구성 요소의 조합된 크기에 따라 달라 니다. 이미지는 사이트를 더욱 매력적으로 만들 수 있는 좋은 방법이지만 크기는 성능에 영향을 줄 수 있습니다. 압축 및 크기 조정을 사용하여 이미지를 최적화하고 스프라이트를 사용하여 매우 큰 이미지의 효과를 오프셋할 수 있습니다. 이미지 SharePoint 사용하여 단일 큰 이미지를 업로드하고 이미지의 섹션을 표시하여 다시 로드하지 않고 다시 사용할 수 있습니다.

>[!NOTE]
>이 항목은 최신 포털 SharePoint 온라인 클래식 게시 사이트에 적용됩니다. SharePoint 온라인 최신 포털 사이트의 이미지 최적화에 대한 자세한 내용은 온라인 최신 포털 SharePoint [이미지 최적화를 참조하세요.](modern-image-optimization.md)
  
## <a name="using-sprites-to-speed-up-image-loading"></a>스프라이트를 사용하여 이미지 로드 속도 향상

![spcommon의 스크린샷.](../media/cc5cdee1-8e54-4537-9a8a-8854f4ee849f.png)

이미지 스프라이트에는 여러 개의 작은 이미지가 포함되어 있습니다. CSS를 사용하면 절대 위치가 있는 페이지의 특정 부분에 표시할 복합 이미지 부분을 선택합니다. 기본적으로 여러 이미지를 로드하는 대신 페이지 주위에 단일 이미지를 이동하고 스프라이트 이미지의 필수 부분이 최종 사용자에게 표시되는 작은 창을 통해 해당 이미지의 작은 부분을 볼 수 있도록 만듭니다. SharePoint 온라인에서는 스프라이트를 사용하여 스프라이트 파일에서 스프라이트 spcommon.png 표시합니다.

여기서 다루는 사항:
- 이미지 압축
- 이미지 최적화
- SharePoint 이미지 Nditions
   
이 경우 여러 이미지가 아닌 하나의 이미지만 다운로드한 다음 해당 이미지를 캐시하고 다시 사용할 수 있기 때문에 성능이 향상될 수 있습니다. 이미지가 캐시된 상태로 유지되지 않는 경우에도 여러 이미지 대신 단일 이미지를 사용하여 이 메서드를 사용하면 서버에 대한 총 HTTP 요청 수가 줄어들어 페이지 로드 시간이 줄어듭니다. 이는 실제로 이미지 번들링의 한 형태입니다. 이 방법은 위에 제공된 이미지 예제와 같이 이미지가 자주 변경되지 않는 경우(예: 아이콘) SharePoint 유용합니다. 타사 오픈 소스 커뮤니티 기반 [프로젝트인 Web Essentials를](https://vswebessentials.com/)사용하여 이러한 결과를 손쉽게 달성할 수 Microsoft Visual Studio. 자세한 내용은 온라인 에서 [최소화 및 번들 SharePoint 참조하세요.](./minification-and-bundling-in-sharepoint-online.md)
  
## <a name="using-image-compression-and-optimization-to-speed-up-page-loading"></a>이미지 압축 및 최적화를 사용하여 페이지 로드 속도 향상

이미지 압축 및 최적화는 사이트에서 사용하는 이미지의 파일 크기를 줄이는 것입니다. 이미지 크기를 줄이는 가장 좋은 방법은 사이트에서 볼 수 있는 최대 크기로 이미지 크기를 변경하는 것입니다. 이미지가 보기보다 더 큰 것은 의미가 없습니다. 이미지 편집기를 사용하여 이미지가 올바른 크기로 표시하는 것이 페이지 크기를 빠르고 쉽게 줄이는 방법입니다.
  
이미지 크기가 올바른 경우 다음 단계는 이러한 이미지의 압축을 최적화하는 것입니다. 사진 갤러리 및 타사 도구를 포함하여 압축 및 최적화에 사용할 수 있는 다양한 도구가 있습니다. 압축의 핵심은 최종 사용자의 품질을 잃지 않고 파일 크기를 최대한 줄이는 것입니다. 압축된 파일을 고화질 디스플레이에서 테스트하여 계속 보기 좋게 표시되도록 합니다.
  
## <a name="speed-up-page-downloads-by-using-sharepoint-image-renditions"></a>이미지 SharePoint 사용하여 페이지 다운로드 속도 향상

이미지 버전은 미리 정의된 이미지 SharePoint 기반의 여러 이미지 버전을 지원할 수 있는 SharePoint Online의 기능입니다. 이는 사용자 생성 이미지 콘텐츠가 있는 경우 또는 사이트의 CSS에서 너비 및 높이와 같은 이미지 크기를 고정하는 경우 특히 중요합니다. 이미지를 CSS로 고정한 경우에도 전체 해상도 이미지가 로드됩니다. 이 경우 이미지 전송을 사용하여 파일 크기를 줄일 수 있습니다.
  
> [!NOTE]
> 게시를 사용하도록 설정한 SharePoint 해당 응용 SharePoint 사용할 수 있습니다. 설정 Server Publishing에서 사이트 기능 설정 관리에서 게시를 \> \> 사용하도록 SharePoint \> 있습니다. 그렇지 않으면 옵션이 나타나지 않습니다.
  
이미지 크기 조정은 정의한 가장 작은 차원(너비 또는 높이)을 고려한 다음 잠긴 가로 세로 비율에 따라 다른 차원의 크기가 자동으로 조정될 수 있도록 이미지의 크기 조정을 통해 작동합니다. 기본적으로 이미지가 가운데에서 나머지 크기까지 자르게 됩니다. 예를 들어 너비가 100px와 50px로 정의하고 원래 이미지가 너비와 800px의 너비가 1000px인 경우 크기는 이제 800px가 50px로, 1000px 차원(현재 62.5px)이 이미지 중심에서 잘리게 됩니다.
  
단계는 비교적 간단하지만 이미지가 이전을 사용하려면 이미지를 추가하기 전에 SharePoint 사이트에 있는 것이 좋습니다. 또한 SharePoint Server 게시 인프라(사이트 모음 수준) 및 SharePoint 서버 게시(사이트 수준) 기능을 설정해야 합니다.
  
### <a name="add-an-image-rendition-to-speed-up-page-loading"></a>페이지 로드 속도를 향상하기 위해 이미지 Ndition 추가
  
1. 이 절차를 수행하는 사용자 계정에 최소한 사이트 모음의 최상위 사이트에 대한 디자인 권한이 있으며 해당 사이트가 웹 페이지로 게시되고 있는지 확인해야 합니다.

2. 웹 브라우저에서 게시 사이트 모음의 최상위 사이트로 이동하십시오.

3. 선택 **설정** 아이콘을 선택 합니다.

4. 사이트 **설정** 페이지의 모양 및  느낌 섹션에 기본 제공 이미지가 표시됩니다.

    기본으로 변경하거나 이미지 변경을 선택해  새 이미지를 만들 수 있습니다.

    ![Image Rendition의 스크린샷.](../media/eaae0d53-657d-47ef-b687-65c5167eae4d.PNG)
  
5. 이미지 **재배포 페이지에서** 새 항목 **추가 를 선택합니다.**

    ![새 항목 추가 스크린샷.](../media/8cede22e-52bf-4d9d-99cb-162f2f6ce92b.PNG)
  
6. 새 **이미지 재배포** 페이지의 이름  상자에 해당 변경의 이름을 입력합니다.

7. 너비 **및** 높이 텍스트 **상자에** 변경의 너비와 높이를 픽셀 단위로 입력한 다음 저장을 **선택 합니다.**

    ![Image Rendition Name의 스크린샷.](../media/5a6119ed-c163-40df-a4db-ec629d15607d.PNG)
  
## <a name="custom-cropping-with-image-renditions"></a>이미지 재배포를 사용하여 사용자 지정 자르기

기본적으로 이미지는 이미지 중앙에서 생성됩니다. 사용하려는 이미지 부분을 자르면 개별 이미지에 대한 이미지 Ndition을 조정할 수 있습니다. 이미지를 개별로 자르고, 그에 따라 자르면 됩니다. 이미지를 자르면 SharePoint 캐시를 사용하여 각 버전에 대한 이미지 버전을 만들어 페이지 로드 속도를 향상합니다. 이렇게 하면 이미지의 배분 방식이 한 번만 줄어들고 최종 사용자에게 여러 번 서비스를 제공해야 하기 때문에 서버 부하가 줄어듭니다. 이미지 재배포를 자르는 방법에 대한 자세한 내용은 이미지 자르기 [를 참조하세요.](/sharepoint/dev/general-development/sharepoint-design-manager-device-channels)
