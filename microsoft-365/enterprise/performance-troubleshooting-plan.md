---
title: Office 365 성능 문제 해결 계획
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 5/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c
ms.collection:
- M365-security-compliance
- Ent_O365
description: 이 문서는 성능 문제의 Office 365 해결하고 가장 일반적인 몇 가지 문제를 해결하는 데 도움이 될 수 있습니다.
ms.openlocfilehash: 6ef459d6469881c71ea7d1da3a32eb42eb3ead6b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59191182"
---
# <a name="performance-troubleshooting-plan-for-office-365"></a>Office 365 성능 문제 해결 계획

SharePoint Online, 비즈니스용 OneDrive, Exchange Online 또는 비즈니스용 Skype Online 및 클라이언트 컴퓨터 간의 성능 저하, 중단 및 성능 저하를 식별하고 해결하기 위해 취할 단계를 알아야 하나요? 지원에 문의하기 전에 이 문서는 성능 Office 365 해결하고 가장 일반적인 몇 가지 문제를 해결하는 데 도움이 될 수 있습니다.

이 문서는 실제로 성능 문제와 관련한 중요한 데이터를 캡처하는 데 사용할 수 있는 예제 작업 계획입니다. 이 문서에는 몇 가지 가장 많은 문제도 포함되어 있습니다.

네트워크 성능을 처음 사용하며 클라이언트 컴퓨터와 컴퓨터 간의 성능을 모니터링하기 위한 장기적인 계획을 세우고 Office 365 관리자 및 IT Office 365 성능 조정 및 문제 [해결을 Pro.](performance-tuning-using-baselines-and-history.md)

## <a name="sample-performance-troubleshooting-action-plan"></a>예제 성능 문제 해결 작업 계획

이 작업 계획에는 두 부분으로 구성됩니다. 준비 단계 및 로깅 단계 지금 성능 문제가 발생하고 데이터 수집을 해야 하는 경우 이 계획을 바로 사용할 수 있습니다.

### <a name="prepare-the-client-computer"></a>클라이언트 컴퓨터 준비

