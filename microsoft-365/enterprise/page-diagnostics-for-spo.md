---
title: SharePoint Online용 페이지 진단 도구 사용
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/03/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPO160
- MOE150
- BSA160
f1.keywords:
- NOCSH
description: SharePoint용 페이지 진단 도구를 사용하여 미리 정의된 성능 기준 집합에 대해 SharePoint Online 최신 포털 및 클래식 게시 페이지를 분석합니다.
ms.openlocfilehash: 2598f2a8c7801a762133c93761d2910a220dc194
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696345"
---
# <a name="use-the-page-diagnostics-for-sharepoint-tool"></a>SharePoint용 페이지 진단 도구 사용

이 문서에서는 **SharePoint용 페이지** 진단 도구를 사용하여 미리 정의된 성능 기준 집합에 대해 SharePoint Online 최신 및 클래식 사이트 페이지를 분석하는 방법을 설명합니다.

다음에 대해 SharePoint용 페이지 진단 도구를 설치할 수 있습니다.

- **Microsoft** [Edge(Edge 확장)](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji)
- **Chrome(Chrome** [확장)](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi)

>[!TIP]
>버전 **2.0.0** 이상에는 클래식 사이트 페이지뿐만 아니라 최신 페이지도 지원됩니다. 사용하고 있는 도구의 버전을 확인할 수 없는 경우 링크  또는 타원(...)을 선택하여 버전을 확인할 수 있습니다. **도구를 사용할** 때 항상 최신 버전으로 업데이트합니다.

