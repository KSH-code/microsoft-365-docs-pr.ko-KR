---
title: SharePoint Online의 성능 조정 소개
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/22/2018
audience: Admin
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid: SPO160
ms.assetid: 81c4be5f-327e-435d-a568-526d68cffef0
description: 이 문서에서는 온라인에서 최상의 성능을 위해 페이지를 디자인할 때 고려해야 하는 특정 측면에 대해 SharePoint 있습니다.
ms.openlocfilehash: d2653e1ee07309d2f31a24df2715bf7810beb65b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215972"
---
# <a name="introduction-to-performance-tuning-for-sharepoint-online"></a>SharePoint Online의 성능 조정 소개

이 문서에서는 온라인에서 최상의 성능을 위해 페이지를 디자인할 때 고려해야 하는 특정 측면에 대해 SharePoint 있습니다.
     
## <a name="sharepoint-online-metrics"></a>SharePoint 온라인 메트릭

SharePoint Online에 대한 다음과 같은 광범위한 메트릭은 성능에 대한 실제 데이터를 제공합니다.
  
- 페이지 로드 속도
    
- 페이지당 필요한 왕복 수
    
- 서비스 문제
    
- 성능 저하를 일으키는 기타 것
    
### <a name="conclusions-reached-because-of-the-data"></a>데이터로 인하여 결론에 도달했습니다.

데이터는 다음을 알 수 있습니다.
  
- 대부분의 페이지는 온라인에서 SharePoint 있습니다.
    
- 사용자 지정되지 않은 페이지는 매우 빠르게 로드됩니다.
    
- 비즈니스용 OneDrive 팀 사이트 및 시스템 페이지(예: _layouts)는 모두 빠르게 로드됩니다.
    
- 온라인 페이지의 가장 느린 SharePoint 로드하는 데 5,000밀리초 이상이 걸릴 수 있습니다.
    
사용할 수 있는 한 가지 간단한 벤치마크 테스트는 사용자 지정된 기능이 거의 사용되지 비즈니스용 OneDrive 홈 페이지의 로드 시간을 비교하여 자체 포털의 로드 시간을 비교하여 성능을 측정하는 것입니다. 이 단계는 종종 지원에서 네트워크 성능 문제를 해결할 때 완료할지 묻는 첫 번째 단계가 됩니다.
  
## <a name="use-a-standard-user-account-when-checking-performance"></a>성능을 확인할 때 표준 사용자 계정 사용

사이트 모음 관리자, 사이트 소유자, 편집자 또는 참가자는 추가 보안 그룹에 속하며 추가 사용 권한을 가지기 때문에 페이지에 로드되는 추가 SharePoint 있습니다.
  
이 변경은 SharePoint 및 SharePoint Online에 적용할 수 있지만, SharePoint Online과는 다른 차이점이 쉽게 SharePoint 않습니다.
  
사용자에 대해 페이지가 어떻게 수행될지 올바르게 평가하려면 표준 사용자 계정을 사용하여 제작 컨트롤 및 보안 그룹과 관련된 추가 트래픽이 로드되지 않도록 해야 합니다.
  
## <a name="connection-categories-for-performance-tuning"></a>성능 조정을 위한 연결 범주

서버와 사용자 간의 연결을 세 가지 기본 구성 요소로 분류할 수 있습니다. 로드 시간을 SharePoint 온라인 페이지를 디자인할 때 이러한 정보를 고려하세요.
  
- **서버** Microsoft가 데이터 센터에서 호스팅하는 서버입니다.
    
- **네트워크** 데이터 센터와 사용자 간의 Microsoft 네트워크, 인터넷 및 사내 네트워크
    
- **브라우저** 페이지가 로드되는 위치입니다.
    
이러한 세 연결 내에 일반적으로 페이지 속도가 95%인 5가지 이유가 있습니다. 이 문서에서는 이러한 각 이유에 대해 논의합니다.
  
- 탐색 문제
    
- 콘텐츠 롤업
    
- 큰 파일
    
- 서버에 대한 많은 요청
    
- 웹 파트 처리
    
### <a name="server-connection"></a>서버 연결

SharePoint 성능에 영향을 주는 대부분의 문제는 SharePoint Online에도 적용됩니다.
  
예상한 것 처럼, 서버가 프레미스 프레미스 서버로 수행하는 방법을 훨씬 더 SharePoint. 온라인 SharePoint 약간 다릅니다. 서버에서 더 많은 작업을 할수록 페이지를 렌더링하는 데 더 오래 걸립니다. 이 SharePoint 가장 큰 장점은 여러 웹 파트가 있는 복잡한 페이지입니다.
  
SharePoint 서버 On-premises
  
![Screenshot of server on premises.](../media/a8e9b646-cdff-4131-976a-b5f891da44ac.png)
  
SharePoint Online
  
![온라인 서버 스크린샷.](../media/46b27ded-d8a4-4287-b3e0-2603a764b8f8.png)
  