- 성능 문제를 재현할 수 있는 클라이언트 컴퓨터를 찾아야 합니다. 이 컴퓨터는 문제 해결 중에 사용됩니다.
- 테스트할 시간을 준비할 수 있도록 성능 문제가 발생하게 하는 단계를 적어 써야 합니다.
- 정보를 수집하고 기록하기 위한 도구를 설치합니다.
  - [Netmon 3.4를 설치하거나](https://www.microsoft.com/download/details.aspx?id=4865) 동등한 네트워크 추적 도구를 사용합니다.
  - 무료 Basic Edition [HTTPWatch를 설치하거나](https://www.httpwatch.com/download/) 동등한 네트워크 추적 도구를 사용합니다.
  - 테스트하는 동안 수행한 단계의 기록을 보관하기 위해 PSR.exe Vista 이상에 제공된 단계 레코더(PSR.exe Windows)를 실행합니다.

### <a name="log-the-performance-issue"></a>성능 문제 기록

- 모든 추가 인터넷 브라우저를 닫습니다.
- 단계 레코더 또는 다른 화면 레코더를 시작하십시오.
- Netmon 캡처(또는 네트워크 추적 도구)를 시작하세요.
- ipconfig /flushdns를 입력하여 명령줄에서 클라이언트 컴퓨터에서 DNS 캐시를 지워야 합니다.
- 새 브라우저 세션을 시작하고 HTTPWatch를 켜야 합니다.
- 선택 사항: 테스트 Exchange Online 클라이언트 Exchange 콘솔에서 Office 365 실행합니다.
- 성능 문제를 일으키는 정확한 단계를 재현합니다.
- Netmon 또는 기타 도구의 추적을 중지합니다.
- 명령줄에서 다음 명령을 입력하고 enter를 눌러 Office 365 구독에 대한 추적 경로를 실행합니다.

  ``` cmd
  tracert <subscriptionname>.onmicrosoft.com
  ```

- 단계 레코더를 중지하고 비디오를 저장합니다. 캡처 날짜 및 시간 및 캡처가 좋은 성능을 보여줄지 또는 좋지 않은 성능을 보여줄지 여부를 포함해야 합니다.
- 추적 파일을 저장합니다. 또한 캡처 날짜 및 시간 및 성능이 좋은지 또는 좋지 않은지 여부를 포함해야 합니다.

이 문서에 언급된 도구를 실행하는 데 익숙하지 않은 경우 다음에 이러한 단계를 제공하기 때문에 걱정하지 마세요. 이러한 종류의 네트워크 캡처를 하는 데 익숙한 경우 필터링 및 [](performance-tuning-using-baselines-and-history.md#how-to-collect-baselines)로그 읽기에 대해 설명하는 기준을 수집하는 방법으로 건너뛸 수 있습니다.

### <a name="flush-the-dns-cache-first"></a>먼저 DNS 캐시 플러시

이유 DNS 캐시를 플러시하여 클린 슬레이트로 테스트를 시작하게 됩니다. 캐시를 지우면 DNS 확인자 콘텐츠를 최신 항목으로 다시 설정하게 됩니다. 플러시는 HOSTS 파일 항목을 제거하지 않습니다. HOST 파일 항목을 광범위하게 사용하는 경우 해당 항목을 다른 디렉터리의 파일에 복사한 다음 HOST 파일을 비워야 합니다.

#### <a name="flush-your-dns-resolver-cache"></a>DNS 확인자 캐시 플러시

1. 명령 프롬프트(Start  Run cmd 또는 Windows \>  \> **cmd)를**  \> **열 수 있습니다.**
2. 다음 명령을 입력한 후 Enter 키를 누릅니다.

    ``` cmd
    ipconfig /flushdns
    ```

## <a name="netmon"></a>Netmon

Microsoft의 네트워크 모니터링[도구(Netmon)는](https://www.microsoft.com/download/details.aspx?id=4865)네트워크의 컴퓨터 간에 전달되는 트래픽인 패킷을 분석합니다. Netmon을 사용하여 트래픽을 추적할 수 Office 365 패킷 헤더를 캡처, 보기 및 읽고, 중간 장치를 식별하고, 네트워크 하드웨어의 중요 설정을 확인하고, 손실된 패킷을 찾아 회사 네트워크 및 네트워크의 컴퓨터 간 트래픽 흐름을 Office 365. 트래픽의 실제 본문이 암호화되어 있기 때문에(SSL/TLS를 통해 포트 443을 이동하는 경우 전송되는 파일을 읽을 수 없습니다. 대신 패킷이 걸리는 경로의 필터되지 않은 추적을 얻게 되어 문제 동작을 추적하는 데 도움이 됩니다.

이때 필터를 적용하지 말아야 합니다. 대신 단계를 실행하여 추적을 중지하고 저장하기 전에 문제를 보여 주십시오.

Netmon 3.4를 설치한 후 도구를 열고 다음 단계를 수행합니다.

### <a name="take-a-netmon-trace-and-reproduce-the-issue"></a>Netmon 추적을 사용 하 고 문제를 재현 합니다.

1. Netmon 3.4를 실행합니다.
시작 페이지에는 최근  **캡처,** 네트워크 선택 및 Microsoft 네트워크 모니터 3.4 시작의 세 개의 창이 **있습니다. 을(를) 알 수** 네트워크 선택 패널에는 캡처할 수 있는 기본 네트워크 목록도 표시됩니다. 여기에서 네트워크 카드가 선택되어 있는지 확인합니다.

2. 시작 **페이지 위쪽에서** 새 **캡처를** 클릭합니다. 그러면 Capture 1이라는  시작 페이지 탭 옆에 새 **탭이 추가됩니다.**
![새 캡처, 시작 및 중지 단추가 강조 표시된 Netmon의 사용자 인터페이스입니다.](../media/d4527d84-62ec-4301-82d5-e0166ff71f20.PNG)

3. 간단한 캡처를 사용하려면 **도구** 모음에서 시작을 클릭합니다.

4. 성능 문제가 있는 단계를 재현합니다.

5. 파일 **다른 로** \> **저장** \> **중지를 클릭합니다.** 표준 시간대를 통해 날짜와 시간을 주고 성능이 나쁘거나 양호한지 언급해야 합니다.

## <a name="httpwatch"></a>HTTPWatch

[HTTPWatch는](https://www.httpwatch.com/download/) 요금이 청구되고 무료 버전이 제공됩니다. 무료 Basic Edition은 이 테스트에 필요한 모든 것을 다합니다. HTTPWatch는 브라우저 창에서 네트워크 트래픽 및 페이지 로드 시간을 바로 모니터링합니다. HTTPWatch는 성능을 그래픽으로 Internet Explorer 플러그 인입니다. 분석은 HTTPWatch Studio에서 저장하고 볼 수 있습니다.

> [!NOTE]
> Firefox, Google Chrome 등의 다른 브라우저를 사용하는 경우 또는 브라우저에 HTTPWatch를 설치할 수 Internet Explorer 새 브라우저 창을 열고 키보드에서 F12를 누릅니다. 브라우저 아래쪽에 개발자 도구 팝업이 표시됩니다. Opera를 사용하는 경우 웹 검사기에서 Ctrl+Shift+I를  누르고 네트워크 탭을 클릭하고 아래에 설명된 테스트를 완료합니다. 정보가 약간 다르지만 로드 시간은 밀리초로 표시됩니다. > HTTPWatch는 온라인 페이지 로드 SharePoint 매우 유용합니다.

### <a name="run-httpwatch-and-reproduce-the-issue"></a>HTTPWatch를 실행하고 문제를 재현합니다.

HTTPWatch는 브라우저 플러그 인이기 때문에 브라우저에 도구를 표시하는 것은 각 브라우저 버전마다 약간 Internet Explorer. 일반적으로 HTTPWatch는 브라우저의 명령 표시줄에서 Internet Explorer 있습니다. 브라우저 창에 HTTPWatch 플러그 인이 없는 경우 도움말을 클릭하여 브라우저 버전을  확인하거나 이후 버전의 Internet Explorer 에서 기어 기호 및 \>  **Internet Explorer.** 명령 **표시줄을 시작하려면** 명령 표시줄에서 메뉴 Internet Explorer 마우스 오른쪽 **단추로 클릭하고 명령 표시줄을 클릭합니다.**

과거에는 HTTPWatch가 명령 및 탐색기 모음에 모두 연결되어 있으므로 설치한 후 아이콘이 즉시 표시되지 않는 경우(다시 시작한 후에도) 도구 및 아이콘에 대한 도구 모음을 선택하십시오. 도구 모음을 사용자 지정하고 옵션을 추가할 수 있습니다.

![Internet Explorer 명령 도구 모음에 HTTPWatch 아이콘이 표시됩니다.](../media/198590b0-d7b1-4bff-a6ad-e4ec3a1e83df.png)

1. 브라우저 창에서 HTTPWatch를 Internet Explorer 실행합니다. 이 창의 아래쪽에 브라우저에 고정된 것으로 표시됩니다. 레코드 **를 클릭합니다.**

2. 성능 문제와 관련된 정확한 단계를 재현합니다. **HTTPWatch에서 중지** 단추를 클릭합니다.

3. HTTPWatch **또는** **전자 메일로 보내기 를 저장합니다.** 날짜 및 시간 정보를 포함하며 Watch에 좋은 성능 또는 좋지 않은 성능의 데모가 포함되어 있는지 여부를 표시하기 위해 파일의 이름을 지정해야 합니다.

![Office 365 홈페이지의 페이지 로드에 대한 네트워크 탭을 보여 주는 HTTPWatch입니다.](../media/021a2c64-d581-49fd-adf4-4c364f589d75.PNG)

이 스크린샷은 HTTPWatch의 Professional 버전입니다. 기본 버전에서 찍은 추적을 컴퓨터의 기본 버전으로 열고 Professional 읽을 수 있습니다. 해당 메서드를 통해 추적에서 추가 정보를 사용할 수 있습니다.

## <a name="problem-steps-recorder"></a>문제 단계 레코더

단계 레코더 또는 PSR.exe 발생하는 문제를 기록할 수 있습니다. 매우 유용한 도구로, 실행이 매우 간단합니다.

### <a name="run-problem-steps-recorder-psrexe-to-record-your-work"></a>문제 단계 레코더(PSR.exe)를 실행하여 작업을 기록합니다.

1. 시작 **실행** 형식을PSR.exe확인을 클릭하거나, Windows 키 형식을 클릭한PSR.exe\>  \> Enter 키를  \>   \>  \> 누르고 있습니다.

2. 작은 PSR.exe 창이 나타나면 레코드  시작을 클릭하고 성능 문제를 재현하는 단계를 재현합니다. 설명 추가를 클릭하여 필요한 경우 설명을 **추가할 수 있습니다.**

3. 단계를 **완료하면** 레코드 중지를 클릭합니다. 성능 문제가 페이지 렌더링인 경우 기록을 중지하기 전에 페이지가 렌더링될 때까지 기다렸다가 렌더링합니다.

4. **저장** 을 클릭합니다.

![단계 레코더 또는 스크린샷은 PSR.exe.](../media/8542b0aa-a3ff-4718-8dc4-43f5521c6c34.PNG)

날짜 및 시간이 기록됩니다. 이렇게 하면 PSR이 Netmon 추적 및 HTTPWatch에 제시간에 연결되고 정밀도 문제 해결에 도움이 됩니다. PSR 레코드의 날짜 및 시간은 예를 들어 URL의 로그인 및 검색과 관리 사이트의 부분 렌더링 간에 1분이 전달된 것으로 표시될 수 있습니다.

## <a name="read-your-traces"></a>추적 읽기

누군가가 문서를 통해 알아야 하는 네트워크 및 성능 문제 해결에 대한 모든 정보를 설명할 수 없습니다. 성능을 능가하는 데는 경험과 네트워크의 작동 방식과 일반적으로 수행에 대한 지식이 필요합니다. 그러나 가장 일반적인 문제 목록을 나열하고 도구를 통해 가장 일반적인 문제를 쉽게 제거할 수 있는 방법을 보여 주어도 됩니다.

Office 365 사이트의 네트워크 추적을 읽는 기술을 선택하려는 경우 페이지 로드 추적을 정기적으로 만들고 이를 읽는 경험을 얻는 것보다 더 나은 교사가 없습니다. 예를 들어, 기회가 있는 경우 서비스 Office 365 로드하고 프로세스를 추적합니다. DNS 트래픽에 대한 추적을 필터링하거나 FrameData에서 검색한 서비스의 이름을 검색합니다. 추적을 검사하여 서비스가 로드될 때 발생하는 단계를 알 수 있습니다. 이렇게 하면 정상적인 페이지 로드의 모양을 알 수 있으며, 문제 해결의 경우 특히 성능과 관련한 좋지 않은 추적과 좋은 비교를 통해 많은 정보를 얻을 수 있습니다.

Netmon은 표시 필터 필드에 Microsoft Intellisense를 사용 합니다. Intellisense 또는 지능형 코드 완료는 기간에 입력하고 사용 가능한 모든 옵션이 드롭다운 선택 상자에 표시되는 트릭입니다. 예를 들어 TCP 창 크기 조정이 걱정되는 경우 이를 통해 필터(예: )를 찾을  `.protocol.tcp.window < 100` 수 있습니다.

![표시 필터 필드가 intellisense를 사용하는 Netmon의 스크린샷입니다.](../media/75a56c11-9a60-47ee-a100-aabdfb1ba10f.PNG)

Netmon 추적에는 트래픽이 많이 남을 수 있습니다. 읽는 경험이 없는 경우 처음에 추적을 여는 것이 부담스러웠을 수 있습니다. 가장 먼저 해야 할 일은 추적의 백그라운드 노이즈와 신호를 분리하는 것입니다. 사용자에 대해 Office 365 테스트했습니다. 이 트래픽이 표시하려는 트래픽입니다. 추적을 사용하는 경우 이 목록이 필요하지 않을 수 있습니다.

클라이언트와 Office 365 트래픽은 TLS를 통해 이동하며, 이는 트래픽 본문이 암호화되고 일반 Netmon 추적에서 읽을 수 없습니다. 성능 분석에서는 패킷에 있는 정보의 구체적인 정보를 알 필요가 없습니다. 그러나 패킷 헤더와 패킷에 포함된 정보에는 매우 관심이 있습니다.

### <a name="tips-to-get-a-good-trace"></a>팁 좋은 추적을 얻을 수 있습니다.

- 클라이언트 컴퓨터의 IPv4 또는 IPv6 주소 값을 확인합니다. **IPConfig를** 입력한 다음 Enter를 눌러 명령 프롬프트에서 이를 얻을 수 있습니다. 이 주소를 알면 추적의 트래픽이 클라이언트 컴퓨터와 직접 관련된지 여부를 한눈에 알 수 있습니다. 알려진 프록시가 있는 경우 프록시를 ping하고 해당 IP 주소도 얻습니다.

- DNS 확인자 캐시를 플러시하고 가능한 경우 테스트를 실행하는 브라우저를 제외한 모든 브라우저를 닫습니다. 예를 들어 지원에서 일부 브라우저 기반 도구를 사용하여 클라이언트 컴퓨터의 데스크톱을 보는 경우 추적 필터링을 준비해야 합니다.

- 사용 중 추적에서 사용 Office 365 서비스를 찾습니다. 이전까지 트래픽을 확인하거나 확인하지 않는 경우 이 단계는 성능 문제를 다른 네트워크 노이즈와 구분하는 데 도움이 되는 단계입니다. 몇 가지 방법으로 이 작업을 할 수 있습니다. 테스트 직전에 특정 서비스의 URL(또는 예: _)에 대해 ping_ 또는 _PsPing을_ 사용할 `ping outlook.office365.com` 수 `psping -4 microsoft-my.sharepoint.com:443` 있습니다. 또한 Netmon 추적에서 프로세스 이름으로 해당 ping 또는 PsPing을 쉽게 찾을 수 있습니다. 이를 통해 찾고 시작할 수 있습니다.

문제 당시 Netmon 추적만 사용 중이면 괜찮습니다. 자신의 방향을 설정하기 위해 또는 처럼 필터를 `ContainsBin(FrameData, ASCII, "office")` `ContainsBin(FrameData, ASCII, "outlook")` 사용하세요. 추적 파일에서 프레임 번호를 기록할 수 있습니다. 프레임 요약 창을  오른쪽으로 스크롤하고 대화 ID 열을 찾아야 할 수도 있습니다. 이 특정 대화의 ID에 대해 표시된 번호가 있으며 나중에 을(를) 녹음하고 나중에 봐도 됩니다. 다른 필터링을 적용하기 전에 이 필터를 제거해야 합니다.

> [!TIP]
> Netmon에는 많은 유용한 기본 제공 필터가 있습니다. 표시 필터 **창의** 맨 위에 있는 필터 로드 _단추를_ 시도합니다.

![클라이언트 컴퓨터의 명령줄에서 PSPing을 사용하여 IP를 찾을 수 있습니다.](../media/4c43ac67-e28e-4536-842d-7add7aa28847.PNG)

![필터 TCP를 통해 동일한 PSPing 명령을 표시하는 클라이언트의 Netmon 추적입니다. Flags.Syn == 1.](../media/0ae7ef7d-e003-4d01-a006-dc49bd1fcef2.PNG)

트래픽에 익숙해지고 필요한 정보를 찾는 방법을 배워야 합니다. 예를 들어 추적의 패킷에 사용 중이던 Office 365(예: "Outlook")에 대한 참조가 있는지 확인하는 방법을 배워야 합니다.

온라인 Office 365 Outlook 경우 트래픽은 다음과 같이 시작됩니다.

- 일치하는 QueryID가 outlook.office365.com DNS 표준 쿼리 및 DNS 응답입니다. 이 회전에 대한 시간 오프셋과 전 세계 Office 365 전역 DNS에서 이름 확인 요청을 보내는 위치를 유의해야 합니다. 이상적으로, 전 세계가 아니라 가능한 한 로컬로.

- 상황 보고서가 영구적으로 이동된 HTTP GET 요청(301)

- RWS를 비롯한 RWS 커넥트 요청 및 커넥트 트래픽입니다. (원격 Winsock에서 연결을 만드는 것입니다.)

- TCP SYN 및 TCP SYN/ACK 대화입니다. 이 대화의 많은 설정이 성능에 영향을 미치게 됩니다.

- 그런 다음 일련의 TLS:TLS 트래픽을 통해 TLS 핸드세이크 및 TLS 인증서 대화가 이됩니다. 데이터는 SSL/TLS를 통해 암호화됩니다.

트래픽의 모든 부분이 중요하고 연결되지만 추적의 작은 부분에는 성능 문제 해결 측면에서 특히 중요한 정보가 포함되어 있으므로 이러한 영역에 집중할 것입니다. 또한 Microsoft에서 일반적인 문제의 상위 10개 목록을 컴파일하기 위해 Office 365 성능 문제 해결을 충분히 수행했기 때문에 이러한 문제에 초점을 맞추고 다음에 문제를 해결해야 하는 도구를 사용하는 방법에 대해 중점적으로 설명할 것입니다.

이러한 도구를 모두 설치하지 않은 경우 아래 매트릭스에서 여러 도구를 사용합니다. 가능한 경우. 설치 지점에 대한 링크가 제공됩니다. 목록에는 [Netmon](https://www.microsoft.com/download/details.aspx?id=4865) 및 [Wireshark와](https://www.wireshark.org/)같은 일반적인 네트워크 추적 도구가 포함되어 있지만 익숙하고 네트워크 트래픽 필터링에 익숙한 모든 추적 도구를 사용합니다. 테스트할 때 다음을 기억하십시오.

- *브라우저를 닫고*  하나의 브라우저만 실행하여 테스트합니다. 그러면 캡처하는 전체 트래픽이 줄어듭됩니다. 이 경우 사용이 적은 추적을 사용할 수 있습니다.
- *클라이언트 컴퓨터에서 DNS 확인자*  캐시 플러시 - 캡처를 시작할 때 더 깔끔한 추적을 위해 깔끔한 슬레이트를 제공합니다.

## <a name="common-issues"></a>일반적인 문제

몇 가지 일반적인 문제와 네트워크 추적에서 문제를 찾는 방법

### <a name="tcp-windows-scaling"></a>TCP Windows 크기 조정

SYN - SYN/ACK에 있습니다. 레거시 또는 기존 하드웨어는 TCP 창 크기 조정을 활용하지 않을 수 있습니다.  적절한 TCP Windows 크기 조정 설정이 없는 경우 TCP 헤더의 기본 16비트 버퍼는 밀리초로 채워지며,  클라이언트가 원래 데이터가 수신된 것으로 확인될 때까지 트래픽을 계속 보낼 수 없습니다. 이로 인해 지연이 발생하게 됩니다.

#### <a name="tools"></a>도구

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>찾아야 할 것

네트워크 추적에서 SYN - SYN/ACK 트래픽을 확인합니다.  Netmon에서 처럼 필터를 사용  `tcp.flags.syn == 1` 합니다. 이 필터는 Wireshark에서 동일합니다.

![두 도구에 대한 Netmon 또는 Wireshark에서 두 도구에 대한 Syn 패킷: TCP를 필터링합니다. Flags.Syn == 1.](../media/4b9a12a1-c915-43c8-ac2f-a679d0435a29.PNG)

모든 SYN에 대해 관련 Ack(SYN/ACK)의 대상 포트(DstPort)에 일치하는 원본 포트(SrcPort) 번호가 있습니다.

네트워크 Windows 사용하는 확장 값을 확인한 후 먼저 SYN을 확장한 다음 관련 SYN/ACK를 확장합니다.

![추적에서 SrcPort와 DstPort를 일치하여 시간 델타를 얻는 방법을 보여 주는 그래픽입니다.](../media/6a4ca573-0253-4fbd-93e8-92821ee1c351.png)

### <a name="tcp-idle-time-settings"></a>TCP 유휴 시간 설정

지금까지 대부분의 경계 네트워크는 일시적 연결에 대해 구성됩니다. 즉, 유휴 연결이 일반적으로 종료됩니다. 유휴 TCP 세션은 100초에서 300초 이상으로 바이러스 백신 및 방화벽에 의해 종료될 수 있습니다. 이는 유휴 여부에 Outlook 장기 연결을 만들고 사용하기 때문에 온라인에서 문제가 됩니다.

프록시 또는 방화벽 장치에 의해 연결이 종료되면 클라이언트에 알리지 않습니다. Outlook Online을 사용하려고 하면 클라이언트 컴퓨터가 새 연결을 만들기 전에 반복적으로 연결을 다시 시도하게 됩니다. 페이지 로드 시 제품, 프롬프트 또는 성능 저하가 표시될 수 있습니다.

#### <a name="tools"></a>도구

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>찾아야 할 것

Netmon에서 시간 오프셋 필드에서 왕복을 살펴 봐야 합니다. 왕복은 클라이언트가 서버에 요청을 보내고 응답을 다시 받는 시간입니다. 클라이언트와 발신 지점(예: ) 사이를 검사합니다. Client -- Proxy) 또는 클라이언트를 \> Office 365(클라이언트 -- \> Office 365). 다양한 유형의 패킷에서 이를 볼 수 있습니다.

예를 들어 Netmon의 필터는  `.Protocol.IPv4.Address == 10.102.14.112 AND .Protocol.IPv4.Address == 10.201.114.12` 또는 Wireshark에서 와 같이 표시될 수  `ip.addr == 10.102.14.112 &amp;&amp; ip.addr == 10.201.114.12` 있습니다.

> [!TIP]
> 추적의 IP 주소가 DNS 서버에 속하는지 모르는 경우 명령줄에서 찾아보아야 합니다. 실행  \> **시작을 클릭하고** \> **cmd를** 입력하거나 Windows **키를** \> 누르고 **cmd 를 입력합니다.** 프롬프트에 를  `nslookup <the IP address from the network trace>` 입력합니다. 테스트하려면 사용자 컴퓨터의 IP 주소에 대해 nslookup을 사용하세요. > Microsoft의 IP 범위 목록을 확인하면 Office 365 및 IP 주소 범위를 [참조하세요.](./urls-and-ip-address-ranges.md)

문제가 있는 경우( 이 경우(Outlook Online) 특히 응용 프로그램 데이터의 흐름을 표시하는 TLS:TLS 패킷(예: Netmon에서 을 통해 응용 프로그램 데이터 패킷을 찾을 수 있습니다)에 긴 시간 오프셋이 표시될 것으로 예상합니다. `.Protocol.TLS AND Description == "TLS:TLS Rec Layer-1 SSL Application Data"` 세션 전체에서 시간이 매끄럽게 진행됩니다. Outlook Online을 새로 고칠 때 긴 지연이 표시되면 높은 수준의 초기화가 전송될 수 있습니다.

### <a name="latencyround-trip-time"></a>대기 시간/왕복 시간

대기 시간은 여러 변수에 따라 크게 변경될 수 있는 측정값입니다( 예: 고령 장치 업그레이드, 많은 수의 사용자를 네트워크에 추가, 네트워크 연결의 다른 작업에서 사용하는 전체 대역폭 비율).

이 네트워크 계획 및 성능 조정 페이지에서 Office 365 대한 대역폭 [계산기가](network-planning-and-performance.md) Office 365 있습니다.

연결 속도 또는 ISP 연결 대역폭을 측정해야 하나요? 이 사이트(또는 사이트와 같은 사이트): [Speedtest 공식](https://www.speedtest.net/)사이트 또는 구 속도 테스트에 대해 즐겨찾는 검색 엔진을 **쿼리합니다.**

#### <a name="tools"></a>도구

- Ping
- PsPing
- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>찾아야 할 것

추적의 대기 시간을 추적하기 위해 클라이언트 컴퓨터 IP 주소와 DNS 서버의 IP 주소를 기록한 경우 Office 365. 이는 보다 쉬운 추적 필터링을 위해 사용됩니다. 프록시를 통해 연결하는 경우 작업을 더 쉽게 만들기 위해 클라이언트 컴퓨터 IP 주소, 프록시/Office 365 IP 주소가 필요합니다.

outlook.office365.com 전송된 ping 요청은  *ping이*  연속된 ICMP 패킷을 전송하기 위해 연결할 수 없는 경우에도 요청을 받는 데이터 센터의 이름을 알려 주게 됩니다. PsPing(무료로 다운로드할 수 있는 도구)을 사용하며 포트(443)를 지정하고 IPv4(-4)를 사용하는 경우 전송된 패킷의 평균 왕복 시간을 얻게 됩니다. 이렇게 하면 처럼 Office 365 URL에 대해 이 작업을 할 수 `psping -4 yourSite.sharepoint.com:443` 있습니다. 실제로 평균적으로 더 큰 샘플을 얻을 수 있도록 여러 ping을 지정할 수 있습니다. `psping -4 -n 20 yourSite-my.sharepoint.com:443`

> [!NOTE]
> PsPing은 ICMP 패킷을 보내지 않습니다. 특정 포트를 통해 TCP 패킷으로 ping을 하여 열려 있는 것으로 알고 있는 포트를 사용할 수 있습니다. SSL/TLS를 사용하는 Office 365 PsPing에 포트 :443을 연결해 보아야 합니다.

![443이 동일한 작업을 수행하지만 평균 RTT가 6.5ms인 PSPing 및 outlook.office365.com ping을 보여주는 스크린샷입니다.](../media/c64339f2-2c96-45b8-b168-c2a060430266.PNG)

네트워크 추적을 수행하는 동안 Office 365 페이지를 로드한 경우 에 대해 Netmon 또는 Wireshark 추적을 필터링해야 `DNS` 합니다. 이는 찾고 있는 IPS 중 하나입니다.

다음은 Netmon을 필터링하여 IP 주소를 갖기 위해 수행되는 단계입니다(DNS 대기 시간 살펴보기). 이 예에서는 outlook.office365.com 사용하지만 예를 들어 SharePoint Online 테넌트의 URL을 hithere.sharepoint.com 있습니다.

1. URL을 Ping하고 결과에 ping 요청이 전송된 DNS 서버의 `ping outlook.office365.com` 이름과 IP 주소를 기록합니다.
2. 네트워크를 추적하여 페이지를 열거나 성능 문제를 줄 수 있는 작업을 수행하거나, ping 자체에서 대기 시간이 길어질 경우 해당 페이지를 추적합니다.
3. Netmon에서 추적을 열고 DNS에 대해 필터링합니다(이 필터는 Wireshark에서도 작동하지만 대소문자에 `-- dns` 민감). ping에서 DNS 서버의 이름을 알고 있는 경우 다음과 같이 Netmon에서 보다 빠르게 필터링할 수 있습니다. `DNS AND ContainsBin(FrameData, ASCII, "namnorthwest")` 는 Wireshark dns 및 frame에 "namnorthwest"가 포함되어 있습니다.<br/>응답 패킷을 열고 Netmon **Frame Details** 창에서 **DNS를** 클릭하여 자세한 내용을 확장합니다. DNS 정보에서 요청이 전송된 DNS 서버의 IP 주소를 Office 365. 다음 단계(PsPing 도구)에는 이 IP 주소가 필요합니다. 필터를 제거하고 Netmon에서 DNS **응답(Frame Summary** Find Conversations DNS)을 마우스 오른쪽 단추로 클릭하여 DNS 쿼리 및 응답을 나란히 \>  \> 봐야 합니다.
4. Netmon에서 DNS 요청과 응답 사이의 시간 오프셋 열도 메모합니다. 다음 단계에서는 ICMP가 방화벽에서 자주 차단되는 경우가 쉽기 때문에 [PsPing](/sysinternals/downloads/psping) 도구를 설치 및 사용하기가 매우 편리합니다. PsPing은 대기 시간을 밀리초만 추적하기 때문에 매우 편리합니다. PsPing은 주소 및 포트(이 경우 열린 포트 443)에 대한 TCP 연결을 완료합니다.
5. PsPing을 설치합니다.
6. 명령 프롬프트(Start \> Run type cmd 또는 Windows Key type cmd)를 열고 PsPing 명령을 실행하기 위해 PsPing을 설치한 디렉터리로 디렉터리를 \> \> 변경합니다. 내 예제에서는 C 루트에 'Perf' 폴더를 만들었다는 사실이 표시됩니다. 빠른 액세스를 위해 동일한 작업을 할 수 있습니다.
7. 이전 Netmon 추적의 Office 365 DNS 서버의 IP 주소(예: 포트 번호)에 대해 PsPing을 만들 수 있도록 명령을 `psping -n 20 132.245.24.82:445` 입력합니다. 이렇게 하면 20개 ping 샘플링이 제공되어 PsPing이 중지될 때 대기 시간이 평균됩니다.

프록시 서버를 Office 365 단계가 약간 다릅니다. 먼저 프록시 서버에 PsPing을 실행하여 평균 대기 시간 값을 밀리초(밀리초)로 확인한 다음 프록시 또는 직접 인터넷에 연결되어 있는 컴퓨터에서 PsPing을 실행하여 누락된 값(Office 365 및 뒤로)을 얻습니다.

프록시에서 PsPing을 실행하기로 선택한 경우 클라이언트 컴퓨터와 프록시 서버 또는 전송 지점의 두밀리초 값, 그리고 프록시 서버를 프록시 서버로 Office 365. 완료했습니다! 아무리 까다로우면 값을 기록합니다.

인터넷에 직접 연결되어 있는 다른 클라이언트 컴퓨터에서 PsPing을 실행하면(즉, 프록시가 없는 경우) 클라이언트 컴퓨터와 프록시 서버 또는 전송 지점에 대한 클라이언트 컴퓨터의 2밀리초 값이 Office 365. 이 경우 클라이언트 컴퓨터의 값에서 Office 365 서버로의 프록시 서버 또는 발신 지점으로 클라이언트 컴퓨터의 값을 빼고 클라이언트 컴퓨터에서 프록시 서버 또는 발신 지점으로 RTT 번호를 뺄 수 있으며, 프록시 서버나 발신 지점에서 프록시를 Office 365.

그러나 직접 연결되거나 프록시를 우회하는 영향을 미치는 위치에서 클라이언트 컴퓨터를 찾을 수 있는 경우 문제가 해당 위치에서 재현되어 있는지를 보고 그 후 해당 컴퓨터를 사용하여 테스트할 수 있습니다.

Netmon 추적에 나타남과 같은 대기 시간은 주어진 세션에 충분한 경우 추가될 수 있는 시간(밀리초)입니다.

![프레임 요약에 Netmon 기본 시간 변화량 열이 추가된 Netmon의 일반 대기 시간입니다.](../media/7ad17380-8527-4bc2-9b9b-6310cf19ba6b.PNG)

> [!NOTE]
> IP 주소가 여기에 표시된 IP와 다를 수 있습니다. 예를 들어 ping은 157.56.0.0/16 또는 유사한 범위를 반환할 수 있습니다. 이 목록에 사용되는 범위 목록은 Office 365 및 IP 주소 Office 365 를 [확인하세요.](./urls-and-ip-address-ranges.md)

132.245와 같은 검색하려는 경우 모든 노드를 확장해야 합니다(이 경우 맨 위에 단추가 있습니다).

### <a name="proxy-authentication"></a>프록시 인증

이 설정은 프록시 서버를 사용하는 경우만 적용됩니다. 그렇지 않은 경우 이러한 단계를 건너뛸 수 있습니다. 제대로 작동하면 프록시 인증이 지속적으로 밀리초만에 이행됩니다. 예를 들어 사용량이 많은 기간 동안에는 성능이 간헐적으로 좋지 않습니다.

프록시 인증이 설정되어 있는 경우 새 TCP 연결을 설정하여 정보를 Office 365 때마다 인증 프로세스를 뒤에서 통과해야 합니다. 따라서 예를 들어 온라인에서 일정에서 메일로 Outlook 인증합니다. 또한 SharePoint Online에서 페이지에 여러 사이트 또는 위치의 미디어 또는 데이터가 표시될 경우 데이터를 렌더링하는 데 필요한 서로 다른 각 TCP 연결에 대해 인증합니다.

Outlook Online에서는 일정과 사서함 간에 전환할 때마다 로드 시간이 느려지거나 온라인에서 페이지 로드가 느려질 SharePoint 있습니다. 그러나 여기에 나열되지 않은 다른 증상이 있습니다.

프록시 인증은 프록시 서버의 설정입니다. 이로 인해 성능 문제가 Office 365 네트워킹 팀에 문의해야 합니다.

#### <a name="tools"></a>도구

- Netmon
- Wireshark

#### <a name="what-to-look-for"></a>찾아야 할 것

일반적으로 서버에서 파일이나 정보를 요청하거나 정보를 제공하려면 새 TCP 세션을 시작해야 할 때마다 프록시 인증이 실행됩니다. 예를 들어 HTTP GET 또는 HTTP POST 요청에 대한 프록시 인증이 표시될 수 있습니다. 추적에서 요청을 인증하는 프레임을 확인하려는 경우 Netmon에 'NTLMSSP Summary' 열을 추가하고 에 대해  `.property.NTLMSSPSummary` 필터링합니다. 인증에 얼마나 오래 들이고, 시간 델타 열을 추가합니다.

Netmon에 열을 추가합니다.

1. 설명과 같은 열을 마우스 오른쪽 단추로 **클릭합니다.**
2. 열 **선택 을 클릭합니다.**
3. 목록에서 _NTLMSSP_  요약 및 시간 델타를 찾고 추가를 **클릭합니다.**
4. 새 열을 설명 열 앞이나  뒤로 이동하여 나란히 읽을 수 있습니다.
5. **확인** 을 클릭합니다.

열을 추가하지 않은 경우에도 Netmon 필터가 작동됩니다. 하지만 어떤 인증 단계가 필요한지 확인하면 문제 해결이 훨씬 더 쉬워집니다.

프록시 인증의 인스턴스를 찾는 경우 NTLM 챌린지가 있는 모든 프레임 또는 인증 메시지가 있는 프레임을 연구해야 합니다. 필요한 경우 특정 트래픽 조각을 마우스 오른쪽 단추로 클릭하고 대화 \> TCP 찾기를 클릭합니다. 이러한 대화의 시간 델타 값에 유의해야 합니다.

![대화를 통해 필터링된 프록시 인증을 보여주는 Netmon 추적입니다.](../media/b640f176-0a52-4bbb-972e-60fb3d6aece2.PNG)

Wireshark에 있는 프록시 인증의 4초 지연 표시된  이전 프레임 열의 시간 델타는 프레임 세부 정보에서 같은 이름의 필드를 마우스 오른쪽 단추로 클릭하고 열로 추가를 선택하면 됩니다.  <br/> ![Wireshark에서 프레임 세부 정보에서 같은 이름의 필드를 마우스 오른쪽 단추로 클릭하고 열로 추가를 선택하여 '표시된 이전 프레임의 시간 델타' 열을 만들 수 있습니다.](../media/f5b7bde4-8067-4ee0-bc7f-e9062ce1ba6f.PNG)

### <a name="dns-performance"></a>DNS 성능

이름 확인은 클라이언트의 국가에 최대한 가깝게 진행할 때 가장 빠르고 가장 빠르게 작동합니다.

DNS 이름 확인이 몇 초 남지 않으면 페이지 로드에 초를 추가할 수 있습니다. 이상적으로는 이름 확인이 100ms 미만으로 진행됩니다. 그렇지 않은 경우 추가 조사를 해야 합니다.

> [!TIP]
> 클라이언트 연결의 작동 방식이 어떻게 Office 365? 여기에서 클라이언트 연결 참조 문서를 [살펴보세요.](/previous-versions//dn741250(v=technet.10))

#### <a name="tools"></a>도구

- Netmon
- Wireshark
- PsPing

#### <a name="what-to-look-for"></a>찾아야 할 것

DNS 성능 분석은 일반적으로 네트워크 추적을 위한 또 다른 작업입니다. 그러나 PsPing은 가능한 원인을 판결하거나 내보는 데에도 유용합니다.

DNS 트래픽은 TCP를 기반으로 하며, UDP 요청 및 응답은 특정 요청과 특정 응답을 일치하도록 도와주는 ID로 명확하게 표시됩니다. 예를 들어 SharePoint Online에서 웹 페이지의 네트워크 이름 또는 URL을 사용하는 경우 DNS 트래픽이 표시됩니다. 일반적으로 이 트래픽은 영역 전송을 제외한 대부분의 트래픽이 UDP를 통해 실행됩니다.

Netmon과 Wireshark 둘 다에서 DNS 트래픽을 확인할 수 있는 가장 기본적인 필터는 `dns` 간단합니다. 필터를 지정할 때 소문자만 사용해야 합니다. 클라이언트 컴퓨터에서 문제를 재현하기 전에 DNS 확인자 캐시를 플러시해야 합니다. 예를 들어 홈 페이지에 대해 SharePoint Online 페이지 로드 속도가 느리면 모든 브라우저를 닫고, 새 브라우저를 열고, 추적을 시작하고, DNS 확인자 캐시를 플러시한 다음 SharePoint Online 사이트로 이동해야 합니다. 전체 페이지가 확인되면 추적을 중지하고 저장해야 합니다.

![Netmon에서 DNS에 대한 기본 필터는 DNS입니다.](../media/1bebc118-ca13-45f3-803f-ab73e7af401d.png)

여기서 시간 오프셋을 살펴보고자 합니다. 또한 다음 단계를 완료하여  할 수 있는 Netmon에 시간 델타 열을 추가하는 것이 유용할 수 있습니다.

1. 설명과 같은 열을 마우스 오른쪽 단추로 **클릭합니다.**
2. 열 **선택 을 클릭합니다.**
3. 목록에서 _시간 델타를_ 찾고 추가를 **클릭합니다.**
4. 새 열을 설명 열 앞이나 뒤로 이동하여 나란히 읽을 수 있도록 합니다. 
5. **확인** 을 클릭합니다.

관심 있는 쿼리를 찾은 경우 프레임 세부 정보 패널에서 해당 쿼리를 마우스 오른쪽 단추로 클릭하고 대화 DNS 찾기 를 선택하여 쿼리를 **차단하는 것이** \> **있습니다.** 네트워크 대화 패널은 UDP 트래픽 로그에서 특정 대화로 바로 이동됩니다.

![DNS를 Outlook 온라인 부하를 필터링한 다음 DNS를 사용하여 결과의 범위를 좁히는 Netmon 추적입니다.](../media/763cf20e-7b48-4a37-9449-c9978cfe118b.PNG)

Wireshark에서 DNS 시간 열을 만들 수 있습니다. Wireshark에서 추적(또는 추적 열기)을 사용하여 또는 보다 `dns` 유용하게  `dns.time` 필터링합니다. DNS 쿼리를 클릭하고 세부 정보를 표시하는 패널에서 세부 정보를  `Domain Name System (response)` 확장합니다. 시간 필드가 표시 됩니다(예: `[Time: 0.001111100 seconds]` ). 이번을 마우스 오른쪽 단추로 클릭하고 **열로 적용을 선택합니다.** 이렇게 하면 추적을 **더** 빠르게 정렬할 수 있는 시간 열이 표시됩니다. 새 열을 클릭하여 내선 값을 정렬하여 확인에 가장 오래 걸려진 DNS 호출을 확인할 수 있습니다.

[dns.time(소문자)에 의해 Wireshark에서 필터링되며 열에 적용된 세부 수준의 시간을 사용하고 오름차순으로 정렬되는 SharePoint Online 찾아보기입니다.](../media/1439dcc2-12ff-4ee2-9ef3-1484cf79c384.PNG)

DNS 확인 시간을 더 조사하려는 경우 TCP에서 사용하는 DNS 포트(예: )에 대해 PsPing을  `psping <IP address of DNS server>:53` 시도합니다. 성능 문제가 계속 표시하나요? 이 경우 해결을 위해 타격을 미치고 있는 특정 DNS 응용 프로그램의 문제보다 더 광범위한 네트워크 문제일 가능성이 까다로워질 수 있습니다. 또한 outlook.office365.com ping을 통해 Outlook Online에 대한 DNS 이름 확인이 진행되는 위치(예: outlook-namnorthwest.office365.com)를 알려 줄 수도 있습니다.

문제가 DNS 관련 문제로 보이는 경우 IT 부서에 문의하여 DNS 구성 및 DNS 전달자에 문의하여 이 문제를 추가로 조사해야 할 수 있습니다.

### <a name="proxy-scalability"></a>프록시 확장성

Outlook Online과 같은 Office 365 여러 장기 연결을 클라이언트에 부여합니다. 따라서 각 사용자는 더 긴 수명을 요구하는 더 많은 연결을 사용할 수 있습니다.

#### <a name="tools"></a>도구

수학

#### <a name="what-to-look-for"></a>찾아야 할 것

이에 대한 네트워크 추적 또는 문제 해결 도구는 없습니다. 대신 제한 사항 및 기타 변수에 따라 대역폭 계산을 기반으로 합니다.

### <a name="tcp-max-segment-size"></a>TCP 최대 세그먼트 크기

SYN - SYN/ACK에 있습니다.  이 작업을 수행하여 TCP 패킷이 가능한 최대 데이터 양을 수행하도록 구성되도록 구성한 성능 네트워크 추적을 확인합니다.

목표는 데이터 전송을 위해 1460비트의 MSS를 보는 것입니다. 프록시 뒤에 있는 경우 또는 NAT를 사용하는 경우 이 테스트를 클라이언트에서 프록시/egress/NAT로, 프록시/egress/NAT에서 최상의 결과를 Office 365 합니다. 이러한 세션은 서로 다른 TCP 세션입니다.

#### <a name="tools"></a>도구

Netmon

#### <a name="what-to-look-for"></a>찾아야 할 것

TCP MSS(최대 세그먼트 크기)는 네트워크 추적에서 3차원 핸드세이크의 또 다른 매개 변수입니다. 즉, SYN - SYN/ACK 패킷에서 필요한 데이터를 찾을 수 있습니다. MSS는 실제로 보기가 매우 간단합니다.

성능 네트워크 추적을 열고 원하는 연결을 찾거나 성능 문제를 보여줄 수 있습니다.

> [!NOTE]
> 추적을 보고 대화와 관련된 트래픽을 찾아야 하는 경우 클라이언트의 IP 또는 프록시 서버의 IP나 발신 지점 또는 둘 다를 필터링합니다. 직접 이동을 수행하려면 추적의 IP 주소에 대해 테스트할 URL을 Office 365 필터링해야 합니다.

중도 추적을 보고 있나요? 필터를 사용하여 방향을 정해 보세요. Netmon에서 처럼 URL에 따라 검색을 실행합니다. `Containsbin(framedata, ascii, "sphybridExample")` 프레임 번호를 확인합니다.

Wireshark에서 와 같은 기능을 사용  `frame contains "sphybridExample"` 합니다. RWS(원격 Winsock) 트래픽을 찾은 경우(Wireshark에서 [PSH, ACK]로 표시될 수 있습니다.) RWS 연결은 앞서 설명한 대로 관련 SYN - SYN/ACK 바로 전에 볼 수 있습니다.

이제 프레임 번호를 기록하고, 필터를 놓고,  Netmon의 네트워크 대화 창에서 모든 트래픽을 클릭하여 가장 가까운 SYN을 볼 수 있습니다.

중요하게, 추적 시 IP 주소 정보를 받지 못하면 추적에서 URL(예: 의 일부)을 검색하면 필터링할 IP 주소가 `sphybridExample-my.sharepoint.com` 표시됩니다.

보시고자 하는 추적에서 연결을 찾습니다. 추적을 검색하거나 IP 주소로 필터링하거나 Netmon의 네트워크 대화 창을 사용하여 특정 대화 ID를 선택하여 이 작업을 할 수 있습니다. SYN 패킷을 찾은 후 프레임 세부 정보 패널에서 TCP(Netmon) 또는 Transmission Control Protocol(Wireshark)을 확장합니다. TCP 옵션 및 MaxSegmentSize를 확장합니다. 관련 SYN-ACK 프레임을 찾고 TCP 옵션 및 MaxSegmentSize를 확장합니다. 두 값 중 작은 값은 최대 세그먼트 크기가 됩니다. 이 그림에서는 TCP 문제 해결이라는 Netmon의 기본 제공 Column을 활용합니다.

![기본 제공 열을 사용하여 Netmon에서 필터링된 네트워크 추적입니다.](../media/e073df13-71f8-497a-83b4-bb9f70bd9833.PNG)

기본 제공 열은 프레임 세부 정보 **패널의 맨 위에** 있습니다. (기본 보기로 다시 전환하려면 **열을** 다시 클릭한 다음 표준 시간대를 **선택하세요.)**

![TCP 문제 해결 옵션에 대한 열 드롭다운을 찾는 위치(프레임 요약 맨 위)입니다.](../media/64fd4baa-a872-4f07-b959-752d7d37fd62.PNG)

다음은 Wireshark의 필터링된 추적입니다. MSS 값()에 대한 필터가 `tcp.options.mss` 있습니다. SYN, SYN/ACK, ACK 핸드셰이크의 프레임은 프레임 세부 정보(프레임 47 ACK, 46 SYN/ACK 링크, 43 SYN에 연결)에 해당하는 Wireshark의 아래쪽에 연결하여 이러한 종류의 작업을 보다 쉽게 할 수 있도록 합니다.

![MSS(최대 세그먼트 크기)에 대해 tcp.options.mss를 통해 Wireshark에서 필터링된 추적입니다.](../media/51e278db-801b-48bc-9b68-87cf92f03fd6.PNG)

선택적 확인(이 매트릭스의 다음 항목)을 선택해야 하는 경우 추적을 닫지 않습니다! 

### <a name="selective-acknowledgment"></a>선택적 인정

SYN - SYN/ACK에 있습니다. SYN 및 SYN/ACK에서 모두 허용된 것으로 보고해야 합니다. SACK(선택적 확인)을 사용하면 패킷 또는 패킷이 누락될 때 데이터를 더 원활하게 다시 전송할 수 있습니다. 장치에서 이 기능을 사용하지 않도록 설정하면 성능 문제가 발생할 수 있습니다.

프록시 뒤에 있는 경우 또는 NAT를 사용하는 경우 이 테스트를 클라이언트에서 프록시/egress/NAT로, 프록시/egress/NAT에서 최상의 결과를 Office 365 합니다. 이러한 세션은 서로 다른 TCP 세션입니다.

#### <a name="tools"></a>도구

Netmon

#### <a name="what-to-look-for"></a>찾아야 할 것

SACK(선택적 Acknowledgment)은 SYN-SYN/ACK 핸드세이크의 또 다른 매개 변수입니다. SYN - SYN/ACK에 대한 추적을 여러 가지 방법으로 필터링할 수 있습니다.

추적을 검색하거나, IP 주소로 필터링하거나, Netmon의 네트워크 대화 창을 사용하여 대화 ID를 클릭하여 확인에 관심이 있는 추적에서 연결을 찾습니다. SYN 패킷을 찾은 후 프레임 세부 정보 섹션에서 Netmon의 TCP 또는 Wireshark의 Transmission Control Protocol을 확장합니다. TCP 옵션을 확장한 다음 SACK을 확장합니다. 관련 SYN-ACK 프레임을 찾고 TCP 옵션 및 해당 SACK 필드를 확장합니다. 특정 SACK이 SYN과 SYN/ACK에서 모두 허용되어 있도록 합니다. 다음은 Netmon 및 Wireshark 둘 다에 있는 SACK 값입니다.

![tcp.flags.syn == 1의 결과로 Netmon의 SACK(선택적 Acknowledgment)입니다.](../media/216f556f-5031-4ed2-b066-a0d9b3251fa2.PNG)

![필터 tcp.flags.syn == 1일 때의 Wireshark에 표시된 것과 같은 SACK입니다.](../media/0a6e26e5-43dc-403b-adc9-3349a55f4e4b.PNG)

### <a name="dns-geolocation"></a>DNS 지리적 위치

전 세계 Office 365 DNS 통화를 해결하면 연결 속도가 향상됩니다.

Outlook Online에서는 첫 번째 DNS 검색이 완료된 후 해당 DNS의 위치를 사용하여 가장 가까운 데이터 센터에 연결합니다. 백본 네트워크를 사용하여 데이터가 저장된 dC(데이터 센터)에 연결하는 Outlook 온라인 CAS 서버에 연결됩니다. 이 속도가 빨라집니다.

SharePoint Online에 액세스할 때 해외로 출장하는 사용자는 활성 데이터 센터로 이동됩니다. 즉, 해당 위치가 SPO 테넌트의 홈 기반(미국에 기반을 두는 경우 미국의 dC)으로 이동됩니다.

Lync Online에는 한에 두 개 이상의 dC에 활성 노드가 있습니다. Lync Online 인스턴스에 대한 요청이 전송될 때 Microsoft의 DNS는 요청이 어디에서 왔는지 결정하고 Lync online이 활성 상태인 가장 가까운 지역 dC에서 IP 주소를 반환합니다.

> [!TIP]
> 클라이언트가 클라이언트에 연결하는 방법에 대해 더 Office 365? 클라이언트 연결 참조 [](/previous-versions//dn741250(v=technet.10)) 문서 및 유용한 그래픽을 살펴보아야 합니다.

#### <a name="tools"></a>도구

- Ping
- PsPing

#### <a name="what-to-look-for"></a>찾아야 할 것

클라이언트의 DNS 서버에서 Microsoft의 DNS 서버로의 이름 확인을 요청하는 경우 대부분의 경우 Microsoft DNS는 지역별 데이터 센터(dC)의 IP 주소를 반환합니다. 이것이 어떤 의미인가요? 본사가 인도 방글라데시에 있지만 사용자가 미국으로 출장하는 경우 브라우저에서 Outlook Online에 대한 요청을 할 때 Microsoft의 DNS 서버는 미국의 데이터 센터에 IP 주소를 제공해야 합니다. 메일이 필요한 경우 Outlook 데이터 센터 간에 Microsoft의 빠른 백본 네트워크를 통해 이동됩니다.

이름 확인이 사용자 위치에 최대한 가깝게 수행된 경우 DNS가 가장 빠르게 작동합니다. 유럽에 있는 경우 유럽의 Microsoft DNS로 이동하여 이상적으로 유럽의 데이터 센터를 거래하고 싶을 것입니다. 유럽의 클라이언트에서 DNS로, 미국의 데이터 센터로의 성능은 더 느립니다.

DNS 요청이 라우팅되는 outlook.office365.com 위치를 확인하려면 Ping 도구를 실행합니다. 유럽에 있는 경우 사용자와 같은 회신이 outlook-emeawest.office365.com. 미국에서는 365와 같은 outlook-namnorthwest.office365.com.

클라이언트 컴퓨터에서 명령 프롬프트를 여는 경우(시작 실행 cmd 또는 키 \> \> Windows \> cmd를 통해). ping을 outlook.office365.com Enter를 누를 수 있습니다. IPv4를 통해 ping을 지정하려는 경우 -4를 지정해야 합니다. ICMP 패킷에서 회신을 얻지 못할 수 있지만 요청이 라우팅된 DNS의 이름이 표시됩니다. 이 연결의 대기 시간 번호를 확인하려는 경우 ping에서 반환되는 서버의 IP 주소로 PsPing을 시도합니다.

![outlook-namnorthwest의 해상도를 보여 주는 outlook.office365.com Ping입니다.](../media/06c944d5-6159-43ec-aa31-757770695e8b.PNG)

![ping에서 반환된 IP 주소로 PSPing을 outlook.office365.com 28밀리초의 대기 시간을 보여 주며,](../media/f2b25a75-1a87-4479-b8a7-fa4375683507.PNG)

### <a name="office-365-application-troubleshooting"></a>Office 365 응용 프로그램 문제 해결

#### <a name="tools"></a>도구

- Netmon
- HTTPWatch
- 브라우저의 F12 콘솔

이 네트워크 관련 문서에서는 응용 프로그램별 문제 해결에 사용되는 도구에 대해 다루지 않습니다. 그러나 이 페이지에서 사용할 수 *있는* 리소스를 찾을 [수 있습니다.](https://support.office.com/article/Network-planning-and-performance-tuning-for-Office-365-e5f1228c-da3c-4654-bf16-d163daee8848)

## <a name="related-topics"></a>관련 항목

[Office 365 끝점 관리](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Office 365 끝점 FAQ](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)