SharePoint용 페이지 진단 도구는 새 Microsoft Edge에 대한 브라우저 확장입니다. (SharePoint Online 최신 포털 및 클래식 게시 사이트 페이지를 분석하는 https://www.microsoft.com/edge) 및 Chrome 브라우저) 이 도구는 SharePoint Online에서만 작동하며 SharePoint 시스템 페이지에서는 사용할 수 없습니다.

이 도구는 분석된 각 페이지에 대해 미리 정의된 규칙 집합에 대해 페이지가 수행되는 방법을 보여 주며 테스트 결과가 기준 값에 맞지 않은 경우 자세한 정보를 표시하는 보고서를 생성합니다. SharePoint Online 관리자 및 디자이너는 이 도구를 사용하여 성능 문제를 해결하고 게시하기 전에 새 페이지를 최적화할 수 있습니다.

페이지 진단 도구는 *allitems.aspx* 또는 *sharepoint.aspx와* 같은 시스템 페이지가 아니라 SharePoint 사이트 페이지만 분석하도록 디자인됩니다. 시스템 페이지 또는 다른 비사이트 페이지에서 도구를 실행하려고 하면 해당 유형의 페이지에 대해 도구를 실행할 수 없다는 오류 메시지가 표시됩니다.

![SharePoint 페이지에서 실행해야 합니다.](../media/page-diagnostics-for-spo/pagediag-Error-StartPage.png)

라이브러리 또는 시스템 페이지를 평가하는 데 값이 없는 경우 이 오류는 도구에서 오류가 되지 않습니다. 이 도구를 사용하려면 SharePoint 사이트 페이지로 이동합니다. SharePoint 페이지에서 이 오류가 발생하는 경우 마스터 페이지를 확인하여 SharePoint 메타태그가 제거되지 않은지 확인하십시오.

도구에 대한 피드백을 제공하려면 도구의 오른쪽 위 모서리에 있는 줄임차를 선택한 다음 피드백 보내기를 [선택합니다.](https://go.microsoft.com/fwlink/?linkid=874109)

![피드백 제공](../media/page-diagnostics-for-spo/pagediag-feedback.png)
  
## <a name="install-the-page-diagnostics-for-sharepoint-tool"></a>SharePoint용 페이지 진단 도구 설치

이 섹션의 설치 절차는 Chrome 및 Microsoft Edge 브라우저에서 모두 사용할 수 있습니다.

> [!IMPORTANT]
> Microsoft는 SharePoint용 페이지 진단 도구로 분석되는 데이터 또는 페이지 콘텐츠를 읽지 않고 개인 정보, 웹 사이트 또는 다운로드 정보를 캡처하지 않습니다. 이 도구로 Microsoft에 기록되는 식별 가능한 정보는 테넌트 이름, 실패한 규칙 수, 도구가 실행된 날짜 및 시간뿐입니다. 이 정보는 Microsoft에서 최신 포털 및 게시 사이트 사용 추세와 일반적인 성능 문제를 보다 잘 이해하는 데 사용됩니다.

1. **Microsoft Edge(Edge** [](https://microsoftedge.microsoft.com/addons/detail/ocemkolpnamjcacndljdfmhlpcaoipji) 확장) 또는 **Chrome(Chrome** 확장)에 대한 SharePoint용 페이지 진단 [도구를 설치합니다.](https://chrome.google.com/webstore/detail/inahogkhlkbkjkkaleonemeijihmfagi) 스토어의 설명 페이지에 제공된 사용자 개인 정보 취급 방침을 검토하세요. When adding the tool to your browser, you will see the following permissions notice.

    ![확장 권한](../media/page-diagnostics-for-spo/pagediag-add-to-edge.png)

    이 알림은 페이지의 웹 파트 및 사용자 지정 내용에 따라 페이지에 SharePoint 외부 위치의 콘텐츠가 포함될 수 있기 때문에 설정됩니다. 즉, 시작 단추를 클릭할 때 도구가 실행 중인 활성 SharePoint 탭에만 요청 및 응답을 읽게 됩니다. 이 정보는 웹 브라우저에서 로컬로 캡처하며 도구의 네트워크 추적 탭에서 **JSON으로** 내보내기  또는 **HAR로** 내보내기 단추를 통해 사용할 수 있습니다. 이 정보는 Microsoft로 전송되거나 Microsoft에 의해 캡처되지 **않습니다.** (이 도구는 여기에 액세스할 수 있는 Microsoft 개인 정보 취급 [방침을](https://go.microsoft.com/fwlink/p/?linkid=857875)준수합니다.)

    다운로드 _관리 권한에서는_ 도구의 **JSON로** 내보내기 기능을 사용하는 방법을 다를 수 있습니다. 결과에는 URL이 포함되어 있으며 PII(개인 식별이 가능한 정보)로 분류될 수 있는 JSON 파일을 조직 외부에서 공유하기 전에 회사의 자체 개인 정보 보호 지침을 따르세요.
1. Incognito 또는 InPrivate 모드에서 도구를 사용하려면 브라우저에 대한 절차를 따르고자 합니다.
    1. Microsoft Edge에서 URL edge://extensions 확장  또는 입력 파일로 이동하고  확장에 대한 세부 정보를 선택합니다.  확장 설정에서 **InPrivate에서 허용할 확인란을 선택합니다.**
    1. Chrome에서 URL **chrome://extensions** 확장  또는 확장을 입력하고 확장에 대한 세부 정보를 선택합니다.  확장 설정에서 **Incognito에서** 허용할 슬라이더를 선택합니다.
1. 검토할 SharePoint Online의 SharePoint 사이트 페이지로 이동합니다. 페이지에서 항목의 "로드 지연"이 허용됩니다. 따라서 도구가 자동으로 중지되지는 않습니다(모든 페이지 로드 시나리오를 수용하기 위해 디자인). 컬렉션을 중지하려면 **중지를 선택합니다.** 데이터 수집을 중지하기 전에 페이지 로드가 완료된지 확인하거나 부분 추적만 캡처합니다.
1. 확장의 도구 모음 단추 클릭 ![SharePoint 로고에 대한 페이지 진단](../media/page-diagnostics-for-spo/pagediag-icon32.png) 도구를 로드하면 다음 확장 팝업 창이 표시됩니다.

    ![페이지 진단 도구 팝업](../media/page-diagnostics-for-spo/pagediag-Landing.png)

분석을 **위해** 데이터 수집을 시작하려면 시작을 선택합니다.

## <a name="what-youll-see-in-the-page-diagnostics-for-sharepoint-tool"></a>SharePoint용 페이지 진단 도구에서 볼 수 있는 정보

1. 도구의 오른쪽 위 모서리에 있는 타원(...)을 클릭하여 다음 링크를 찾을 수 있습니다.
   1. 추가 **리소스 링크는** 이 문서로 돌아가는 링크를 포함하여 도구에 대한 일반적인 지침과 세부 정보를 제공합니다.
   1. 피드백 **보내기 링크는** SharePoint 사이트 및 공동 작업 사용자 음성 사이트에 _대한 링크를 제공합니다._
   1. 정보  링크에는 현재 설치된 도구 버전과 도구의 타사 알림에 대한 직접 링크가 포함되어 있습니다.  
1. **상관 관계 ID, SPRequestDuration, SPIISLatency,** 페이지 로드 시간 및 **URL** 세부 정보는 정보를 제공하며 몇 가지 용도로 사용할 수 있습니다. 

    ![페이지 진단 세부 정보](../media/page-diagnostics-for-spo/pagediag-details.PNG)

   - **CorrelationID는** Microsoft 지원 서비스에서 특정 페이지에 대한 추가 진단 데이터를 수집할 수 있도록 하는 중요한 요소입니다.
   - **SPRequestDuration은** SharePoint에서 페이지를 처리하는 데 들이는 시간입니다. 구조 탐색, 큰 이미지, 많은 API 호출이 모두 더 긴 기간에 기여할 수 있습니다.
   - **SPIISLatency는** SharePoint Online에서 페이지 로드를 시작하는 데 들이는 시간(밀리초)입니다. 이 값에는 웹 응용 프로그램이 응답하는 데 들이는 시간이 포함되어 있지 않습니다.
   - **페이지 로드 시간은** 요청 시간부터 응답이 수신 및 브라우저에서 렌더링된 시간까지 페이지에 의해 기록된 총 시간입니다. 이 값은 네트워크 대기 시간, 컴퓨터의 성능 및 브라우저가 페이지를 로드하는 데 걸리는 시간을 비롯한 다양한 요인의 영향을받습니다.
   - 페이지 **URL(Uniform** Resource Locator)은 현재 페이지의 웹 주소입니다.

1. 진단 [**테스트 탭에는**](#how-to-use-the-diagnostic-tests-tab) 분석 결과가 세 가지 범주로 표시됩니다. **조치가 필요하지 않습니다.** **개선 기회** 및 **주의가 필요하지 않습니다.** 다음 표에 설명된 각 테스트 결과는 다음 범주 중 하나의 항목으로 표시됩니다.

    |범주  |색  |설명  |
    |---------|---------|---------|
    |**주의 필요** |빨강 |테스트 결과는 기준 값 외부에 있으며 페이지 성능에 영향을 미치고 있습니다. 수정 지침을 따르는 경우|
    |**개선 기회** |노란색 |테스트 결과는 기준 값을 능가하여 성능 문제에 기여할 수 있습니다. 테스트 관련 조건이 적용될 수 있습니다.|
    |**필요한 작업 없음** |녹색 |테스트 결과는 테스트의 기준 값에 해당합니다.|

    ![페이지 진단](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

1. 네트워크 [**추적 탭은**](#how-to-use-the-network-trace-tab) 페이지 빌드 요청 및 응답에 대한 세부 정보를 제공합니다.

## <a name="how-to-use-the-diagnostic-tests-tab"></a>진단 테스트 탭을 사용하는 방법

SharePoint용 페이지 진단 도구를 사용하여 SharePoint 최신 포털 페이지 또는 클래식 게시 사이트 페이지를 분석하는 경우 결과를 기준 값과 비교하고  진단 테스트 탭에 표시되는 미리 정의된 규칙을 사용하여 결과를 분석합니다. 특정 테스트에 대한 규칙은 두 테스트 간의 특정 성능 특성이 어떻게 다른지에 따라 최신 포털 및 클래식 게시 사이트에 대해 서로 다른 기준 값을 사용할 수 있습니다.

개선 기회 또는  주의 필요  범주에 나타나는 테스트 결과는 권장 사례에 대해 검토해야 하는 영역을 나타내며 결과에 대한 추가 정보를 표시하기 위해 선택할 수 있습니다. 각 항목에 대한 세부  정보에는 테스트와 관련된 적절한 지침으로 바로 연결되는 자세한 정보 링크가 포함되어 있습니다. 작업 필요 없음  범주에 나타나는 테스트 결과는 관련 규칙의 준수를 나타내며, 선택한 경우 추가 세부 정보를 표시하지 않습니다.

진단 테스트 탭의 정보는 페이지를 디자인하는 방법을 설명하지 않지만 페이지 성능에 영향을 줄 수 있는 요인을 강조합니다. 일부 페이지 기능 및 사용자 지정은 페이지 성능에 불가피한 영향을 미치며, 해당 영향이 큰 경우 페이지에서 잠재적인 수정 또는 누락을 검토해야 합니다.

빨간색 또는 노란색 결과는 데이터를 너무 자주 새로 고치는 웹 파트를 나타낼 수도 있습니다. 예를 들어 회사 뉴스는 매 초마다 업데이트되지 않지만 사용자 지정 웹 파트는 전체 사용자 환경을 개선할 수 있는 캐싱 요소를 구현하는 대신 매 초마다 최신 뉴스를 표시하도록 구축되는 경우가 종종 있습니다. 페이지에 웹 파트를 포함하면 사용 가능한 각 매개 변수의 값을 평가하여 의도한 용도에 적절하게 설정되도록 하여 성능에 미치는 영향을 줄이는 간단한 방법이 있는 경우가 종종 있습니다.

>[!NOTE]
>게시 기능을 사용하도록 설정하지 않은 클래식 팀 사이트는 CDNS를 사용할 수 없습니다. 이러한 사이트에서 도구를 실행하면 CDN 테스트가 실패하고 무시될 수 있지만 나머지 테스트는 모두 적용할 수 있습니다. SharePoint 게시 기능의 추가 기능을 사용하면 페이지 로드 시간이 늘어날 수 있으므로 CDN 기능을 허용하기 위해 사용하도록 설정하면 안 됩니다.

>[!IMPORTANT]
>테스트 규칙은 정기적으로 추가 및 업데이트됩니다. 따라서 테스트 결과에 포함된 현재 규칙 및 특정 정보에 대한 자세한 내용은 최신 버전의 도구를 참조하세요. 확장을 관리하여 버전을 확인할 수 있으며 확장은 업데이트를 사용할 수 있는지 여부를 권고합니다.

## <a name="how-to-use-the-network-trace-tab"></a>네트워크 추적 탭을 사용하는 방법

네트워크 **추적** 탭에서는 페이지 작성 요청과 SharePoint에서 받은 응답에 대한 자세한 정보를 제공합니다.

1. **빨간색으로 플래그가 지정된** 항목 로드 시간을 찾아 봐야 합니다. 각 요청 및 응답은 다음 대기 시간 메트릭을 사용하여 전체 페이지 성능에 미치는 영향을 나타내기 위해 색으로 코딩됩니다.
    - 녹색: \< 500ms
    - 노란색: 500-1000ms
    - 빨간색: \> 1,000ms

    ![네트워크 추적](../media/page-diagnostics-for-spo/pagediag-networktrace-red.png)

    위에 표시된 이미지에서 빨간색 항목은 기본 페이지에 해당합니다. 페이지가 \< 1000ms(1초 미만)로 로드되지 않는 한 항상 빨간색으로 표시됩니다.

2. **테스트 항목 로드 시간입니다.** 경우에 따라 항목이 브라우저에 의해 이미 캐시되어 있기 때문에 시간 또는 색 표시기가 없는 경우도 있습니다. 이 테스트를 올바르게 테스트하려면 페이지를 열고 브라우저  캐시를 지운 다음 시작을 클릭하여 "콜드" 페이지 로드를 강제로 실행하고 초기 페이지 로드를 실제 반영합니다. 그런 다음 "웜" 페이지 로드와 비교해야 합니다. 그러면 페이지에 캐시되는 항목을 확인하는 데도 도움이 됩니다.

3. 문제를 조사하는 데 도움이 되는 다른 사용자와 관련 **세부 정보를 공유합니다.** 도구에 제공된 세부 정보 또는 정보를 개발자 또는 기술 지원 사용자와 공유하려면 **JSON으로** 내보내기(위 이미지에 표시된 대로)를 클릭합니다. 이를 통해 JSON 파일 뷰어에서 볼 수 있는 결과를 다운로드할 수 있습니다.

    미리 보기 기능을 사용하도록 설정한 경우 *HAR로* 내보내기 기능을 사용하도록 설정하면 내보내기 유형이 **HAR로 내보내기로 표시됩니다.**

    ![네트워크 추적](../media/page-diagnostics-for-spo/pagediag-NetworkTraceHAR.PNG)

> [!IMPORTANT]
> 이러한 결과에는 PII(개인 식별이 가능한 정보)로 분류할 수 있는 URL이 포함되어 있습니다. 해당 정보를 배포하기 전에 조직의 지침을 따라야 합니다.

## <a name="engaging-with-microsoft-support"></a>Microsoft 지원 참여

지원 사례에서 직접 작업할 때만 활용해야 하는 **Microsoft** 지원 수준 기능이 포함되어 있습니다. 이 기능을 사용하면 팀 참여를 지원하지 않고 사용할 경우 이점이 제공되지 않고 페이지가 크게 느려질 수 있습니다. 서비스 로깅에 추가 정보가 추가될 때 도구에서 이 기능을 사용할 경우 추가 정보가 없습니다.

이 기능을 사용하도록 설정하고 페이지 성능이 2~3배 느려지며 사용하도록 설정했다는 알림을 들은 경우를 제외하고는 어떤 변경도 표시되지 않습니다. 특정 페이지 및 해당 활성 세션에만 해당합니다. 이러한 이유로 지원에 적극적으로 참여할 때만 이 를 사용해야 합니다.

### <a name="to-enable-the-microsoft-support-level-feature"></a>Microsoft 지원 수준 기능을 사용하도록 설정하려면

1. SharePoint용 페이지 진단 도구를 여십시오.
2. 키보드에서 **Alt-Shift-L을 누릅니다.** 그러면 지원 **로깅 사용 확인란이** 표시됩니다.
3. 확인란을 선택한 다음  시작을 클릭하여 페이지를 다시 로드하고 자세한 로깅을 생성합니다.

    ![지원 옵션 사용](../media/page-diagnostics-for-spo/pagediag-support.png)
  
    CorrelationID(도구 맨 위에 표시)를 메모하고 지원 담당자에게 제공하여 진단 세션에 대한 추가 정보를 수집할 수 있도록 해야 합니다.

## <a name="related-topics"></a>관련 항목

[SharePoint Online 성능 조정](tune-sharepoint-online-performance.md)

[Office 365 성능 조정](tune-microsoft-365-performance.md)

[최신 SharePoint 환경의 성능](https://docs.microsoft.com/sharepoint/modern-experience-performance)

[콘텐츠 배달 네트워크](content-delivery-networks.md)

[sharepoint Online을 활용해 Office 365 콘텐츠 배달 네트워크(CDN) 사용하기](use-microsoft-365-cdn-with-spo.md)
