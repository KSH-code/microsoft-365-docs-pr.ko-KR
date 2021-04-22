---
title: Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
ms.reviewer: ''
description: Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, linux, 클라우드, 연결, 통신
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0345d7f88d147abb750e66a5e61f516abf38d553
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933112"
---
# <a name="troubleshoot-cloud-connectivity-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b46a4-104">Linux에서 끝점용 Microsoft Defender에 대한 클라우드 연결 문제 해결</span><span class="sxs-lookup"><span data-stu-id="b46a4-104">Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b46a4-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="b46a4-105">**Applies to:**</span></span>
- [<span data-ttu-id="b46a4-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b46a4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b46a4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b46a4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b46a4-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="b46a4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b46a4-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="run-the-connectivity-test"></a><span data-ttu-id="b46a4-110">연결 테스트 실행</span><span class="sxs-lookup"><span data-stu-id="b46a4-110">Run the connectivity test</span></span>

<span data-ttu-id="b46a4-111">Linux의 끝점용 Defender가 현재 네트워크 설정을 사용하여 클라우드와 통신할 수 있는지 테스트하려면 명령줄에서 연결 테스트를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-111">To test if Defender for Endpoint on Linux can communicate to the cloud with the current network settings, run a connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="b46a4-112">예상 출력:</span><span class="sxs-lookup"><span data-stu-id="b46a4-112">expected output:</span></span>

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

<span data-ttu-id="b46a4-113">연결 테스트가 실패하면 장치에 인터넷에 액세스할 수 [](microsoft-defender-endpoint-linux.md#network-connections) 있는지와 제품에 필요한 끝점이 프록시 또는 방화벽에 의해 차단되어 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-113">If the connectivity test fails, check if the device has Internet access and if [any of the endpoints required by the product](microsoft-defender-endpoint-linux.md#network-connections) are blocked by a proxy or firewall.</span></span>

<span data-ttu-id="b46a4-114">오류 컬 오류 35 또는 60, 인증서 고정 거부를 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-114">Failures with curl error 35 or 60, indicate certificate pinning rejection.</span></span> <span data-ttu-id="b46a4-115">연결이 SSL 또는 HTTPS 검사에 속하는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-115">Please check if the connection is under SSL or HTTPS inspection.</span></span> <span data-ttu-id="b46a4-116">그렇다면 허용 목록에 끝점용 Microsoft Defender를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-116">If so, add Microsoft Defender for Endpoint to the allow list.</span></span>

## <a name="troubleshooting-steps-for-environments-without-proxy-or-with-transparent-proxy"></a><span data-ttu-id="b46a4-117">프록시가 없는 환경 또는 투명 프록시를 사용하는 환경의 문제 해결 단계</span><span class="sxs-lookup"><span data-stu-id="b46a4-117">Troubleshooting steps for environments without proxy or with transparent proxy</span></span>

<span data-ttu-id="b46a4-118">프록시가 없는 환경에서 또는 투명한 프록시를 사용하여 연결이 차단되지 않는지 테스트하기 위해 터미널에서 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-118">To test that a connection is not blocked in an environment without a proxy or with a transparent proxy, run the following command in the terminal:</span></span>

```bash
curl -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="b46a4-119">이 명령의 출력은 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-119">The output from this command should be similar to:</span></span>

```Output
OK https://x.cp.wd.microsoft.com/api/report
OK https://cdn.x.cp.wd.microsoft.com/ping
```

## <a name="troubleshooting-steps-for-environments-with-static-proxy"></a><span data-ttu-id="b46a4-120">정적 프록시를 사용하는 환경에 대한 문제 해결 단계</span><span class="sxs-lookup"><span data-stu-id="b46a4-120">Troubleshooting steps for environments with static proxy</span></span>

> [!WARNING]
> <span data-ttu-id="b46a4-121">PAC, WPAD 및 인증된 proxies는 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-121">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="b46a4-122">정적 프록시 또는 투명 프록시만 사용 중이지 않도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-122">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="b46a4-123">보안상의 이유로 SSL 검사 및 가로채기 Proxies도 지원되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-123">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="b46a4-124">SSL 검사 및 프록시 서버에 대한 예외를 구성하여 Linux 끝점용 Defender의 데이터를 가로채지 않고 관련 URL로 직접 전달합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-124">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="b46a4-125">전역 저장소에 가로채기 인증서를 추가하면 가로채는 것을 허용하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-125">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="b46a4-126">정적 프록시가 필요한 경우 프록시 주소 및 포트에 해당하는 위의 명령에 proxy 매개 `proxy_address:port` 변수를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-126">If a static proxy is required, add a proxy parameter to the above command, where `proxy_address:port` correspond to the proxy address and port:</span></span>

```bash
curl -x http://proxy_address:port -w ' %{url_effective}\n' 'https://x.cp.wd.microsoft.com/api/report' 'https://cdn.x.cp.wd.microsoft.com/ping'
```

<span data-ttu-id="b46a4-127">파일에 구성된 동일한 프록시 주소와 포트를 사용하는지 `/lib/system/system/mdatp.service` 확인</span><span class="sxs-lookup"><span data-stu-id="b46a4-127">Ensure that you use the same proxy address and port as configured in the `/lib/system/system/mdatp.service` file.</span></span> <span data-ttu-id="b46a4-128">위의 명령에서 오류가 있는 경우 프록시 구성을 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-128">Check your proxy configuration if there are errors from the above commands.</span></span>

> [!WARNING]
> <span data-ttu-id="b46a4-129">정적 프록시는 시스템 전체 환경 변수를 통해 `HTTPS_PROXY` 구성할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-129">The static proxy cannot be configured through a system-wide `HTTPS_PROXY` environment variable.</span></span> <span data-ttu-id="b46a4-130">대신 파일에 올바르게 `HTTPS_PROXY` 설정되어 있는지 `/lib/system/system/mdatp.service` 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-130">Instead, ensure that `HTTPS_PROXY` is properly set in the `/lib/system/system/mdatp.service` file.</span></span>

<span data-ttu-id="b46a4-131">정적 프록시를 사용하려면 `mdatp.service` 파일을 수정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-131">To use a static proxy, the `mdatp.service` file must be modified.</span></span> <span data-ttu-id="b46a4-132">다음 줄의 줄을 제거하기 위해 선행이 `#` 제거되도록 `/lib/systemd/system/mdatp.service` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-132">Ensure the leading `#` is removed to uncomment the following line from `/lib/systemd/system/mdatp.service`:</span></span>

```bash
#Environment="HTTPS_PROXY=http://address:port"
```

<span data-ttu-id="b46a4-133">또한 을 바꾸기 위해 올바른 정적 프록시 주소를 채워야 `address:port` 합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-133">Also ensure that the correct static proxy address is filled in to replace `address:port`.</span></span>

<span data-ttu-id="b46a4-134">이 파일이 올바른 경우 터미널에서 다음 명령을 실행하여 Linux의 끝점용 Defender를 다시 로드하고 설정을 전파합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-134">If this file is correct, try running the following command in the terminal to reload Defender for Endpoint on Linux and propagate the setting:</span></span>

```bash
sudo systemctl daemon-reload; sudo systemctl restart mdatp
```

<span data-ttu-id="b46a4-135">성공하면 명령줄에서 다른 연결 테스트를 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-135">Upon success, attempt another connectivity test from the command line:</span></span>

```bash
mdatp connectivity test
```

<span data-ttu-id="b46a4-136">문제가 계속되면 고객 지원에 문의합니다.</span><span class="sxs-lookup"><span data-stu-id="b46a4-136">If the problem persists, contact customer support.</span></span>

## <a name="resources"></a><span data-ttu-id="b46a4-137">리소스</span><span class="sxs-lookup"><span data-stu-id="b46a4-137">Resources</span></span>

- <span data-ttu-id="b46a4-138">정적 프록시를 사용하도록 제품을 구성하는 방법에 대한 자세한 내용은 정적 프록시 검색을 위해 [끝점용 Microsoft Defender 구성을 참조하세요.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b46a4-138">For more information about how to configure the product to use a static proxy, see [Configure Microsoft Defender for Endpoint for static proxy discovery](linux-static-proxy-configuration.md).</span></span>
