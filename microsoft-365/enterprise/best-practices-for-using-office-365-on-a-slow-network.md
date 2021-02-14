---
title: 저속 네트워크에서 Office 365를 사용하는 모범 사례
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: 이 문서에서는 느린 네트워크에서 Office 365를 사용하기 위해 채택할 수 있는 모범 사례를 안내합니다.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/14/2020
ms.locfileid: "46692700"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>저속 네트워크에서 Office 365를 사용하는 모범 사례

인터넷 연결이 항상 빠르며 다운되지 않는 것이 좋은가요? 그 날이 오게 될 것입니다. 하지만 그동안 발키리 네트워크를 해결하고 매일 작업을 완료하기 위해 할 수 있는 실용적인 작업들이 있습니다. Office 365는 클라우드 기반 서비스지만 오프라인으로 콘텐츠를 작업하고 변경 내용을 동기화된 상태로 유지하는 다양한 방법도 제공합니다. 또한 응용 프로그램이 더 빠르게 실행하고 사용자 인터페이스의 응답성이 더 높기 때문에 오프라인으로 콘텐츠를 사용하는 것이 더 효율적일 수 있습니다. 이 점은 Office 365를 통해 두 세계 최고의 결과를 제공합니다. 이를 활용하는 방법에는 다음과 같은 것이 있습니다. 
  
