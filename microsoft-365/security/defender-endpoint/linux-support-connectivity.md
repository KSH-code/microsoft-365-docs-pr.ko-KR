---
title: Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
ms.reviewer: ''
description: Linux에서 끝점용 Microsoft Defender의 클라우드 연결 문제를 해결하는 방법에 대해 자세히 알아보기
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 클라우드, 연결, 통신
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4f547e6701e0b22c2d55d0fa68a236f85b821a11
ms.sourcegitcommit: 43adb0d91af234c34e22d450a9c1d26aa745c2ca
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/19/2021
ms.locfileid: "60478916"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a>Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a>연결 테스트 실행

Linux의 끝점용 Defender가 현재 네트워크 설정을 사용하여 클라우드와 통신할 수 있는지 테스트하려면 명령줄에서 연결 테스트를 실행합니다.

```bash
mdatp connectivity test
```

예상 출력:

```output
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

연결 테스트가 실패하면 장치에 인터넷에 액세스할 수 [](microsoft-defender-endpoint-linux.md#network-connections) 있는지와 제품에 필요한 끝점이 프록시 또는 방화벽에 의해 차단되어 있는지 확인합니다.

오류 컬 오류 35 또는 60, 인증서 고정 거부를 나타냅니다. 연결이 SSL 또는 HTTPS 검사에 속하는지 확인합니다. 그렇다면 허용 목록에 끝점용 Microsoft Defender를 추가합니다.

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a>프록시가 없는 환경 또는 투명 프록시를 사용하는 환경의 문제 해결 단계

프록시가 없는 환경에서 또는 투명한 프록시를 사용하여 연결이 차단되지 않는지 테스트하기 위해 터미널에서 다음 명령을 실행합니다.

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

이 명령의 출력은 다음과 유사해야 합니다.

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a>정적 프록시를 사용하는 환경에 대한 문제 해결 단계

> [!WARNING]
> PAC, WPAD 및 인증된 proxies는 지원되지 않습니다. 정적 프록시 또는 투명 프록시만 사용 중이지 않도록 합니다.
>
> 보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다. SSL 검사 및 프록시 서버에 대한 예외를 구성하여 Linux 끝점용 Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달합니다. 전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.

정적 프록시가 필요한 경우 프록시 주소 및 포트에 해당하는 위의 명령에 proxy 매개 `proxy_address:port` 변수를 추가합니다.

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

파일에 구성된 동일한 프록시 주소와 포트를 사용하는지 `/lib/system/system/mdatp.service` 확인 위의 명령에서 오류가 있는 경우 프록시 구성을 검사합니다.

mdatp에 대한 프록시를 설정하기 위해 다음 명령을 사용 합니다.

```bash
mdatp config proxy set --value http://address:port 
```


성공하면 명령줄에서 다른 연결 테스트를 시도합니다.

```bash
mdatp connectivity test
```

문제가 계속되면 고객 지원에 문의합니다.

## <a name="resources"></a>리소스

- 정적 프록시를 사용하도록 제품을 구성하는 방법에 대한 자세한 내용은 정적 프록시 검색을 위해 [끝점용 Microsoft Defender 구성을 참조하세요.](linux-static-proxy-configuration.md)
