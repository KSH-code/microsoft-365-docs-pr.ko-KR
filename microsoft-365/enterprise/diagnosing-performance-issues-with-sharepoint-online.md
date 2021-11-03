---
title: SharePoint Online의 성능 문제 진단
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/9/2019
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
ms.assetid: 3c364f9e-b9f6-4da4-a792-c8e8c8cd2e86
description: 이 문서에서는 개발자 도구를 사용하여 SharePoint 일반적인 문제를 진단하는 Internet Explorer 방법을 보여줍니다.
ms.openlocfilehash: bb12bc6b8b8f95c33ad35aafad760803e927e830
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60664942"
---
# <a name="diagnosing-performance-issues-with-sharepoint-online"></a>SharePoint Online의 성능 문제 진단

이 문서에서는 개발자 도구를 사용하여 SharePoint 일반적인 문제를 진단하는 Internet Explorer 방법을 보여줍니다.
  
온라인 사이트의 페이지에 사용자 지정에 성능 문제가 SharePoint 식별할 수 있는 방법에는 세 가지가 있습니다.
  
- F12 도구 모음 네트워크 모니터

- 사용자 지정되지 않은 기준과 비교

- SharePoint 온라인 응답 헤더 메트릭

이 항목에서는 이러한 각 방법을 사용하여 성능 문제를 진단하는 방법에 대해 설명합니다. 문제의 원인을 찾은 후 에서 찾을 수 있는 성능 향상에 대한 문서를 SharePoint 해결 방법을 찾을 수 https://aka.ms/tune 있습니다. 또는 관리자인 경우 문제를 빠르게 진단하려면 이 진단 [도구를 실행합니다.](https://aka.ms/PillarSiteandPagePerf) 
  
## <a name="using-the-f12-tool-bar-to-diagnose-performance-in-sharepoint-online"></a>F12 도구 모음을 사용하여 온라인에서 SharePoint 진단
<a name="F12ToolInfo"> </a>

이 문서에서는 11에 Internet Explorer 있습니다. 다른 브라우저의 F12 개발자 도구 버전은 약간 다를 수 있습니다. F12 개발자 도구에 대한 자세한 내용은 다음을 참조하세요.
  
