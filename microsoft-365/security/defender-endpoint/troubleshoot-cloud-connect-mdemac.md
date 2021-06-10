---
title: MacOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
description: 이 항목에서는 macOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제를 해결하는 방법을 설명합니다.
keywords: microsoft, defender, Endpoint용 Microsoft Defender, mac, 설치, 배포, 제거, intune, jamf, macos, catalina, mojave, high sierra
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 291cd3016dcb4e1a321f39b4d2731ce2068b6544
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935212"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="1e74b-104">MacOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="1e74b-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="1e74b-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="1e74b-105">**Applies to:**</span></span>
- [<span data-ttu-id="1e74b-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="1e74b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1e74b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1e74b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

<span data-ttu-id="1e74b-108">**플랫폼** macOS</span><span class="sxs-lookup"><span data-stu-id="1e74b-108">**Platform** macOS</span></span>

<span data-ttu-id="1e74b-109">이 항목에서는 macOS의 끝점용 Microsoft Defender에 대한 클라우드 연결 문제를 해결하는 방법을 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-109">This topic describes how to Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="run-the-connectivity-test"></a><span data-ttu-id="1e74b-110">연결 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="1e74b-110">Run the connectivity test</span></span>
<span data-ttu-id="1e74b-111">Mac의 끝점용 Defender가 현재 네트워크 설정을 사용하여 클라우드와 통신할 수 있는지 테스트하려면 명령줄에서 연결 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-111">To test if Defender for Endpoint on Mac can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```Bash
mdatp connectivity test
```

<span data-ttu-id="1e74b-112">예상 출력:</span><span class="sxs-lookup"><span data-stu-id="1e74b-112">expected output:</span></span>
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

<span data-ttu-id="1e74b-113">연결 테스트가 실패하면 장치에 인터넷에 액세스할 수 [](microsoft-defender-endpoint-mac.md#network-connections) 있는지와 제품에 필요한 끝점이 프록시 또는 방화벽에 의해 차단되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-mac.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="1e74b-114">오류 컬링 오류 35 또는 60은 인증서 고정 거부를 나타내며 이는 SSL 또는 HTTPS 검사에서 발생할 수 있는 문제를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-114">Failures with curl error 35 or 60 indicate certificate pinning rejection, which indicates a potential issue with SSL or HTTPS inspection.</span></span> <span data-ttu-id="1e74b-115">SSL 검사 구성에 대한 아래 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="1e74b-115">See instructions below regarding SSL inspection configuration.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-proxy-autoconfig-pac-or-with-web-proxy-autodiscovery-protocol-wpad"></a><span data-ttu-id="1e74b-116">프록시가 없는 환경이나 PAC(프록시 자동 구성) 또는 WPAD(웹 프록시 자동 검색 프로토콜)를 사용하는 환경의 문제 해결 단계</span><span class="sxs-lookup"><span data-stu-id="1e74b-116">Troubleshooting steps for environments without proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD)</span></span>
<span data-ttu-id="1e74b-117">다음 절차에 따라 프록시가 없는 환경이나 PAC(프록시 자동 구성) 또는 WPAD(웹 프록시 자동 검색 프로토콜)를 사용하는 환경에서 연결이 차단되지 않는지 테스트합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-117">Use the following procedure to test that a connection is not blocked in an environment without a proxy or with Proxy autoconfig (PAC) or with Web Proxy Autodiscovery Protocol (WPAD).</span></span>

<span data-ttu-id="1e74b-118">프록시 또는 방화벽에서 익명 트래픽을 차단하는 경우 이전에 나열된 URL에서 익명 트래픽이 허용되어 있는지 확인</span><span class="sxs-lookup"><span data-stu-id="1e74b-118">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span>

> [!WARNING]
> <span data-ttu-id="1e74b-119">인증된 proxies는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-119">Authenticated proxies are not supported.</span></span> <span data-ttu-id="1e74b-120">PAC, WPAD 또는 정적 프록시만 사용 중이지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-120">Ensure that only PAC, WPAD, or a static proxy is being used.</span></span> <span data-ttu-id="1e74b-121">보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-121">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="1e74b-122">MacOS용 끝점용 Microsoft Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달하도록 SSL 검사 및 프록시 서버에 대한 예외를 구성합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-122">Configure an exception for SSL inspection and your proxy server to directly pass through data from Microsoft Defender for Endpoint on macOS to the relevant URLs without interception.</span></span> <span data-ttu-id="1e74b-123">전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-123">Adding your interception certificate to the global store will not allow for interception.</span></span>
<span data-ttu-id="1e74b-124">연결이 차단되지 않는지 테스트하기 위해: Mac 또는 Safari용 Microsoft Edge 같은 브라우저에서 및 https://x.cp.wd.microsoft.com/api/report https://cdn.x.cp.wd.microsoft.com/ping 를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-124">To test that a connection is not blocked: In a browser such as Microsoft Edge for Mac or Safari open https://x.cp.wd.microsoft.com/api/report and https://cdn.x.cp.wd.microsoft.com/ping.</span></span>

<span data-ttu-id="1e74b-125">터미널에서 선택적으로 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-125">Optionally, in Terminal, run the following command:</span></span>

```Bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping' 
```

<span data-ttu-id="1e74b-126">이 명령의 출력은 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="1e74b-126">The output from this command should be similar to:</span></span>
```bash
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```