온라인 SharePoint 특정 페이지 요청이 실제로 여러 서버를 호출하게 될 수 있습니다. 개별 요청에 대한 서버 간의 요청 행렬이 끝날 수 있습니다. 이러한 조작은 페이지 로드 관점에서 비용이 많이 들고 속도가 느려질 수 있습니다.
  
서버 간 상호 작용의 예는 다음과 같습니다.
  
- 웹에서 SQL 서버로
    
- 웹에서 응용 프로그램 서버로
    
서버 상호 작용이 느려질 수 있는 다른 점은 캐시 누락입니다. 프레미스 SharePoint 달리 이전에 방문한 페이지에 대해 동일한 서버를 적중할 가능성이 매우 높습니다. 이렇게 하면 개체 캐싱이 사용되지 않습니다.
  
### <a name="network-connection"></a>네트워크 연결

WAN을 사용하지 않는 SharePoint 사용하여 데이터 센터와 최종 사용자 간의 고속 연결을 사용할 수 있습니다. 일반적으로 네트워크 관점에서는 쉽게 관리할 수 있습니다.
  
온라인 SharePoint 고려할 몇 가지 추가 요인이 있습니다. 예를 들어:
  
- Microsoft 네트워크
    
- 인터넷
    
- The ISP
    
사용 SharePoint(및 네트워크)에 관계없이 일반적으로 네트워크가 사용 중이 될 수 있는 작업은 다음과 같습니다.
  
- 큰 페이로드
    
- 많은 파일
    
- 서버와의 실제 거리가 먼 거리
    
SharePoint Online에서 활용할 수 있는 한 가지 기능은 Microsoft CDN(Content Delivery Network). 이 CDN 기본적으로 여러 데이터 센터에 배포된 분산된 서버 모음입니다. 클라이언트 CDN 원래 서버와 멀리 떨어져 있는 경우에도 페이지의 콘텐츠를 클라이언트와 가까운 서버에서 호스팅할 SharePoint 있습니다. Microsoft는 향후 이 기능을 사용하여 사용자 지정할 수 없는 페이지의 로컬 인스턴스(예: SharePoint 온라인 관리 홈 페이지)를 저장할 예정입니다. CDNS에 대한 자세한 내용은 콘텐츠 배달 [네트워크를 참조하세요.](content-delivery-networks.md)
  
주의해야 하지만 ISP의 연결 속도에 대해 많은 작업을 하지 않을 수 있습니다. 간단한 속도 테스트 도구로 연결 속도를 알 수 있습니다.
  
### <a name="browser-connection"></a>브라우저 연결

성능 관점에서 웹 브라우저에서 고려해야 할 몇 가지 요인이 있습니다.
  
복잡한 페이지를 방문하면 성능에 영향을 미치게 됩니다. 대부분의 브라우저에는 작은 캐시(약 90MB)만 있는 반면, 평균 웹 페이지는 일반적으로 약 1.6MB입니다. 이렇게 하는 데는 시간이 오래 걸릴 수 없습니다.
  
대역폭도 문제가 될 수 있습니다. 예를 들어 사용자가 다른 세션에서 비디오를 보고 있는 경우 이로 설정하면 사용자 페이지의 성능에 SharePoint 있습니다. 사용자가 스트리밍 미디어를 스트리밍하지 못하게 할 수 있는 반면, 사용자가 페이지를 로드하는 방법을 제어할 수 있습니다.
  
최적의 성능을 얻을 수 있도록 다양한 SharePoint 온라인 페이지 사용자 지정 기술 및 기타 모범 사례에 대한 다음 문서를 참조하세요.
  
- [온라인용 탐색 SharePoint 옵션](navigation-options-for-sharepoint-online.md)
    
- [온라인용 페이지 진단 SharePoint 사용](page-diagnostics-for-spo.md)
    
- [SharePoint Online에 대한 이미지 최적화](image-optimization-for-sharepoint-online.md)
    
- [SharePoint Online에서 이미지 및 JavaScript 로드 지연](delay-loading-images-and-javascript-in-sharepoint-online.md)
    
- [SharePoint Online의 축소 및 묶음](minification-and-bundling-in-sharepoint-online.md)
    
- [sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기](use-microsoft-365-cdn-with-spo.md)
    
- [콘텐츠 쿼리 웹 파트 대신 콘텐츠 검색 웹 파트를 사용하여 온라인에서 SharePoint 향상](using-content-search-web-part-instead-of-content-query-web-part-to-improve-perfo.md)
    
- [Capacity planning and load testing SharePoint Online](capacity-planning-and-load-testing-sharepoint-online.md)(용량 계획과 부하 테스트가 가능한 SharePoint Online)
    
- [SharePoint Online의 성능 문제 진단](diagnosing-performance-issues-with-sharepoint-online.md)
    
- [SharePoint online에서 개체 캐시 사용](using-the-object-cache-with-sharepoint-online.md)
    
- [How to: Avoid gettrottled or blocked in SharePoint Online](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)
