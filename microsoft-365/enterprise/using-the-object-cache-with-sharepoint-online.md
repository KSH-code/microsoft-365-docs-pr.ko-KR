---
title: SharePoint online에서 개체 캐시 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/20/2015
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: 38bc9c14-3826-449c-beb6-b1003bcbeaaf
description: 이 문서에서는 SharePoint Server 2013의 개체 캐시 사용과 SharePoint Online의 차이점에 대해 설명하고 있습니다.
ms.openlocfilehash: 40863ccf375620cf4b38d231fa0a86336c4826cc
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59210422"
---
# <a name="using-the-object-cache-with-sharepoint-online"></a>SharePoint online에서 개체 캐시 사용

이 문서에서는 SharePoint Server 2013의 개체 캐시 사용과 SharePoint Online의 차이점에 대해 설명하고 있습니다.
  
온라인 배포에서 개체 캐시에 대한 영향을 크게 SharePoint 있습니다. SharePoint Online의 개체 캐시에 종속하면 페이지의 안정성이 감소합니다. 
  
## <a name="how-the-sharepoint-online-and-sharepoint-server-2013-object-cache-works"></a>SharePoint Online 및 SharePoint Server 2013 개체 캐시의 작동 방식

SharePoint Server 2013이 사내에서 호스팅되는 경우 고객에게는 개체 캐시를 호스트하는 개인 프런트 엔드 웹 서버가 있습니다. 즉, 캐시는 고객 한 명에게만 전용으로 사용 가능하고 개체 캐시에 할당되는 메모리의 크기에 의해서만 제한됩니다. 프런트 엔드 웹 서버는 일반적으로 한 고객만이 동일한 사이트에 대한 요청을 여러 번 실행하게 됩니다. 즉, 캐시가 빠르게 가득 차고 사용자가 정기적으로 요청하는 SharePoint 쿼리 결과 및 모든 개체가 그대로 남아 있습니다.
  
![트래픽 및 부하를 사내 프런트 엔드 웹 서버로 보여줍니다.](../media/a0d38b36-4909-4abb-8d4e-4930814bb3de.png)
  
따라서 사용자가 페이지를 두 번째 방문하면 페이지 로드 시간이 향상됩니다. 같은 페이지의 부하가 네 개 이상이면 모든 프런트 엔드 웹 서버에서 해당 페이지가 캐시됩니다.
  
반면, SharePoint Online에는 서버가 더 많지만 사이트도 더 많이 있습니다. 각 사용자는 캐시를 채우지 않은 다른 프런트 엔드 웹 서버에 연결할 수 있습니다. 또는 캐시가 서버에 대해 채워지지만 해당 프런트 엔드 웹 서버의 다음 사용자가 다른 사이트에서 페이지를 요청합니다. 또는 다음 사용자가 이전 방문 시와 동일한 페이지를 요청하는 경우에도 해당 페이지가 캐시에 없는 다른 프런트 엔드 웹 서버로 부하가 조정됩니다. 이 마지막 경우 캐싱은 사용자에게 전혀 도움이되지 않습니다.
  
다음 그림에서 각 점은 사용자가 요청하는 페이지와 캐시된 페이지를 나타내고 있습니다. 서로 다른 색은 SaaS 인프라를 공유하는 다양한 고객을 나타내고 있습니다.
  
![Online에서 개체 캐싱의 결과를 SharePoint 나타냅니다.](../media/25d04011-ef83-4cb7-9e04-a6ed490f63c3.png)
  
다이어그램에서 볼 수 있 있든, 주어진 사용자가 해당 페이지의 캐시된 버전을 사용하여 서버를 적중할 가능성은 배제됩니다. 또한 많은 사이트 간에 서버가 공유되는 데 많고 캐시가 오래 지속되지는 않습니다. 캐싱을 사용할 수 있는 공간이 너무 많기 때문에 캐시가 오래 지속되지 않습니다.
  
이러한 모든 이유로 사용자가 캐시된 개체를 사용하게 하여 온라인에서 품질 사용자 환경 및 페이지 로드 시간을 보장하는 SharePoint 없습니다.
  
## <a name="if-we-cant-rely-on-the-object-cache-to-improve-performance-in-sharepoint-online-what-do-we-use-instead"></a>SharePoint Online에서 성능을 개선하기 위해 개체 캐시를 사용할 수 없는 경우 대신 무엇을 사용하나요?

SharePoint Online에서는 캐싱을 사용하지 말아야 하기 때문에 개체 캐시를 사용하는 SharePoint 사용자 지정에 대한 대체 디자인 방법을 평가해야 합니다. 즉, 사용자에게 좋은 결과를 얻기 위해 개체 캐싱을 사용하지 않는 성능 문제에 접근 방식을 사용합니다. 이 문서는 이 시리즈의 일부 다른 문서에 설명되어 있으며 다음을 포함합니다.
  
- [온라인용 탐색 SharePoint 옵션](navigation-options-for-sharepoint-online.md)
    
- [SharePoint Online의 축소 및 묶음](minification-and-bundling-in-sharepoint-online.md)
    
- [sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기](use-microsoft-365-cdn-with-spo.md)
    
- [SharePoint Online에서 이미지 및 JavaScript 로드 지연](delay-loading-images-and-javascript-in-sharepoint-online.md)
    

