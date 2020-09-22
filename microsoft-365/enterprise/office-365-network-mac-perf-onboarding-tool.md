---
title: Microsoft 365 네트워크 연결 테스트 도구 (미리 보기)
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
description: Microsoft 365 네트워크 연결 테스트 도구 (미리 보기)
ms.openlocfilehash: 72f42a71ec44d165a24187edaf03aa62d330479b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48200820"
---
# <a name="microsoft-365-network-connectivity-test-tool-preview"></a>Microsoft 365 네트워크 연결 테스트 도구 (미리 보기)

Microsoft 365 네트워크 연결 테스트 도구는에 <https://connectivity.office.com> 있습니다. Microsoft 365 관리 센터에서 사용할 수 있는 네트워크 평가 및 네트워크 insights 정보에 대 한 adjunct 도구입니다. **| 연결** 메뉴

![연결 테스트 도구](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>네트워크 연결 테스트 도구는 WW 상업용 및 독일의 테 넌 트를 지원 하지만 GCC 보통, GCC High, DoD 또는 중국이 아닙니다.

Microsoft 365 관리 센터의 네트워크 insights는 매일 집계 되는 Microsoft 365 테 넌 트에 대 한 일반 제품 측정을 기반으로 합니다. 비교에서는 Microsoft 365 네트워크 연결 테스트의 네트워크 insights가 로컬로 실행 되 고 도구에서 한 번 수행 됩니다. 제품에서 수행할 수 있는 테스트는 제한 되며 사용자에 대 한 로컬 테스트를 실행 하 여 더 많은 데이터를 수집할 수 있습니다. Microsoft 365 관리 센터의 네트워크 insights에서 특정 사무실 위치에 Microsoft 365 사용에 대 한 네트워킹 문제가 있음을 보여 줍니다. Microsoft 365 연결 테스트를 통해 권장 되는 네트워크 성능 개선 작업으로 인해 발생 하는 문제의 근본적인 원인을 확인할 수 있습니다.

Microsoft 365 관리 센터의 각 사무실 위치에 대해 네트워킹 품질 상태를 평가할 수 있으며 Microsoft 365 연결 테스트를 기반으로 테스트를 배포한 후 더 자세한 내용을 확인할 수 있는 방법을 함께 사용 하는 것이 좋습니다.

>[!IMPORTANT]
>네트워크 insights, Microsoft 365 관리 센터의 성능 권장 사항 및 평가는 현재 미리 보기 상태 이며, 기능 미리 보기 프로그램에 등록 되어 있는 Microsoft 365 테 넌 트에만 사용할 수 있습니다.

## <a name="what-happens-at-each-test-step"></a>각 테스트 단계에서 수행 되는 작업

### <a name="office-location-identification"></a>사무실 위치 식별

테스트 실행 단추를 클릭 하면 실행 중인 테스트 페이지가 표시 되 고 사무실 위치를 식별 합니다. 구/군/시, 시/도 및 국가를 기준으로 위치를 입력 하거나 웹 브라우저에서 검색 하도록 설정할 수 있습니다. 검색 한 후에는 웹 브라우저에서 위도 및 경도를 요청 하 고 사용 하기 전에 300m에 따라 정확성을 300m으로 제한 합니다. 네트워크 성능에 대 한 건물 보다 더 정확 하 게 위치를 식별할 필요가 없기 때문에이 작업을 수행 합니다. 

### <a name="javascript-tests"></a>JavaScript 테스트

Office 위치 확인 후 JavaScript에서 TCP 대기 시간 테스트를 실행 하 고 서비스에서 사용 및 권장 되는 Office 365 서비스 전면 도어 서버에 대 한 데이터를 요청 합니다. 완료 되 면 지도에 표시 되 고 다음 단계 이전에 볼 수 있는 세부 정보 탭에 나타납니다.

### <a name="download-the-advanced-tests-client-application"></a>고급 테스트 클라이언트 응용 프로그램 다운로드

다음으로, 고급 테스트 클라이언트 응용 프로그램의 다운로드를 시작 합니다. 사용자가 클라이언트 응용 프로그램을 시작 하는 데 의존 하며 .NET Core도 설치 되어 있어야 합니다.

Microsoft 365 네트워크 연결 테스트는 두 부분으로 구성 됩니다. <https://connectivity.office.com> 고급 네트워크 연결 테스트를 실행 하는 다운로드 가능한 Windows 클라이언트 응용 프로그램 및 웹 사이트 대부분의 테스트에서는 응용 프로그램을 실행 해야 합니다. 그러면 결과가 웹 페이지에 다시 실행 될 때 채워집니다.

웹 브라우저 테스트가 완료 되 면 웹 사이트에서 고급 클라이언트 테스트 응용 프로그램을 다운로드 하 라는 메시지가 표시 됩니다. 메시지가 표시 되 면 파일을 열고 실행 합니다.

![고급 테스트 클라이언트 응용 프로그램](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>고급 테스트 클라이언트 응용 프로그램 시작

클라이언트 응용 프로그램이 시작 되 면 웹 페이지가 표시 되도록 업데이트 되 고 테스트 데이터가 웹 페이지로 수신 되기 시작 합니다. 새 데이터를 받을 때마다 업데이트 되며 도착 하면 데이터를 검토할 수 있습니다.

### <a name="advanced-tests-completed-and-test-report-upload"></a>고급 테스트가 완료 되었으며 보고서 업로드 테스트

테스트가 완료 되 면 웹 페이지와 고급 테스트 클라이언트가 모두이를 나타내고 테스트 보고서에 로그인 한 사용자가 고객 테 넌 트에 업로드 됩니다.

## <a name="sharing-your-test-report"></a>테스트 보고서 공유

테스트 보고서를 사용 하려면 Office 365 계정에 로그인 해야 합니다. 관리자가 테스트 보고서를 공유할 수 있는 방법을 선택 합니다.

### <a name="sharing-your-report-with-your-administrator"></a>관리자와 보고서 공유

로그인 한 상태에서 모든 테스트 보고서는 관리자와 공유 됩니다.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Microsoft 계정 팀, 지원 또는 기타 직원과 공유

개인 식별을 제외 하는 테스트 보고서는 Microsoft 직원과 공유 됩니다. 이 기능은 기본적으로 사용 하도록 설정 되어 있으며 관리자가 상태를 사용 하지 않도록 설정할 수 있습니다. **| ** Microsoft 365 관리 센터의 네트워크 연결 페이지입니다.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>동일한 Office 365 테 넌 트에 로그인 하는 다른 사용자와 공유

사용자를 선택 하 여 보고서를 공유할 수 있으며, 기본적으로이 옵션은 사용 하도록 설정 되어 있습니다. 관리자가이 기능을 사용 하지 않도록 설정할 수도 있습니다.

![사용자와 함께 테스트 결과에 대 한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>ReportID 링크를 사용 하 여 모든 사용자와 공유

ReportID 링크에 대 한 액세스 권한을 제공 하 여 모든 사용자와 테스트 보고서를 공유할 수 있습니다. 이렇게 하면 로그인 하지 않고도 테스트 보고서를 가져올 수 있도록 다른 사람에 게 보낼 수 있는 URL이 생성 됩니다. 이 기능은 기본적으로 사용 하지 않도록 설정 되어 있으며 관리자가 사용 하도록 설정 해야 합니다.

![테스트 결과에 대 한 링크 공유](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>네트워크 연결 테스트 결과

결과가 **요약** 및 **세부 정보** 탭에 표시 됩니다. 요약 탭에는 검색 된 네트워크 경계의 맵과 주변의 다른 Office 365 고객에 대 한 네트워크 평가가 비교 되어 표시 됩니다. 또한 테스트 보고서를 공유할 수 있습니다. 요약 결과 보기의 모양은 다음과 같습니다.

![네트워크 연결 테스트 도구 요약 결과](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

다음은 도구에 표시 되는 세부 정보 탭 출력의 예입니다. 세부 정보 탭에서 favorably를 임계값과 비교한 결과 녹색 원형 확인 표시가 나타납니다. 결과가 네트워크 통찰력을 나타내는 임계값을 초과 하면 빨간색 삼각형 느낌표가 표시 됩니다. 다음 섹션에서는 각 세부 항목 탭 결과 행에 대해 설명 하 고 네트워크 insights에 사용 되는 임계값에 대해 설명 합니다.

![네트워크 연결 테스트 도구 예제 테스트 결과](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>위치 정보

이 섹션에서는 사용자의 위치와 관련 된 테스트 결과를 보여 줍니다.

#### <a name="your-location"></a>사용자 위치

사용자 위치는 사용자가 웹 브라우저에서 검색 되거나 사용자가 선택한 시간에 입력 될 수 있습니다. 네트워크 거리를 엔터프라이즈 네트워크 경계의 특정 부분으로 식별 하는 데 사용 됩니다. 이 위치 검색의 도시와 다른 네트워크 지점 까지의 거리가 보고서에 저장 됩니다.

사용자 사무실 위치는 지도 보기에 표시 됩니다.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>네트워크 송신 위치 (ISP에 네트워크가 연결 되는 위치)

서버 쪽에서 네트워크 송신 IP 주소를 식별 합니다. 위치 데이터베이스는 네트워크 송신에 대 한 대략적인 위치를 조회 하는 데 사용 됩니다. 일반적으로 이러한 데이터베이스는 약 90%의 IP 주소를 정확 하 게 사용할 수 있습니다. 네트워크 송신 IP 주소에서 찾은 위치가 정확 하지 않으면이 테스트에서 잘못 된 결과가 반환 됩니다. 특정 IP 주소에 대해이 오류가 발생 하는지 확인 하려면 공용으로 액세스 가능한 네트워크 IP 주소 위치 웹 사이트를 사용 하 여 실제 위치와 비교할 수 있습니다.

#### <a name="your-distance-from-the-network-egress-location"></a>네트워크 송신 위치 로부터의 거리

해당 위치에서 사무실 위치로의 거리를 확인 합니다. 이는 TCP 대기 시간이 25ms 보다 많이 증가 하 여 사용자 환경에 영향을 줄 수 있으므로 거리가 **500 마일** (800 킬로미터) 보다 큰 경우 네트워크를 파악 하는 것으로 표시 됩니다.

네트워크 송신 위치가 지도 보기에 표시 되 고 엔터프라이즈 WAN 내부에 네트워크가 연결 되었음을 나타내는 사용자 사무실 위치에 연결이 설정 됩니다.

Microsoft 365 네트워크 연결에는 사용자 사무실 위치에서 인터넷으로 로컬 및 직접 네트워크 송신을 구현 하는 것이 좋습니다. 이러한 네트워크 통찰력을 해결 하는 가장 좋은 방법은 로컬 및 직접 egress에 대 한 개선 사항입니다.

#### <a name="proxy-server-information"></a>프록시 서버 정보

로컬 컴퓨터에 구성 된 프록시 서버를 확인 합니다. 최적화 범주에 대 한 네트워크 경로에 구성 되어 있는 항목 (Microsoft 365 네트워크 트래픽)이 있는지 확인 합니다. 사용자 사무실 위치에서 프록시 서버 까지의 거리를 확인 합니다. 이러한 간격은 먼저 ICMP ping을 통해 테스트 하며,이로 인해 TCP ping을 실행 하는 데 실패 한 경우에는 IP 주소 위치 데이터베이스에서 프록시 서버 IP 주소를 조회 합니다. 사용자 사무실 위치에서 프록시 서버가 **500 마일** (800 킬로미터) 보다 멀리 떨어진 경우 네트워크 통찰력을 볼 수 있습니다.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>조직에 연결 하는 데 사용 하는 VPN (가상 사설망)

이는 VPN을 사용 하 여 Office 365에 연결 하는 경우를 감지 합니다. VPN을 사용 하지 않는 경우 또는 Office 365에 대 한 권장 분할 터널 구성의 VPN이 있는 경우 통과 결과가 표시 됩니다.

#### <a name="vpn-split-tunnel"></a>VPN 분할 터널

Exchange Online, SharePoint Online 및 Microsoft 팀에 대 한 각 최적화 범주 경로는 VPN에서 터널링 되는지 여부를 테스트 합니다. 작업을 분할 하면 VPN 전체가 방지 됩니다. 터널링 된 작업은 모두 VPN을 통해 전송 됩니다. 선택적 터널링 된 작업에는 VPN을 통해 전송 되는 일부 경로와 몇 개의 분할이 있습니다. 모든 작업을 분할 하거나 선택적으로 터널링 하면 통과 결과가 표시 됩니다.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>대도시 영역에 있는 고객의 성능 향상

Exchange Online 서비스에 대 한 사용자 사무실 위치의 네트워크 TCP 대기 시간은 같은 메트로 영역의 다른 Microsoft 365 고객과 비교 됩니다. 네트워크에 대 한 자세한 내용은 같은 지하철 영역에 있는 고객 중 10% 이상이 더 나은 성능을 가진 경우에 표시 됩니다. 즉, 사용자는 Microsoft 365 사용자 인터페이스에서 더 나은 성능을 갖게 됩니다.

이 네트워크 통찰력은 도시의 모든 사용자가 동일한 통신 인프라에 대 한 액세스 권한을 가지 며 인터넷 회로 및 Microsoft 네트워크와 같은 근접성을 갖게 된다는 것을 기반으로 생성 됩니다.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>네트워크에서 DNS 요청을 만드는 시간

테스트를 실행 한 클라이언트 컴퓨터에 구성 된 DNS 서버를 표시 합니다. DNS 재귀 확인 프로그램 서버 일 수 있지만 드문 경우는 아닙니다. DNS 결과를 캐시 하 고 캐시 되지 않은 DNS 요청을 다른 DNS 서버로 전달 하는 DNS 전달자 서버가 될 수 있습니다.

이는 정보를 제공 하기 위한 것 이며 네트워크 통찰력에는 영향을 주지 않습니다.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>DNS 재귀 해결 프로그램에 연결할 때 까지의 거리 및/또는 시간

사용 중인 DNS 재귀 해결 프로그램은 특정 DNS 요청을 수행한 다음 DNS 이름 서버에 동일한 요청을 받은 IP 주소를 물어 확인 합니다. 이 IP 주소는 DNS 재귀 해결 프로그램 이며 위치를 찾기 위해 IP 주소 위치 데이터베이스에서 조회 됩니다. 그러면 사용자 사무실 위치에서 DNS 재귀 확인자 서버 위치로의 거리가 계산 됩니다. 이는 거리가 **500 마일** (800 킬로미터) 보다 크면 네트워크에 대 한 정보를 파악 하는 것으로 표시 됩니다.

네트워크 송신 IP 주소에서 조회 되는 위치는 정확 하지 않을 수 있으며이 테스트에서 잘못 된 결과가 이어집니다. 특정 IP 주소에 대해이 오류가 발생 하는지 확인 하려면 공개적으로 액세스 가능한 네트워크 IP 주소 위치 웹 사이트를 사용할 수 있습니다.

이 네트워크 통찰력은 Exchange Online 서비스의 프런트 도어 선택에 특히 영향을 줍니다. 이 통찰력을 확인 하려면 로컬 및 직접 네트워크 송신이 필수 구성 요소 여야 하 고, DNS 재귀 해결 프로그램을 해당 네트워크 egress에 가까이에 배치 해야 합니다.

### <a name="exchange-online"></a>Exchange Online

이 섹션에서는 Exchange Online과 관련 된 테스트 결과를 보여 줍니다.

#### <a name="exchange-service-front-door-location"></a>Exchange 서비스 전면 도어 위치

사용 중인 Exchange service 프런트 도어는 Outlook에서이를 수행 하는 것과 동일한 방식으로 식별 되며, 사용자 위치에서 네트워크 TCP 대기 시간을 측정 합니다. TCP 대기 시간이 표시 되 고 사용 중 Exchange 서비스 전면 도어가 현재 위치에 대 한 모범 사례 서비스 전면 도어 목록과 비교 됩니다. 이는 최상의 Exchange 서비스 전면 도어 중 하나를 사용 하지 않는 경우 네트워크에 대 한 정보로 표시 됩니다.

회사 네트워크를 송신 하기 전에 네트워크 교환이 너무 많이 발생 하는 경우 (예를 들어, 로컬 및 직접 네트워크 송신을 권장 하는 경우)에는 Exchange 서비스 프런트 도어 중 하나를 사용 하지 못할 수 있습니다. 또한 원격 DNS 재귀 해결 프로그램 서버를 사용 하는 경우에도 DNS 재귀 해결 프로그램 서버를 네트워크 egress에 정렬 하는 것이 좋습니다.

Exchange 서비스 전면 도어의 TCP 대기 시간 (ms)에 대 한 잠재적 개선이 계산 됩니다. 이 작업은 테스트 된 사용자 사무실 위치 네트워크 대기 시간을 살펴보고 현재 위치에서 closets Exchange 서비스 전면 도어 까지의 네트워크 대기 시간을 빼서 수행 합니다. 차이점은 개선에 대 한 잠재적인 기회를 나타냅니다.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>사용자의 위치에 대 한 최상의 Exchange 서비스 전면 도어

사용자 위치에 대해 도시별로 가장 적합 한 Exchange 서비스 프런트 도어 위치를 나열 합니다.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>클라이언트 DNS에 기록 된 서비스 전면 도어

여기에는 연결 하려는 Exchange 서비스 전면 도어 서버의 DNS 이름과 IP 주소가 표시 됩니다. 정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다.

### <a name="sharepoint-online"></a>SharePoint Online

이 섹션에서는 SharePoint Online 및 OneDrive와 관련 된 테스트 결과를 보여 줍니다.

#### <a name="the-service-front-door-location"></a>서비스 전방 도어 위치

사용 중인 SharePoint service 프런트 도어는 OneDrive 클라이언트와 동일한 방식으로 식별 되며, 사용자 사무실 위치에서의 네트워크 TCP 대기 시간을 측정 합니다.

#### <a name="download-speed"></a>다운로드 속도

SharePoint 서비스 전면 도어에서 15Mb 파일의 다운로드 속도를 측정 합니다. 결과는 **1 초**에 SharePoint 또는 OneDrive에서 다운로드할 수 있는 크기 (mb)를 나타내기 위해 초당 mb로 표시 됩니다. 이 숫자는 최소 회로 대역폭과 초당 1-10과 비슷해야 합니다. 예를 들어 100mbps 인터넷 연결이 있는 경우 초당 10mb가 될 수 있습니다 (10MBps).

#### <a name="buffer-bloat"></a>버퍼 팽창

15Mb 다운로드 중에 SharePoint 서비스 전면 도어의 TCP 대기 시간을 측정 합니다. 이 시간은 부하가 발생 하는 대기 시간으로, 부하가 발생 하지 않을 때의 대기 시간과 비교 됩니다. 로드 하는 동안 대기 시간 증가는 종종 로드 되는 소비자 네트워크 장치 버퍼 (또는 증가가)로 인해 발생 합니다. 네트워크 통찰력은 1000 이상으로 표시 됩니다.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>클라이언트 DNS에 기록 된 서비스 전면 도어

여기에는 보낸 SharePoint 서비스 프런트 엔드 서버의 DNS 이름과 IP 주소가 표시 됩니다. 정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다.

### <a name="microsoft-teams"></a>Microsoft Teams

이 섹션에서는 Microsoft 팀과 관련 된 테스트 결과를 보여 줍니다.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>미디어 연결 (오디오, 비디오 및 응용 프로그램 공유)

이를 통해 Microsoft 팀 서비스 전면 도어의 UDP 연결을 테스트 합니다. 이 문제가 차단 되 면 Microsoft 팀 에서도 여전히 TCP를 사용할 수 있지만 오디오 및 비디오는 손상 됩니다. [비즈니스용 Skype Online의 미디어 품질 및 네트워크 연결 성능](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance) 에서 Microsoft 팀에도 적용 되는 이러한 UDP 네트워크 측정에 대해 자세히 알아봅니다.

#### <a name="packet-loss"></a>패킷 손실

클라이언트에서 Microsoft 팀 서비스 전면 도어로 10 초의 두 번째 테스트 오디오 호출로 측정 된 UDP 패킷 손실을 보여 줍니다. 이는 패스의 **1.00%** 보다 작아야 합니다.

### <a name="latency"></a>대기 시간

측정 된 UDP 대기 시간 ( **적고 100 밀리초**미만 이어야 함)을 표시 합니다.

#### <a name="jitter"></a>지터

계산 된 UDP 지터를 표시 하며이 값은 **30ms**보다 작아야 합니다.

#### <a name="connectivity"></a>연결

사용자 사무실 위치에서 필요한 모든 Microsoft 365 네트워크 끝점에 대 한 HTTP 연결을 테스트 합니다. 이러한 기능은에 게시 됩니다 [https://aka.ms/o365ip](https://aka.ms/o365ip) . 연결할 수 없는 모든 필수 네트워크 끝점에 대 한 네트워크 통찰력이 표시 됩니다.

연결 ay는 회사 네트워크 경계에 있거나 클라우드 프록시로 사용 중인 프록시 서버, 방화벽 또는 다른 네트워크 보안 장치에 의해 차단 됩니다.

에서 정의 된 최적화 또는 허용 범주에 있는 각각의 필수 Microsoft 365 네트워크 끝점에서 SSL 인증서를 테스트 합니다 [https://aka.ms/o365ip](https://aka.ms/o365ip) . Microsoft SSL 인증서를 찾지 못하는 테스트는 중간 네트워크 장치에 의해 연결 된 암호화 된 네트워크를 차단 해야 합니다. 네트워크에 대 한 통찰력은 모든 암호화 된 네트워크 끝점에 표시 됩니다.

Microsoft에서 제공 하지 않는 SSL 인증서가 발견 되 면 테스트에 대 한 FQDN과 사용 중인 SSL 인증서 소유자가 표시 됩니다. SSL 인증서 소유자는 프록시 서버 공급 업체가 될 수도 있고, 엔터프라이즈 자체 서명 된 인증서 일 수도 있습니다.

#### <a name="network-path"></a>네트워크 경로

이 섹션에서는 Exchange Online 서비스 전면 도어, SharePoint Online 서비스 전면 도어 및 Microsoft 팀 서비스 전면 도어에 대 한 ICMP traceroute 결과를 보여 줍니다. 정보를 제공 하기 위한 것 이며 연결 된 네트워크 통찰력은 없습니다. 3 개의 traceroutes 제공 됩니다. _Outlook.office365.com_에 대 한 traceroute, 고객 SharePoint 프런트 엔드에 대 한 traceroute 또는 _microsoft.sharepoint.com_ 에 대 한 _traceroute를 제공 합니다._

## <a name="connectivity-reports"></a>연결 보고서

로그인 한 경우 이전에 실행 한 보고서를 검토할 수 있습니다. 또한 목록에서 공유 하거나 삭제할 수 있습니다.

![보고서](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>네트워크 상태

여기에는 microsoft 365 고객에 게 영향을 줄 수 있는 Microsoft의 글로벌 네트워크에 대 한 중요 한 상태 문제가 표시 됩니다.

![네트워크 상태](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>FAQ

다음은 자주 묻는 몇 가지 질문에 대 한 대답입니다.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>이 도구는 Microsoft에서 출시 및 지원 하나요?

현재는 미리 보기 이며 Microsoft의 지원을 통해 일반 가용성 릴리스 상태에 도달할 때까지 정기적으로 업데이트를 제공 하는 계획입니다. 개선에 도움이 되는 의견을 제공 하세요. 테스트 결과를 기준으로 조직에 대해 사용자 지정 된이 도구의 일부로 보다 자세한 Office 365 네트워크 온 보 딩 가이드를 게시할 계획입니다.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>고급 테스트 클라이언트를 실행 하는 데 필요한 사항

고급 테스트 클라이언트에는 .NET Core 3.1 데스크톱 런타임이 필요 합니다. 설치 하지 않고 고급 테스트 클라이언트를 실행 하는 경우에는 [.Net Core 3.1 설치 관리자 페이지로](https://dotnet.microsoft.com/download/dotnet-core/3.1)이동 합니다. 데스크톱 런타임과 SDK가 설치 되어 있지 않거나 해당 페이지에서 위쪽에 있는 ASP.NET 코어 런타임이 있어야 합니다. .NET Core를 설치 하려면 컴퓨터에 대 한 관리자 권한이 필요 합니다.

### <a name="what-is-microsoft-365-service-front-door"></a>Microsoft 365 서비스 전면 도어 란?

Microsoft 365 서비스 전면 도어는 Microsoft의 글로벌 네트워크에서 Office 클라이언트 및 서비스가 네트워크 연결을 종료 하는 진입점입니다. Microsoft 365에 대 한 최적의 네트워크 연결을 위해 네트워크 연결이 도시나 메트로 가장 가까운 Microsoft 365 전면 도어로 종료 되는 것이 좋습니다.

참고: Microsoft 365 서비스 전면 도어는 Azure marketplace에서 제공 되는 **azure Direct 도어 서비스** 제품과 직접 관계가 없습니다.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>가장 적합 한 Microsoft 365 서비스 전면 도어는 무엇입니까?

가장 적합 한 Microsoft 365 서비스 전면 도어 (이전의 가장 적합 한 서비스 전면 도어)는 네트워크 egress에서 일반적으로 구/군/시 또는 지하철 지역에 가깝습니다. Microsoft 365 네트워크 성능 도구를 사용 하 여 사용 중인 Microsoft 365 서비스 전면 도어의 위치 및 모범 서비스 전면 도어를 확인 합니다. 도구에서 사용자가 사용 하는 프런트 도어 중 하나에 해당 하는 경우 Microsoft의 글로벌 네트워크에 대 한 연결을 잘 알고 있어야 합니다.

### <a name="what-is-an-internet-egress-location"></a>인터넷 송신 위치 란?

인터넷 송신 위치는 네트워크 트래픽이 기업 네트워크를 종료 하 고 인터넷에 연결 하는 위치입니다. 또한 NAT (Network Address Translation) 장치가 있는 위치로도 식별 되며, 대개 ISP (인터넷 서비스 공급자)와 연결 됩니다. 위치와 인터넷 송신 위치 사이에 긴 거리가 표시 되 면이로 인해 상당한 WAN 백을 확인할 수 있습니다.

## <a name="related-topics"></a>관련 항목

[Microsoft 365 관리 센터의 네트워크 연결 (미리 보기)](office-365-network-mac-perf-overview.md)

[Microsoft 365 network performance insights (preview)](office-365-network-mac-perf-insights.md)

[Microsoft 365 네트워크 평가 (미리 보기)](office-365-network-mac-perf-score.md)

[Microsoft 365 네트워크 연결 위치 서비스 (미리 보기)](office-365-network-mac-location-services.md)