> [!TIP]
> 네트워크 연결 속도가 얼마나 느리거나 빠른지 확인하려는 경우 [OOKLA 속도 테스트](https://www.speedtest.net/) 또는 네트워크 속도 테스트 [앱을 사용해 하세요.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70) 

## <a name="why-is-my-network-so-slow"></a>네트워크 속도가 너무 느려야 하는 이유는 무엇입니까?

네트워크 성능 자체를 제어할 수 있는 것은 아니어도, 그 배경에서 어떤 일이 진행하는지 이해하는 데 도움이 됩니다. 인터넷은 매우 복잡하지만 상황을 훨씬 더 잘 이해할 수 있는 몇 가지 개념이 있습니다. 이 문서의 모범 사례를 따라 문제를 해결하고 좌절을 줄일 수 있습니다.
  
**네트워크 성능에 영향을 주는 주요 요인**

![네트워크 성능 요인](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **대역폭 및 대기 시간** 네트워크 성능의 가장 중요한 두 가지 측정값은 대역폭과 대기 시간입니다. 
  
- 대역폭은 비트(초당 비트)로 측정된 속도입니다. 더 큰 것이 좋습니다. 대역폭은 수도 파이프와 같아야 합니다. 파이프가 클수록 "통과"할 수 있는 더 많은 수입니다.

- 대기 시간은 콘텐츠가 서버 또는 서비스에서 장치로 전송되는 데 걸리는 시간으로, 밀리초 단위로 측정됩니다. 속도가 빨라집니다. 대기 시간은 낮은 대역폭, 연결 부족 또는 전송 시간을 비롯한 다양한 요인으로 인해 발생할 수 있습니다.

 **일반적인 문제** 대역폭 및 대기 시간 외에 다른 문제는 네트워크 성능에 영향을 주며 예측할 수 없는 경우가 종종 있습니다. 네트워크 성능은 하루 중 시간 또는 실제 위치에 따라 변동될 수 있습니다. 자연 재해나 주요 공용 이벤트와 같은 특정 이벤트가 발생하여 인터넷 사용이 막히는 경우 네트워크가 막히게 될 수 있습니다. 로드되는 페이지의 크기와 복잡도와 전송되는 파일의 수와 크기는 성능에 직접적인 부담을 줄 수 있습니다. WiFi 연결은 일시적으로 저하될 수 있습니다. 예를 들어 모든 사람이 동시에 트윗을 하게 요청하여 수천 개의 대규모 회의 모임을 폴링합니다. 
  
 **위성 네트워크 고려 사항** 위성 네트워크는 배방 국가, 유람선 또는 원격 과학 영역과 같은 위성 네트워크가 실현할 수 없는 경우 유용합니다. 이러한 네트워크는 적도 위에서 22,000마일의 지리적 비동기 궤도에 있는 위성을 사용합니다. 그러나 전송은 실제로 약 90,000마일을 이동하기 때문에 위성 네트워크의 대기 시간(500ms 이상)이 지구대 네트워크(20~50ms)보다 느립니다. 최상의 조건에서는 이 대기 시간이 눈에 띄지 않을 수 있지만 대용량 파일, 스트리밍 비디오 및 게임 플레이의 경우 이 대기 시간을 알 수 없습니다. 또 다른 문제는 위성 전송을 일시적으로 중단할 수 있는 흐린 날씨(예: 번개, 눈바운드 등)가 흐린 것일 수 있는 "비가 흐림"입니다.
  
## <a name="are-you-sure-its-the-network"></a>네트워크인가요?

성능 문제가 발생할 때마다 먼저 장치가 문제의 근본 원인이 아닌지 확인합니다. 크게 개선할 수 있는 두 가지 작업을 할 수 있습니다.
  
- 장치가 잘 실행되고 있으며 컴퓨터에 맬웨어가 없는지 확인합니다.

- 가능하면 메모리를 더 구입합니다. 메모리를 추가하는 것은 디바이스의 성능을 개선하는 가장 간단하고 가장 효과적인 방법입니다. 대용량 파일 및 비디오로 작업할 때 특히 유용합니다.

자세한 내용은 [Windows 10에서](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) PC 성능을 개선하기 위한 Windows 성능 및 유지 관리 및 [팁을 참조하세요.](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance)

## <a name="best-practices-for-using-your-browser"></a>브라우저 사용에 대한 모범 사례

브라우저는 Office 365에 대한 게이트웨이이기 때문에 특히 페이지를 로드하는 데 걸리는 시간 및 Office 365 서비스로 왕복하는 자주 성능에 영향을 줄 수 있습니다.
  
 **일반적으로 브라우저**
  
다음은 일반적으로 브라우저에 대한 몇 가지 제안 사항입니다.
  
- 성능에 영향을 줄 수 있는 브라우저 추가 기능 또는 실제로 필요하지 않은 브라우저 추가 기능을 사용하지 않도록 설정하세요.

- 임시 인터넷 파일의 캐시 크기를 늘입니다.

- 직장 또는 학교 계정에 로그인한 후 하루 동안 브라우저 창을 열어 두십시오. 다시 로그인하지 않고 다른 탭과 창을 열 수 있습니다. 다른 계정에 로그인해야 하는 경우 개인 검색을 사용하세요. 

- 각 페이지가 다운로드된 후 열리면 탭을 사용하여 열어 두십시오. 탭 간에 쉽게 탐색하고 나중에 페이지를 사용할 수 있습니다. 해당 페이지에 최신 데이터가 필요한 경우만 페이지를 새로 고침합니다.

- 페이지를 여는 데 시간이 너무 오래 지난 경우 페이지 다운로드를 중지하고(ESC 누르기) 페이지를 새로 고치십시오(F5 누르기). 

-  가능한 경우 Office 365 왕복을 줄입니다. 예를 들어 목록이나 라이브러리를 통해 이동하는 대신 검색을 사용하여 큰 라이브러리에서 파일을 찾고 목록에서 필터링을 사용하여 원하는 결과를 바로 얻을 수 있습니다. 또는 페이지 로드 시간을 최소화하는 보기를 만들 수 있습니다. 자세한 내용은 [Office 365에서](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)큰 목록 및 라이브러리 관리를 참조하세요.

- 비디오 성능이 좋지 않은 경우 비디오를 다운로드하여 디바이스에서 시청할 수 있습니다. 다운로드 링크를 사용할 수 있습니다. 또는 비디오 링크를 마우스 오른쪽 단추로 클릭하고 다른 것으로 대상 저장을 **선택할 수 있습니다.**

 **브라우저별**
  
다음은 특정 브라우저에 대한 몇 가지 제안 사항입니다.
  
- **Internet Explorer** 이전 Internet Explorer 성능을 크게 향상하기 위해 버전 11 이상으로 업그레이드합니다. 자세한 내용은 에 대한 문제 [해결 Internet Explorer.](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)

- **FireFox** 자세한 내용은 [Firefox가 느리거나 작동이 중지된 경우를 참조하세요.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)

- **Safari** 자세한 내용은 [Apple - Safari를 참조하세요.](https://www.apple.com/safari/)

- **Chrome** 자세한 내용은 [Chrome 도움말을 참조하세요.](https://support.google.com/chrome/?hl=en)
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Outlook 및 웹 에지 사용에 대한 모범 Outlook Web App

전자 메일 읽기, 쓰기 및 구성은 모든 사람이 매일 하는 중요한 부분입니다. Outlook과 OWA(Outlook Web App)는 모두 오프라인 지원을 제공합니다. 스마트폰에서 전자 메일 앱을 사용하는 것은 또 다른 유용한 대안입니다. 요구에 가장 적합한 다음 옵션을 사용하세요.
  
- 이전 버전보다 성능을 크게 개선하기 위해 최신 버전의 Outlook으로 업그레이드합니다. 

-  Outlook Web App OWA가 다음에 Office 365에 연결할 수 있을 때 업로드되는 오프라인 메시지, 연락처 및 일정 이벤트를 만들 수 있습니다. 오프라인 모드에서 OWA 설정 및 사용에 대한 자세한 내용은 오프라인에서 OWA Outlook Web App [참조하세요.](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)

- Outlook에서는 가능한 경우 자동으로 연결되는 캐시 모드에서 작업할 수 있습니다. Outlook에서 전체 사서함을 다운로드하거나 사서함의 일부만 다운로드할 수 있습니다. 자세한 내용은 Outlook에서 캐시된 [Exchange](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) 모드 켜기 및 [오프라인으로 작업 기능을 참조하십시오.](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlook에서는 오프라인 모드도 제공합니다. 이 기능을 사용하려면 먼저 계정의 정보를 컴퓨터로 복사할 수 있도록 캐시 모드를 설정해야 합니다. 오프라인 모드에서 Outlook은 보내기 및 받기 설정을 사용하여 연결하거나 수동으로 온라인으로 작동하게 설정하려고 시도합니다. 자세한 내용은 오프라인으로 작업하여 데이터 연결 [](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)요금이 부과되지 않도록 [하고,](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)오프라인으로 작업할 때 보내기 및 받기 설정을 변경하고, 오프라인에서 온라인으로 전환을 [참조하세요.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- 스마트폰이 있는 경우 휴대폰 통신사 네트워크를 통해 전자 메일 및 일정을 선출하는 데 사용할 수 있습니다.

> [!NOTE]
> 다음은 Outlook 또는 OWA를 사용하는 경우에 대한 몇 가지 지침입니다. 디스크 공간이 장치에 문제가 없는 경우 Outlook에는 전체 기능 집합이 있으며 가장 잘 작동할 수 있습니다. 디스크 공간이 장치에서 문제가 있는 경우 기능의 하위 집합이 있지만 온라인 상황에서도 가장 잘 작동하는 OWA를 사용하는 것이 가장 까다로울 수 있습니다. 물론 함께 잘 작동하기 때문에 둘 중 하나를 사용할 수 있습니다.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>비즈니스용 OneDrive 사용 모범 사례

비즈니스용 OneDrive는 온라인 및 오프라인에서 파일을 사용할 수 있도록 설계된 것입니다. 설정하면 변경 내용을 설정할 때마다 변경 내용이 자동으로 안정적으로 동기화됩니다. 네트워크 속도가 느리면 오프라인 버전의 파일을 사용할 수 있습니다.
  
비즈니스용 OneDrive 동기화 앱은 SharePoint Online 및 Office 365 Business [](https://support.microsoft.com/kb/2903984) 구독과 함께 제공되거나 비즈니스용 OneDrive 동기화 앱을 무료로 다운로드할 수 있습니다. 이 앱은 탐색기에서  열기 또는 업로드 명령을 사용하는 것보다 **속도가** 빠릅니다. 자세한 내용은 [Office 365에서 비즈니스용 OneDrive](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)파일을 동기화하는 컴퓨터 설정을 참조하세요.
  
비즈니스용 OneDrive 동기화 앱을 사용하는 방법에 대한 몇 가지 추가 지침은 다음과 같습니다.
  
- 큰 라이브러리를 처음 동기화하는 경우, 새 시간(예: 하야)에 동기화를 시작하십시오.

- 비즈니스용 [OneDrive](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) 앱 기능을 사용하여 라이브러리 동기화 중지를 사용하여 업데이트 동기화를 일시적으로 중지할 수 있습니다. 그러나 이 기능은 한 시간에 몇 시간과 같이 짧은 기간 동안 사용하여 많은 수의 업데이트를 대기하지 않도록 방지하고 여러 사용자가 동일한 문서에서 작업하는 경우 병합 충돌 위험을 최소화할 수 있습니다.
  
## <a name="best-practices-for-using-onenote"></a>OneNote 사용에 대한 모범 사례

모든 SharePoint 팀 사이트에는 OneNote 전자 필기장이 기본 제공되어 있으며 직접 쉽게 만들 수 있습니다. OneNote는 작업을 수행하는 데 매일 필요한 시기적정한 정보를 수집하는 좋은 방법입니다. 예를 들어 많은 팀에서 주간 모임, 프로젝트 메모, 아이디어, 계획 및 상황 보고서의 컬렉션 지점으로 OneNote를 사용하게 됩니다. 페이지, 섹션 및 탭을 사용하여 이 다른 정보를 깔끔하게 구성할 수 있습니다.
  
OneNote의 매력은 데스크톱, 노트북, 태블릿 또는 스마트폰 등 거의 모든 장치에서 콘텐츠에 액세스할 수 있습니다. 또한 OneNote에서 이 작업을 자동으로 실행하기 때문에 저장 또는 동기화에 대해 걱정할 필요가 없습니다.
  
자세한 내용은 [Microsoft OneNote를 참조하세요.](https://office.microsoft.com/onenote)

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>비즈니스용 Skype 및 Lync Online 사용에 대한 모범 사례

다음은 네트워크 속도가 느리면 비즈니스용 Skype 또는 Lync Online을 사용하는 일반적인 지침입니다.

- 저속 네트워크에서 잘 작동하기 때문에 인스턴트 메시징을 사용할 수 있습니다.

- VPN(가상 사설망) 또는 RAS(원격 액세스 서비스) 연결을 통해 전화 통화를 하지 않도록 합니다.

- 오디오 장치가 승인된지 확인합니다. 자세한 내용은 [Microsoft Lync에](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones)대해 자격을 갖춘 전화 및 장치를 참조하세요.

- 온라인 프레젠테이션에서 PowerPoint를 사용하는 경우 슬라이드의 크기와 복잡성을 줄입니다. 자세한 내용은 프레젠테이션의 성능을 개선하기 위한 [팁을 참조하십시오.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- 비디오 성능은 네트워크 성능에 따라 매우 달라집니다. 네트워크 속도가 느린 경우 비디오를 사용하지 않도록 합니다.

자세한 내용은 [Lync Online에서](https://support.microsoft.com/kb/2386655)오디오 또는 비디오 품질이 나쁨을 참조하거나 비즈니스용 Skype에서 연결 문제를 해결하는 [방법을 참조하세요.](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)
  
## <a name="best-practices-for-using-sharepoint-lists"></a>SharePoint 목록 사용 모범 사례

오프라인에서 목록 데이터를 "스크러브", 분석 또는 보고로 작업하는 것은 느린 네트워크의 영향을 최소화하는 좋은 방법입니다. Microsoft Access 2019 및 Microsoft Access 2016에서 대부분의 목록을 읽고 쓸 수 있습니다. Excel 테이블과 목록 간에 단방형 데이터 연결을 만드는 Excel 테이블로 목록을 내보낼 수 있습니다. [SharePoint 목록에 연결된](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)테이블을 사용하여 오프라인으로 작업하는 방법을 확인합니다.
  
자세한 내용은 [Office 365의](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)큰 목록 및 라이브러리 관리에서 "큰 목록 관리에 대한 자세한 정보" 섹션을 참조하세요.
  
## <a name="best-practices-for-customizing-web-pages"></a>웹 페이지 사용자 지정을 위한 모범 사례

웹 페이지를 사용자 지정할 때 페이지 성능이 잘못될 수 있습니다. 페이지의 복잡도 및 크기, 추가되는 웹 파트 수, 처음에 표시되는 목록 또는 라이브러리 항목 수, 페이지를 코딩하는 방법 등 다양한 요인이 영향을 줄 수 있습니다.
  
자세한 내용은 SharePoint Online 성능 [조정을 참조하세요.](tune-sharepoint-online-performance.md)
  
## <a name="best-practices-for-using-project-online"></a>Project Online 사용에 대한 모범 사례

다음 지침은 네트워크 성능을 개선하는 데 도움이 될 수 있습니다.
  
- Project Online 및 SharePoint Online에는 동기화가 필요하며 이 동기화에는 시간이 오래 걸릴 수 있습니다. 프로젝트 팀의 회전율이 낮은 경우 프로젝트 사이트 동기화를 사용하지 않도록 설정하여 프로젝트 게시 및 프로젝트 세부 정보 페이지 성능을 개선합니다. 실제로 시스템을 사용하는 데 필요한 리소스 그룹으로 Active Directory 동기화를 제한하고 대규모 그룹을 동기화한 후 잠재적인 사용 권한 문제를 모니터링합니다.

- 조직에서 프로젝트 사이트를 사용하는 경우 자동으로 만들지 않고 필요한 경우 만들어야 합니다. 이렇게 하여 첫 번째 게시 환경의 속도를 향상하고 불필요한 사이트 및 콘텐츠를 만들지 않습니다.

- PDP(프로젝트 세부 정보 페이지)는 전체 프로젝트의 재계산을 트리거하고 성능 집약적인 작업이 될 수 있는 워크플로 작업을 시작해야 합니다. 동일한 PDP에서 두 업데이트 프로세스가 동시에 트리거되지 않도록 일정 필드(시작 날짜, 완료 날짜, 상태 날짜 및 현재 날짜)와 예약되지 않은 필드(프로젝트 이름, 설명 및 소유자)를 업데이트하지 않도록 합니다.

- 각 PDP에 웹 파트 사용자 정의 필드의 수를 줄입니다. 부하를 개선하고 시간을 절약하기 위해 업데이트해야 하는 유일한 필드가 있는 전용 PDP를 만드시다.

- 보고에 OData를 사용하는 경우 서버 쪽 필터링을 사용하여 런타임에 쿼리하는 데이터의 양을 제한합니다.

자세한 내용은 Project Online 성능 [조정을 참조하세요.](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)
  
## <a name="whats-the-best-way-to-report-problems"></a>문제를 보고하는 가장 좋은 방법은 무엇입니까?

Microsoft는 네트워크를 모니터링하고, 대역폭 및 대기 시간을 측정하고, 페이지 로드 시간을 단축하고, 디스크 I/O를 줄이고, 최소한의 다운로드 전략을 사용하기 위해 페이지를 다시 디자인하고, 데이터 센터에 하드웨어를 추가하고, 데이터 센터를 더 추가하여 Office 365의 전반적인 성능을 지속적으로 개선합니다. 현재 상태 및 보고 문제를 확인 하는 방법에 대 한 자세한 내용은 [Office 365](view-service-health.md)서비스 상태를 확인 하는 방법을 참조 합니다.
  
## <a name="see-also"></a>참고 항목

[Office 365의 네트워크 계획 및 성능 조정](network-planning-and-performance.md)
  
[Office 365 네트워크 연결 원칙](microsoft-365-network-connectivity-principles.md)
  
[Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Office 365 끝점 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
