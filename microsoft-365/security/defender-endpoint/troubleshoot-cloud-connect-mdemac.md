---
title: MacOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
description: 이 항목에서는 macOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제를 해결하는 방법을 설명합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, catalina, mojave, high sierra
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: fab06ce2d221d08aac57d9c6873e255fca5a7627
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60151809"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a>MacOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼** macOS

이 항목에서는 macOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제를 해결하는 방법을 설명합니다.

## <a name="run-the-connectivity-test"></a>연결 테스트 실행
Mac의 끝점용 Defender가 현재 네트워크 설정을 사용하여 클라우드와 통신할 수 있는지 테스트하려면 명령줄에서 연결 테스트를 실행합니다.

```Bash
mdatp connectivity test
```

예상 출력:
```Bash
Testing connection with https://cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://eu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://wu-cdn.x.cp.wd.microsoft.com/ping ... [OK]
Testing connection with https://x.cp.wd.microsoft.com/api/report ... [OK]
Testing connection with https://winatp-gw-cus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-eus.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-weu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-neu.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-ukw.microsoft.com/test ... [OK]
Testing connection with https://winatp-gw-uks.microsoft.com/test ... [OK]
Testing connection with https://eu-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://us-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://uk-v20.events.data.microsoft.com/ping ... [OK]
Testing connection with https://v20.events.data.microsoft.com/ping ... [OK]
```

연결 테스트가 실패하면 장치에 인터넷에 액세스할 수 [](microsoft-defender-endpoint-mac.md#network-connections) 있는지와 제품에 필요한 끝점이 프록시 또는 방화벽에 의해 차단되어 있는지 확인합니다.

오류 컬링 오류 35 또는 60은 인증서 고정 거부를 나타내며 이는 SSL 또는 HTTPS 검사에서 발생할 수 있는 문제를 나타냅니다. SSL 검사 구성에 대한 아래 지침을 참조하세요.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a>프록시가 없는 환경이나 PAC(프록시 자동 구성) 또는 WPAD(웹 프록시 자동 검색 프로토콜)를 사용하는 환경의 문제 해결 단계
다음 절차에 따라 프록시가 없는 환경이나 PAC(프록시 자동 구성) 또는 WPAD(웹 프록시 자동 검색 프로토콜)를 사용하는 환경에서 연결이 차단되지 않는지 테스트합니다.

프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인

> [!WARNING]
> 인증된 proxies는 지원되지 않습니다. PAC, WPAD 또는 정적 프록시만 사용 중이지 않습니다. 보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다. MacOS용 끝점용 Microsoft Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달하도록 SSL 검사 및 프록시 서버에 대한 예외를 구성합니다. 전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.
연결이 차단되지 않는지 테스트하기 위해: Mac 또는 Safari용 Microsoft Edge 같은 브라우저에서 및 https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping 를 사용합니다.

터미널에서 선택적으로 다음 명령을 실행합니다.

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

이 명령의 출력은 다음과 유사해야 합니다.
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
