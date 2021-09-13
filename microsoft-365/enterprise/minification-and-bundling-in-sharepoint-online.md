---
title: SharePoint Online의 축소 및 묶음
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 3/1/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- SPO160
- MET150
ms.assetid: 87a52468-994e-43a2-b155-7229ed659291
description: Web Essentials와 함께 축소 및 번들링 기술을 사용하여 HTTP 요청과 온라인에서 페이지를 로드하는 데 걸리는 시간을 SharePoint 방법을 알아보습니다.
ms.openlocfilehash: 5ba1e174cbb016bdf88a1d4006a0b8aafd5ec042
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59220804"
---
# <a name="minification-and-bundling-in-sharepoint-online"></a>SharePoint Online의 축소 및 묶음

이 문서에서는 Web Essentials와 함께 축소 및 번들링 기술을 사용하여 HTTP 요청 수를 줄이고 SharePoint Online에서 페이지를 로드하는 데 걸리는 시간을 줄이는 방법을 SharePoint 있습니다.
  
웹 사이트를 사용자 지정할 때 사용자 지정을 지원하기 위해 서버에 많은 수의 추가 파일을 추가할 수 있습니다. JavaScript, CSS 및 이미지를 더 추가하면 서버에 대한 HTTP 요청 수가 증가하여 웹 페이지를 표시하는 데 걸리는 시간이 늘어납니다. 동일한 형식의 파일이 여러 개 있는 경우 이러한 파일을 번들로 묶어 파일을 더 빠르게 다운로드할 수 있습니다.
  
JavaScript 및 CSS 파일의 경우 축소라는 접근 방식을 사용하여 공백 및 필요하지 않은 기타 문자를 제거하여 파일의 전체 크기를 줄일 수도 있습니다.
  
## <a name="minification-and-bundling-javascript-and-css-files-with-web-essentials"></a>Web Essentials를 사용하여 JavaScript 및 CSS 파일 다국어화 및 번들화

Web Essentials와 같은 타사 소프트웨어를 사용하여 CSS 및 JavaScript 파일을 번들로 묶을 수 있습니다.
  
> [!IMPORTANT]
> Web Essentials는 타사 오픈 소스 커뮤니티 기반 프로젝트입니다. 소프트웨어는 2012 및 Visual Studio 확장 Visual Studio 2013 Microsoft에서 지원되지 않습니다. Web Essentials를 다운로드하려면 의 웹 사이트를 [https://vswebessentials.com/download](https://go.microsoft.com/fwlink/p/?LinkId=525629) 방문하세요. 
  
Web Essentials는 두 가지 형태의 번들링을 제공합니다.
  
- .bundle: CSS 및 JavaScript 파일용
    
- .sprite: 이미지의 경우(Visual Studio 2013)
    
사용자 지정 마스터 페이지 내에서 참조되는 일부 브랜징 요소가 있는 기존 기능이 있는 경우 Web Essentials를 사용할 수 있습니다.
  
![사용자 지정 마스터 페이지의 브랜드 요소 스크린샷.](../media/3a6eba36-973d-482b-8556-a9394b8ba19f.png)
  
 **Web Essentials에서 TE000127218 및 CSS 번들을 만들 수 있습니다.**
  
1. 이 Visual Studio 솔루션 탐색기에서 번들에 포함할 파일을 선택합니다.
    
2. 선택한 파일을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **Web Essentials** \> **JavaScript 번들** 파일 만들기를 선택합니다. 예시: 
    
    ![Web Essentials 메뉴 옵션을 보여 주는 스크린샷.](../media/41aac84c-4538-4f78-b454-46e651f868a3.png)
  
## <a name="viewing-the-results-of-bundling-javascript-and-css-files"></a>JavaScript 및 CSS 파일 번들링 결과 보기

JavaScript 및 CSS 번들을 만들 때 Web Essentials는 JavaScript 및 CSS 파일 및 기타 구성 정보를 식별하는 조리법 파일이라는 XML 파일을 만듭니다. 
  
![JavaScript 및 CSS 조리법 파일의 스크린샷.](../media/7ba891f8-52d8-467b-a0f6-b062dd1137a4.png)
  
또한 번들화법에서 minify 플래그를 true로 설정하면 파일 크기가 줄어들고 함께 번들화됩니다. 즉, 마스터 페이지에서 참조할 수 있는 새로운 JavaScript 파일 버전이 만들어졌습니다.
  
![minify 플래그를 true로 설정한 스크린샷.](../media/50523af2-6412-4117-ac3d-5bd26f6d562e.png)
  
웹 사이트에서 페이지를 로드할 때 웹 브라우저(예: Internet Explorer 11)에서 개발자 도구를 사용하여 서버로 전송된 요청 수와 각 파일을 로드하는 데 걸려오는 기간을 볼 수 있습니다.
  
다음 그림은 자르기 전에 JavaScript 및 CSS 파일을 로드한 결과입니다.
  
![다운로드되는 80개 항목을 보여 주는 스크린샷.](../media/e2df3912-1923-46e6-8cf2-3015a31554e1.png)
  
CSS 및 JavaScript 파일을 함께 번들링한 후 요청 수가 74개로 삭제된 후 각 파일이 원래 파일보다 약간 더 오래 걸려 개별적으로 다운로드했습니다.
  
![다운로드되는 74개 항목을 보여 주는 스크린샷.](../media/686c4387-70e8-4a74-9d45-059f33a91184.png)
  
번들링 후 JavaScript 번들 파일은 815KB에서 365KB로 크게 줄어듭니다.
  
![축소된 다운로드 크기를 보여 줄 수 있는 스크린샷.](../media/5e7dbd98-faff-4f68-b320-108fb252e395.png)
  
## <a name="bundling-images-by-creating-an-image-sprite"></a>이미지 스프라이트를 만들어 이미지 번들링

JavaScript 및 CSS 파일을 번들로 묶는 방법과 마찬가지로 많은 작은 아이콘과 기타 일반적인 이미지를 더 큰 스프라이트 시트에 결합한 다음 CSS를 사용하여 개별 이미지를 표시할 수 있습니다. 사용자의 웹 브라우저는 각 개별 이미지를 다운로드하는 대신 스프라이트 시트를 한 번 다운로드한 다음 로컬 컴퓨터에 캐시합니다. 이렇게하면 웹 서버로의 왕복 및 다운로드 수를 컷다운하여 페이지 로드 성능이 향상됩니다.
  
 **Web Essentials에서 이미지 스프라이트를 만들 수 있습니다.**
  
1. 이 Visual Studio 솔루션 탐색기에서 번들에 포함할 파일을 선택합니다.
    
2. 선택한 파일을 마우스 오른쪽 단추로 클릭한 다음 상황에 맞는 메뉴에서 **Web Essentials** 이미지 \> **스프라이트** 만들기를 선택합니다. 예시: 
    
    ![이미지 스프라이트를 만드는 방법을 보여주는 스크린샷.](../media/de0fe741-4ef7-4e3b-bafa-ef9f4822dac6.png)
  
3. 스프라이트 파일을 저장할 위치를 선택하십시오. .sprite 파일은 스프라이트의 설정 및 파일을 설명하는 XML 파일입니다. 다음 그림에서는 스프라이트 PNG 파일과 해당 .sprite XML 파일의 예를 보여 주었다.
    
    ![스프라이트 파일의 스크린샷.](../media/0876bb2a-d1b9-4169-8e95-9c290d628d90.png)
  
    ![스프라이트 XML 파일의 스크린샷.](../media/d1f94776-280d-4d56-abb5-384f145d9989.png)
  

