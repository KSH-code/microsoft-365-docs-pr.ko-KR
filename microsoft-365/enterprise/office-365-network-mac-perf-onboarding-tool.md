---
title: Microsoft 365 네트워크 연결 테스트 도구(미리 보기)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 네트워크 연결 테스트 도구(미리 보기)
ms.openlocfilehash: b29eb29cd390c3febd0992e942cf8ab39f652fb2
ms.sourcegitcommit: 26c2f01d6f88f6c288b04f9f08062d68dd1e67e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/04/2020
ms.locfileid: "49569990"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Microsoft 365 네트워크 연결 테스트 도구(미리 보기)

Microsoft 365 네트워크 연결 테스트 도구는 <https://connectivity.office.com> 에 있습니다. 이 도구는 상태 | 아래에 있는 Microsoft 365 관리 센터에서 사용할 수 있는 네트워크 평가 및 네트워크 정보의 부재 **중 도구입니다. 연결 메뉴**

> [!IMPORTANT]
> 모든 테스트 보고서를 관리자와 공유하고 로그인하는 동안 테넌트에 업로드하기 때문에 Microsoft 365 테넌트에 로그인하는 것이 중요합니다.

![연결 테스트 도구](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>네트워크 연결 테스트 도구는 WW Commercial 및 Germany의 테넌트는 지원하지만 GCC Moderate, GCC High, DoD 또는 중국은 지원하지 않습니다.

Microsoft 365 관리 센터의 네트워크 인사이트는 매일 집계되는 Microsoft 365 테넌트에 대한 정기적인 제품 내 측정을 기반으로 합니다. 이에 비해 Microsoft 365 네트워크 연결 테스트의 네트워크 인사이트는 도구에서 한 번씩 로컬로 실행됩니다. 제품에서 수행될 수 있는 테스트는 제한되어 있으며, 사용자에게 로컬로 테스트를 실행하면 더 많은 데이터를 수집할 수 있습니다. 그런 다음 Microsoft 365 관리 센터의 네트워크 정보를 통해 특정 사무실 위치에서 Microsoft 365를 사용하기 위한 네트워킹 문제가 있는 것으로 나타났습니다. Microsoft 365 연결 테스트는 권장되는 네트워크 성능 개선 작업으로 이어지는 해당 문제의 근본 원인을 파악하는 데 도움이 될 수 있습니다.

이러한 기능을 함께 사용하여 Microsoft 365 관리 센터의 각 사무실 위치에 대해 네트워킹 품질 상태를 평가할 수 있으며, Microsoft 365 연결 테스트를 기반으로 테스트를 배포한 후 보다 구체적인 정보를 확인할 수 있습니다.

>[!IMPORTANT]
>Microsoft 365 관리 센터의 네트워크 정보, 성능 권장 사항 및 평가는 현재 미리 보기 상태입니다. 기능 미리 보기 프로그램에 등록된 Microsoft 365 테넌트에만 사용할 수 있습니다.

## <a name="what-happens-at-each-test-step"></a>각 테스트 단계에서 발생하는 결과

### <a name="office-location-identification"></a>Office 위치 식별

테스트 실행 단추를 클릭하면 실행 중인 테스트 페이지가 표시되고 사무실 위치가 식별됩니다. 도시, 시 및 국가별로 위치를 입력하거나 웹 브라우저에서 검색할 수 있습니다. 검색한 경우 웹 브라우저에서 위도 및 세로를 요청하고 사용하기 전에 정확도를 300m에서 300m로 제한합니다. 네트워크 성능을 위해 건물보다 위치를 더 정확하게 식별할 필요는 없습니다. 

### <a name="javascript-tests"></a>JavaScript 테스트

사무실 위치 식별 후 JavaScript에서 TCP 대기 시간 테스트를 실행하고 사용 중 및 권장되는 Office 365 서비스 프런트 도어 서버에 대한 데이터를 서비스에서 요청합니다. 이 작업을 완료하면 지도 및 세부 정보 탭에 표시하며, 이 탭에서는 다음 단계 전에 해당 정보를 볼 수 있습니다.

### <a name="download-the-advanced-tests-client-application"></a>고급 테스트 클라이언트 응용 프로그램 다운로드

그런 다음 고급 테스트 클라이언트 응용 프로그램 다운로드를 시작합니다. 사용자가 클라이언트 응용 프로그램을 시작해야 하며 .NET Core도 설치되어 있어야 합니다.

Microsoft 365 네트워크 연결 테스트에는 두 부분으로 구성됩니다. 고급 네트워크 연결 테스트를 실행하고 웹 사이트 및 다운로드 가능한 <https://connectivity.office.com> Windows 클라이언트 응용 프로그램입니다. 대부분의 테스트에서는 응용 프로그램을 실행해야 합니다. 실행 시 결과를 웹 페이지에 다시 채우게 됩니다.

웹 브라우저 테스트가 완료되면 웹 사이트에서 고급 클라이언트 테스트 응용 프로그램을 다운로드하라는 메시지가 표시됩니다. 메시지가 표시될 때 파일을 열고 실행합니다.

![고급 테스트 클라이언트 응용 프로그램](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>고급 테스트 클라이언트 응용 프로그램 시작

클라이언트 응용 프로그램이 시작되면 웹 페이지가 업데이트되어 이를 표시하고 테스트 데이터를 웹 페이지로 수신하기 시작합니다. 새 데이터를 수신할 때마다 업데이트하며 데이터가 도착하면 검토할 수 있습니다.

### <a name="advanced-tests-completed-and-test-report-upload"></a>고급 테스트 완료 및 테스트 보고서 업로드

테스트가 완료되면 고급 테스트 클라이언트가 이를 나타내고 사용자가 테스트 보고서에 로그인한 경우 고객 테넌트에 업로드됩니다.

## <a name="sharing-your-test-report"></a>테스트 보고서 공유

테스트 보고서에는 Office 365 계정에 로그인해야 합니다. 관리자가 테스트 보고서를 공유하는 방법을 선택합니다.

### <a name="sharing-your-report-with-your-administrator"></a>관리자와 보고서 공유

로그인한 동안의 모든 테스트 보고서는 관리자와 공유됩니다.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Microsoft 계정 팀, 지원 또는 기타 직원과 공유

개인 식별을 제외한 테스트 보고서는 Microsoft 직원과 공유됩니다. This is enabled by default and can be disabled by your administrator in the **Health |** Microsoft 365 관리 센터의 네트워크 연결 페이지

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>동일한 Office 365 테넌트에 로그인한 다른 사용자와 공유

보고서를 공유할 사용자를 선택할 수 있으며 이 설정은 기본적으로 사용하도록 설정됩니다. 관리자가 사용하지 않도록 설정할 수도 있습니다.

![사용자와 테스트 결과에 대한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>ReportID 링크를 사용하는 모든 사람과 공유

ReportID 링크에 대한 액세스를 제공하여 모든 사용자와 테스트 보고서를 공유할 수 있습니다. 이렇게하면 로그인하지 않고 테스트 보고서를 가져올 수 있도록 다른 사람에게 보낼 수 있는 URL이 생성됩니다. 이 설정은 기본적으로 사용하지 않도록 설정되어 있으며 관리자가 사용하도록 설정해야 합니다.

![테스트 결과에 대한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>네트워크 연결 테스트 결과

결과는 요약 및 **Summary** 세부 정보 **탭에** 표시됩니다. 요약 탭에는 검색된 네트워크 경계의 지도와 네트워크 평가를 근처의 다른 Office 365 고객과 비교한 것이 표시됩니다. 또한 테스트 보고서를 공유할 수 있습니다. 요약 결과 보기의 모양은 다음과 같아야 합니다.

![네트워크 연결 테스트 도구 요약 결과](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

다음은 도구에서 보여 주는 세부 정보 탭 출력의 예입니다. 결과가 임계값과 비교된 경우 세부 정보 탭에 녹색 원 확인 표시가 표시됩니다. 결과가 네트워크 정보를 나타내는 임계값을 초과하는 경우 빨간색 삼각형 느낌표가 표시됩니다. 다음 섹션에서는 각 세부 정보 탭 결과 행에 대해 설명하고 네트워크 인사이트에 사용되는 임계값에 대해 설명합니다.

![네트워크 연결 테스트 도구 예제 테스트 결과](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>위치 정보

이 섹션에는 사용자 위치와 관련된 테스트 결과가 표시됩니다.

#### <a name="your-location"></a>사용자 위치

사용자 위치가 사용자 웹 브라우저에서 검색되거나 사용자가 선택한 경우 입력할 수 있습니다. 엔터프라이즈 네트워크 경계의 특정 부분에 대한 네트워크 거리를 식별하는 데 사용됩니다. 이 위치 검색의 도시와 다른 네트워크 지점까지의 거리만 보고서에 저장됩니다.

사용자 사무실 위치가 지도 보기에 표시됩니다.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>네트워크 유선 위치(네트워크가 ISP에 연결되는 위치)

서버 쪽에서 네트워크 전송 IP 주소를 식별합니다. 위치 데이터베이스는 네트워크 이동의 대략적인 위치를 검색하는 데 사용됩니다. 이러한 데이터베이스는 일반적으로 IP 주소의 약 90%의 정확성을 가집니다. 네트워크에서 검색한 위치가 정확하지 않은 경우 이 테스트에서 잘못된 결과가 표시됩니다. 특정 IP 주소에 대해 이 오류가 발생하는지 확인을 위해 공개적으로 액세스할 수 있는 네트워크 IP 주소 위치 웹 사이트를 사용하여 실제 위치와 비교할 수 있습니다.

#### <a name="your-distance-from-the-network-egress-location"></a>네트워크 시작 위치로부터의 거리

해당 위치에서 사무실 위치까지의 거리를 결정할 수 있습니다. 이는 거리가 **500마일(800킬로미터)보다** 크면 TCP 대기 시간이 25ms 이상 증가하고 사용자 경험에 영향을 줄 수 있는 네트워크 정보로 표시됩니다.

네트워크 시작 위치는 지도 보기에 표시되고 엔터프라이즈 WAN 내부의 네트워크 백HAUL을 나타내는 사용자 사무실 위치에 연결됩니다.

Microsoft 365 네트워크 연결을 위해 사용자 사무실 위치에서 인터넷으로의 로컬 및 직접 네트워크 연결을 구현하는 것이 좋습니다. 로컬 및 직접 연결에 대한 개선은 이 네트워크 정보를 해결할 수 있는 가장 좋은 방법입니다.

#### <a name="proxy-server-information"></a>프록시 서버 정보

로컬 컴퓨터로 구성된 프록시 서버를 식별합니다. 네트워크 경로에서 최적화 범주 Microsoft 365 네트워크 트래픽을 위해 이러한 구성이 구성되어 있는지 확인합니다. 사용자 사무실 위치에서 프록시 서버까지의 거리를 식별합니다. 거리는 ICMP ping에서 먼저 테스트하고 TCP ping으로 테스트에 실패하면 테스트한 다음 실패하면 IP 주소 위치 데이터베이스에서 프록시 서버 IP 주소를 검색합니다. 프록시 서버가 사용자 사무실 위치에서 500킬로미터(800킬로미터)를 멀어도 네트워크 정보를 제공합니다. **500 miles**

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>조직에 연결하는 데 사용하는 VPN(가상 사설망)

VPN을 사용하여 Office 365에 연결하는지 검색합니다. VPN이 없는 경우 또는 Office 365에 대한 권장 분할 터널 구성이 있는 VPN이 있는 경우 통과 결과가 표시 됩니다.

#### <a name="vpn-split-tunnel"></a>VPN 분할 터널

Exchange Online, SharePoint Online 및 Microsoft Teams에 대한 각 최적화 범주 경로는 VPN에서 터널링되어 있지 않은지 테스트됩니다. 분할된 워크로드는 VPN을 완전히 방지합니다. 터널링된 워크로드는 모두 VPN을 통해 전송됩니다. 선택적 터널링 워크로드에는 VPN을 통해 전송된 일부 경로와 분할된 경로가 있습니다. 전달 결과는 모든 워크로드가 분할되거나 선택적으로 터널링된 경우를 보여 주게 됩니다.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>더 나은 성능을 제공한 대도시 지역 고객

Exchange Online 서비스 프런트 도어에 대한 사용자 사무실 위치의 네트워크 TCP 대기 시간은 동일한 대도시 지역에 있는 다른 Microsoft 365 고객과 비교됩니다. 같은 대도시 지역에 있는 고객의 10% 이상이 더 나은 성능을 얻을 경우 네트워크 인사이트가 표시됩니다. 즉, 사용자가 Microsoft 365 사용자 인터페이스에서 더 나은 성능을 하게 됩니다.

이 네트워크 인사이트는 도시에 있는 모든 사용자가 동일한 통신 인프라와 인터넷 회로 및 Microsoft 네트워크와 동일한 근접성에 액세스할 수 있도록 기초로 생성됩니다.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>네트워크에서 DNS 요청을 하는 데 들이는 시간

테스트를 실행한 클라이언트 머신에 구성된 DNS 서버가 표시 됩니다. DNS 재동기 확인 서버일 수 있습니다. 그러나 이는 확연한 일입니다. DNS 결과를 캐시하고 캐시되지 않은 DNS 요청을 다른 DNS 서버로 전달하는 DNS 전달자 서버일 가능성이 확연합니다.

이 정보는 정보에만 제공된 것이고 네트워크 인사이트에 영향을 주지 않습니다.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>DNS 재발 확인자까지의 거리 및/또는 시간

사용 중 DNS 재발 확인은 특정 DNS 요청을 한 다음 DNS 이름 서버에 동일한 요청을 받은 IP 주소를 요청하여 식별됩니다. 이 IP 주소는 DNS 재발방지 확인자로, IP 주소 위치 데이터베이스에서 검색하여 위치를 찾을 수 있습니다. 그러면 사용자 사무실 위치에서 DNS 재구성 확인 서버 위치까지의 거리가 계산됩니다. 이는 거리가 **500마일(800킬로미터)보다** 큰 경우 네트워크 정보로 표시됩니다.

네트워크에서 검색한 위치가 IP 주소가 정확하지 않을 수 있으며 이로 인해 이 테스트에서 잘못된 결과가 발생할 수 있습니다. 특정 IP 주소에 대해 이 오류가 발생하는지 확인을 위해 공개적으로 액세스할 수 있는 네트워크 IP 주소 위치 웹 사이트를 사용할 수 있습니다.

이 네트워크 인사이트는 Exchange Online 서비스 프런트 도어 선택에 특히 영향을 미치게 됩니다. 이 인사이트를 해결하기 위해 로컬 및 직접 네트워크 발신은 선행 요구해야 합니다. 그런 다음 DNS 재귀 확인자는 해당 네트워크 발신에 가깝게 위치해야 합니다.

### <a name="exchange-online"></a>Exchange Online

이 섹션에는 Exchange Online과 관련된 테스트 결과가 표시됩니다.

#### <a name="exchange-service-front-door-location"></a>Exchange 서비스 프런트 도어 위치

사용 중 Exchange 서비스 프런트 도어는 Outlook에서 이 기능을 하는 방법과 동일한 방식으로 식별됩니다. 사용자 위치에서 서비스로의 네트워크 TCP 대기 시간을 측정합니다. TCP 대기 시간이 표시될 때 사용 중인 Exchange 서비스 프런트 도어가 현재 위치에 대한 최상의 서비스 프런트 도어 목록과 비교됩니다. 이는 최상의 Exchange 서비스 프런트 도어 중 하나를 사용하지 않는 경우 네트워크 정보로 표시됩니다.

최상의 Exchange 서비스 프런트 도어 중 하나를 사용하지 않는 경우 로컬 및 직접 네트워크 유출을 권장하는 경우 회사 네트워크가 들어오기 전에 네트워크 백힐로 인해 발생할 수 있습니다. 또한 원격 DNS 재귀 확인 서버 사용으로 인해 발생할 수 있습니다. 이 경우 DNS 재귀 확인 서버와 네트워크 전송을 맞추는 것이 좋습니다.

Exchange 서비스 프런트 도어에 대한 TCP 대기 시간(ms)의 잠재적 향상을 계산합니다. 테스트된 사용자 사무실 위치 네트워크 대기 시간을 보고 현재 위치에서 닫기 Exchange 서비스 프런트 도어로 네트워크 대기 시간을 뺄 수 있습니다. 이 차이는 개선할 수 있는 기회를 나타 내는 것입니다.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>위치에 가장 적합한 Exchange 서비스 프런트 도어

여기에는 해당 위치의 도시당 최상의 Exchange 서비스 프런트 도어 위치가 나열됩니다.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>클라이언트 DNS에 기록된 서비스 프런트 도어

그러면 연결한 Exchange 서비스 프런트 도어 서버의 DNS 이름과 IP 주소가 표시됩니다. 정보만 제공하며 연결된 네트워크 인사이트가 없습니다.

### <a name="sharepoint-online"></a>SharePoint Online

이 섹션에는 SharePoint Online 및 OneDrive와 관련된 테스트 결과가 표시됩니다.

#### <a name="the-service-front-door-location"></a>서비스 프런트 도어 위치

사용 중 SharePoint 서비스 프런트 도어는 OneDrive 클라이언트가 실행하고 사용자 사무실 위치에서 네트워크 TCP 대기 시간을 측정하는 방식으로 식별됩니다.

#### <a name="download-speed"></a>다운로드 속도

SharePoint 서비스 프런트 도어에서 15Mb 파일의 다운로드 속도를 측정합니다. 결과는 SharePoint 또는 OneDrive에서 1초에 다운로드할 수 있는 크기( 메가바이트)를 나타내기 위해 초당 메가바이트(기가바이트)로 **표시됩니다.** 이 숫자는 최소 회로 대역폭의 10분의 1(초당 메가비트)과 비슷해야 합니다. 예를 들어 인터넷 연결이 100mbps인 경우 초당 10MB(10MBps)가 예상될 수 있습니다.

#### <a name="buffer-bloat"></a>버퍼 블로트

15Mb를 다운로드하는 동안 SharePoint 서비스 프런트 도어에 대한 TCP 대기 시간을 측정합니다. 이는 부하가 낮은 대기 시간으로, 부하가 없는 경우 대기 시간과 비교됩니다. 부하가 낮은 경우 대기 시간이 증가하는 것은 소비자 네트워크 장치 버퍼가 로드(또는 더 이상 사용되지 않습니다)에 기인하는 경우가 자주 있습니다. 네트워크 인사이트가 1,000개 이상인 경우 표시됩니다.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>클라이언트 DNS에 기록된 서비스 프런트 도어

이 예에서는 지시한 SharePoint 서비스 프런트 도어 서버의 DNS 이름 및 IP 주소를 보여 주며, 정보만 제공하며 연결된 네트워크 인사이트가 없습니다.

### <a name="microsoft-teams"></a>Microsoft Teams

이 섹션에는 Microsoft Teams와 관련된 테스트 결과가 표시됩니다.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>미디어 연결(오디오, 비디오 및 응용 프로그램 공유)

이 테스트에서는 Microsoft Teams 서비스 프런트 도어에 대한 UDP 연결을 테스트합니다. 차단된 경우 Microsoft Teams는 여전히 TCP를 사용하여 작업할 수 있지만 오디오 및 비디오에는 장애가 있습니다. 비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능에서 Microsoft Teams에도 적용되는 이러한 UDP 네트워크 측정에 대해 자세히 [읽어 읽습니다.](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>패킷 손실

클라이언트에서 Microsoft Teams 서비스 프런트 도어로의 10초 테스트 오디오 통화로 측정된 UDP 패킷 손실을 보여 주며, 이 수준은 통과에 **대해 1.00%** 보다 낮아야 합니다.

#### <a name="latency"></a>대기 시간

측정된 UDP 대기 시간을 보여 주며, **100ms보다 낮아야 합니다.**

#### <a name="jitter"></a>지터

측정된 UDP 지터를 보여 주며, **30ms보다 낮아야 합니다.**

#### <a name="connectivity"></a>연결

사용자 사무실 위치에서 필요한 모든 Microsoft 365 네트워크 끝점으로의 HTTP 연결을 테스트합니다. 다음에 [https://aka.ms/o365ip](https://aka.ms/o365ip) 게시됩니다. 연결할 수 없는 필수 네트워크 끝점에 대한 네트워크 인사이트가 표시됩니다.

프록시 서버, 방화벽 또는 엔터프라이즈 네트워크 경계의 다른 네트워크 보안 장치에 의해 연결이 차단될 수 있습니다. HTTP 요청을 통해 TCP 포트 80에 대한 연결을 테스트하고 HTTPS 요청을 통해 TCP 포트 443에 대한 연결을 테스트합니다. 응답이 없는 경우 FQDN이 오류로 표시됩니다. HTTP 응답 코드 407이 있는 경우 FQDN이 오류로 표시됩니다. HTTP 응답 코드 403이 있는 경우 응답의 Server 특성을 확인하고 프록시 서버로 나타나는 경우 이를 오류로 표시됩니다. Windows 명령줄 도구 모음을 사용하여 수행하는 테스트를 시뮬레이트할 수 curl.exe.

최적화 또는 허용 범주에 정의된 각 필수 Microsoft 365 네트워크 끝점에서 SSL 인증서를 [https://aka.ms/o365ip](https://aka.ms/o365ip) 테스트합니다. 테스트에서 Microsoft SSL 인증서를 찾지 못하면 연결된 암호화된 네트워크가 중간 네트워크 장치에 의해 가로채야 합니다. 가로채는 암호화된 네트워크 끝점에 네트워크 인사이트가 표시됩니다.

Microsoft에서 제공하지 않는 SSL 인증서가 발견되는 경우 테스트에 대한 FQDN과 사용 중 SSL 인증서 소유자를 보여 주게 됩니다. 이 SSL 인증서 소유자는 프록시 서버 공급업체일 수도, 엔터프라이즈 자체 서명된 인증서일 수도 있습니다.

#### <a name="network-path"></a>네트워크 경로

이 섹션에서는 Exchange Online 서비스 프런트 도어, SharePoint Online 서비스 프런트 도어 및 Microsoft Teams 서비스 프런트 도어로의 ICMP 추적 출구 결과를 보여 제공합니다. 정보만 제공하며 연결된 네트워크 인사이트가 없습니다. 세 개의 추적이 제공됩니다. 이 outlook.office365.com, _outlook.office365.com_ 고객 SharePoint 프런트 엔드 또는 microsoft.sharepoint.com(제공되지 않은 _microsoft.sharepoint.com_ 경우) 및 해당 서비스로의 추적 _world.tr.teams.microsoft.com._

## <a name="connectivity-reports"></a>연결 보고서

로그인하면 실행한 이전 보고서를 검토할 수 있습니다. 목록에서 공유하거나 삭제할 수도 있습니다.

![보고서](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>네트워크 상태

이는 Microsoft 365 고객에게 영향을 줄 수 있는 Microsoft의 전역 네트워크에서 중요한 상태 문제를 보여 주며,

![네트워크 상태](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>FAQ

다음은 자주 묻는 몇 가지 질문에 대한 답변입니다.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>이 도구가 Microsoft에서 릴리스 및 지원하나요?

현재 미리 보기로, Microsoft의 지원을 통해 일반 가용성 릴리스 상태가 될 때까지 정기적으로 업데이트를 제공할 예정입니다. 개선에 도움이 되는 피드백을 제공하시기 바랍니다. 테스트 결과로 조직에 맞게 사용자 지정된 이 도구의 일부로 보다 자세한 Office 365 네트워크 온보드 가이드를 게시할 계획입니다.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>고급 테스트 클라이언트를 실행하려면 무엇이 필요한가요?

고급 테스트 클라이언트에는 .NET Core 3.1 데스크톱 런타임이 필요합니다. 설치하지 않고 고급 테스트 클라이언트를 실행하면 [.NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)설치 관리자 페이지로 이동됩니다. SDK가 아닌 데스크톱 런타임 또는 페이지에 더 ASP.NET Core 런타임이 설치해야 합니다. .NET Core를 설치하려면 컴퓨터에 대한 관리자 권한이 필요합니다.

### <a name="what-is-microsoft-365-service-front-door"></a>Microsoft 365 서비스 프런트 도어란?

Microsoft 365 서비스 프런트 도어는 Office 클라이언트 및 서비스가 네트워크 연결을 종료하는 Microsoft 전역 네트워크의 진입점입니다. Microsoft 365에 대한 최적의 네트워크 연결을 위해 네트워크 연결을 도시 또는 대도시에서 가장 가까운 Microsoft 365 프런트 도어로 종료하는 것이 좋습니다.

참고: Microsoft 365 서비스 프런트 도어는 Azure 마켓플레이스에서 사용할 수 있는 **Azure Front Door 서비스** 제품에 직접적인 관계가 없습니다.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>최상의 Microsoft 365 서비스 프런트 도어란 무엇입니까?

최상의 Microsoft 365 서비스 프런트 도어(이전의 최적의 서비스 프런트 도어)는 일반적으로 시나 대도시에서 네트워크에서 가장 가까운 서비스 프런트 도어입니다. Microsoft 365 네트워크 성능 도구를 사용하여 사용 중 Microsoft 365 서비스 프런트 도어의 위치와 최상의 서비스 프런트 도어를 확인합니다. 이 도구에서 사용 중 프런트 도어가 최상의 정문 중 하나로 확인되는 경우 Microsoft의 글로벌 네트워크에 대한 연결이 매우 잘 연결될 것으로 예상됩니다.

### <a name="what-is-an-internet-egress-location"></a>인터넷으로 이동하는 위치란?

인터넷 나가기 위치는 네트워크 트래픽이 엔터프라이즈 네트워크를 종료하고 인터넷에 연결하는 위치입니다. NAT(Network Address Translation) 장치가 있는 위치와 일반적으로 ISP(인터넷 서비스 공급자)에 연결하는 위치로도 식별됩니다. 위치와 인터넷의 연결 위치 간에 긴 거리가 표시될 경우 이는 중요한 WAN 백HAUL을 식별할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결(미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 네트워크 성능 인사이트(미리 보기)](office-365-network-mac-perf-insights.md)

[Microsoft 365 네트워크 평가(미리 보기)](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location Services(미리 보기)](office-365-network-mac-location-services.md)