- [F12 도구의 새로운 기능](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

- [F12 개발자 도구 사용](/previous-versions/windows/internet-explorer/ie-developer/samples/bg182326(v=vs.85))

개발자 도구를 표시하려면 **F12를 누를** 때 다음 아이콘을 Wi-Fi 클릭합니다.
  
![F12 개발자 도구 Wi-Fi 아이콘 스크린샷.](../media/27acacbb-5688-459a-aa2f-5c8c5f17b76e.png)
  
네트워크 **탭에서** 녹색 재생 단추를 눌러 페이지를 로드합니다. 이 도구는 요청한 페이지를 다운로드하기 위해 브라우저에서 요청하는 모든 파일을 반환합니다. 다음 스크린샷에는 이러한 목록이 하나 표시됩니다.
  
![페이지 요청을 통해 반환되는 파일 목록의 스크린샷](../media/247a9422-76da-4b0c-bed3-ce77b05e4560.png)
  
이 스크린샷과 같이 오른쪽에서 파일의 다운로드 시간을 볼 수 있습니다.
  
![요청된 페이지를 웹 페이지에서 로드하는 데 걸리는 시간을 보여 SharePoint.](../media/d71ad1fa-9018-4fae-82eb-c1838e7db0ff.png)
  
이렇게 하면 파일을 로드하는 데 걸려진 기간을 시각적으로 확인할 수 있습니다. 녹색 선은 브라우저에서 페이지를 렌더링할 준비가 된 때를 나타내는 선입니다. 이렇게하면 사이트에서 페이지 로드가 느려질 수 있는 여러 파일을 빠르게 볼 수 있습니다.
  
## <a name="setting-up-a-non-customized-baseline-for-sharepoint-online"></a>SharePoint Online에 대해 사용자 지정되지 않은 기준 설정
<a name="F12ToolInfo"> </a>

사이트의 성능 약점을 확인하는 가장 좋은 방법은 온라인에서 완전히 새로운 사이트 모음을 SharePoint 것입니다. 이렇게 하면 사이트의 모든 다양한 측면과 페이지에서 사용자 지정하지 않고도 얻을 수 있는 측면을 비교할 수 있습니다. 이 비즈니스용 OneDrive 페이지는 사용자 지정이 없는 별도의 사이트 모음의 좋은 예입니다.
  
## <a name="viewing-sharepoint-response-header-information"></a>응답 SharePoint 정보 보기
<a name="F12ToolInfo"> </a>

온라인 SharePoint 각 파일의 응답 헤더에서 브라우저로 다시 전송되는 정보에 액세스할 수 있습니다. 성능 문제를 평가하는 데 가장 유용한 값은 요청이 처리되는 데 걸려오는 시간을 표시하는 **SPRequestDuration입니다.** 이렇게하면 요청이 매우 과도하고 리소스를 많이 사용하는지 여부를 확인하는 데 도움이 될 수 있습니다. 서버가 페이지를 제공하는 데 얼마나 많은 작업을 수행하고 있는지 파악하는 데 가장 적합한 정보입니다.

### <a name="to-view-sharepoint-response-header-information"></a>응답 SharePoint 정보를 보기 위해
  
1. F12 도구가 설치되어 있는지 확인합니다. 이러한 도구를 다운로드하고 설치하는 데 대한 자세한 내용은 F12 도구의 새로운 [기능 을 참조하세요.](/previous-versions/windows/internet-explorer/ie-developer/dev-guides/bg182632(v=vs.85))

2. F12 도구의 네트워크 **탭에서** 녹색 재생 단추를 눌러 페이지를 로드합니다.

3. 도구에서 반환된 .aspx 파일 중 하나를 클릭한 다음 **세부 정보 를 클릭합니다.**

    ![응답 헤더의 세부 정보를 보여줍니다.](../media/1f8a044a-caf8-4613-be2b-7e064141ac8a.png)
  
4. 응답 **헤더 를 클릭합니다.**

    ![응답 헤더의 URL을 보여 주는 다이어그램입니다.](../media/efc7076e-447e-447e-882a-ae3aa721e2c3.png)
  
## <a name="whats-causing-performance-issues-in-sharepoint-online"></a>온라인에서 성능 문제를 일으키는 원인은 SharePoint?
<a name="F12ToolInfo"> </a>

SharePoint [Online의](navigation-options-for-sharepoint-online.md) 탐색 옵션 문서에서는 SPRequestDuration 값을 사용하여 복잡한 구조 탐색으로 인해 서버에서 페이지를 처리하기까지 시간이 오래 걸릴 수 있는 예를 보여줍니다. 사용자 지정하지 않고 기준 사이트의 값을 사용하여 특정 파일을 로드하는 데 시간이 오래 필요한지 확인할 수 있습니다. SharePoint [Online의](navigation-options-for-sharepoint-online.md) 탐색 옵션에 사용되는 예제는 기본 .aspx 파일입니다. 이 파일에는 페이지 로드에 ASP.NET 실행되는 대부분의 코드가 포함되어 있습니다. 사용하는 사이트 서식 파일에 따라 홈 페이지를 사용자 지정하는 경우 start.aspx, home.aspx, default.aspx 또는 다른 이름이 될 수 있습니다. 이 수치가 기준 사이트보다 훨씬 높은 경우 페이지에 성능 문제를 일으키는 복잡한 문제가 있는 것을 표시하는 것이 좋습니다.
  
사이트와 관련한 문제가 확인되면 성능 향상을 위해 권장되는 방법은 페이지 사용자 지정과 같은 가능한 모든 원인을 제거한 다음 사이트에 하나씩 다시 추가하는 것입니다. 페이지가 잘 수행되는 충분한 사용자 지정을 제거한 후 특정 사용자 지정을 하나씩 다시 추가할 수 있습니다.
  
예를 들어 매우 복잡한 탐색이 있는 경우 탐색을 변경하여 하위 사이트를 표시하지 않습니다. 그런 다음 개발자 도구를 확인하여 이로 인해 차이가 나는지 확인할 수 있습니다. 또는 많은 양의 콘텐츠 롤업이 있는 경우 페이지에서 이를 제거하고 개선되는지 확인하십시오. 가능한 모든 원인을 제거하고 한 번씩 다시 추가하는 경우 가장 큰 문제인 기능을 쉽게 식별한 다음 해결을 진행할 수 있습니다.
