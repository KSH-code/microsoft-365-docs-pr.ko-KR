---
title: Linux 정적 프록시 검색용 Microsoft Defender ATP
ms.reviewer: ''
description: 정적 프록시 검색을 위해 Microsoft Defender ATP를 구성하는 방법을 설명 합니다.
keywords: microsoft, defender, atp, linux, 설치, 프록시
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
ms.openlocfilehash: b96f49d6c4744eae987393c17792c4f566d98997
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587074"
---
# <a name="configure-microsoft-defender-for-endpoint-for-linux-for-static-proxy-discovery"></a><span data-ttu-id="17229-104">정적 프록시 검색을 위해 Linux용 끝점에 대한 Microsoft Defender 구성</span><span class="sxs-lookup"><span data-stu-id="17229-104">Configure Microsoft Defender for Endpoint for Linux for static proxy discovery</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="17229-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="17229-105">**Applies to:**</span></span>
- <span data-ttu-id="17229-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="17229-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="17229-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17229-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="17229-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="17229-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17229-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="17229-110">Microsoft Defender ATP는 환경 변수를 사용하여 프록시 서버를 ```HTTPS_PROXY``` 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-110">Microsoft Defender ATP can discover a proxy server using the ```HTTPS_PROXY``` environment variable.</span></span> <span data-ttu-id="17229-111">이 설정은 설치  시와 제품이 설치된 후에 모두 구성해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-111">This setting must be configured **both** at installation time and after the product has been installed.</span></span>

## <a name="installation-time-configuration"></a><span data-ttu-id="17229-112">설치 시간 구성</span><span class="sxs-lookup"><span data-stu-id="17229-112">Installation time configuration</span></span>

<span data-ttu-id="17229-113">설치하는 동안 ```HTTPS_PROXY``` 환경 변수를 패키지 관리자에게 전달해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-113">During installation, the ```HTTPS_PROXY``` environment variable must be passed to the package manager.</span></span> <span data-ttu-id="17229-114">패키지 관리자는 다음 방법 중 한 가지 방법으로 이 변수를 읽을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-114">The package manager can read this variable in any of the following ways:</span></span>

- <span data-ttu-id="17229-115">변수는 ```HTTPS_PROXY``` 다음 ```/etc/environment``` 줄로 정의됩니다.</span><span class="sxs-lookup"><span data-stu-id="17229-115">The ```HTTPS_PROXY``` variable is defined in ```/etc/environment``` with the following line:</span></span>

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- <span data-ttu-id="17229-116">변수는 패키지 관리자 전역 `HTTPS_PROXY` 구성에 정의되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-116">The `HTTPS_PROXY` variable is defined in the package manager global configuration.</span></span> <span data-ttu-id="17229-117">예를 들어 Ubuntu 18.04에서 다음 줄을 추가할 수 `/etc/apt/apt.conf.d/proxy.conf` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-117">For example, in Ubuntu 18.04, you can add the following line to `/etc/apt/apt.conf.d/proxy.conf`:</span></span>
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > <span data-ttu-id="17229-118">위의 두 메서드는 시스템의 다른 응용 프로그램에 사용할 프록시를 정의할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-118">Note that above two methods could define the proxy to use for other applications on your system.</span></span> <span data-ttu-id="17229-119">이 방법은 일반적으로 전역 구성인 경우 또는 주의하여 사용하십시오.</span><span class="sxs-lookup"><span data-stu-id="17229-119">Use this method with caution, or only if this is meant to be a generally global configuration.</span></span>
  
- <span data-ttu-id="17229-120">변수가 설치 또는 제거 명령에 `HTTPS_PROXY` 추가됩니다.</span><span class="sxs-lookup"><span data-stu-id="17229-120">The `HTTPS_PROXY` variable is prepended to the installation or uninstallation commands.</span></span> <span data-ttu-id="17229-121">예를 들어 APT 패키지 관리자를 통해 끝점용 Microsoft Defender를 설치할 때 변수를 다음과 같이 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-121">For example, with the APT package manager, prepend the variable as follows when installing Microsoft Defender for Endpoint:</span></span> 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > <span data-ttu-id="17229-122">환경 변수 정의와 apt 사이에 sudo를 추가하지 말고, 그렇지 않으면 변수가 전파되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-122">Do not add sudo between the environment variable definition and apt, otherwise the variable will not be propagated.</span></span>

<span data-ttu-id="17229-123">제거 중에 환경 변수도 비슷하게 `HTTPS_PROXY` 정의될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-123">The `HTTPS_PROXY` environment variable may similarly be defined during uninstallation.</span></span>

<span data-ttu-id="17229-124">프록시가 필요하지만 구성되지 않은 경우 설치 및 제거가 반드시 실패할 필요는 없습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-124">Note that installation and uninstallation will not necessarily fail if a proxy is required but not configured.</span></span> <span data-ttu-id="17229-125">그러나 원격 분석은 제출되지 않습니다. 네트워크 시간 제한으로 인해 작업이 훨씬 오래 걸릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-125">However, telemetry will not be submitted, and the operation could take much longer due to network timeouts.</span></span>

## <a name="post-installation-configuration"></a><span data-ttu-id="17229-126">설치 후 구성</span><span class="sxs-lookup"><span data-stu-id="17229-126">Post installation configuration</span></span>
  
<span data-ttu-id="17229-127">설치 후 `HTTPS_PROXY` 환경 변수는 Endpoint 서비스용 Defender 파일에 정의되어야 합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-127">After installation, the `HTTPS_PROXY` environment variable must be defined in the Defender for Endpoint service file.</span></span> <span data-ttu-id="17229-128">이렇게 하도록 루트 사용자로 실행 하는 동안 텍스트 `/lib/systemd/system/mdatp.service` 편집기에서 를 여는 합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-128">To do this, open `/lib/systemd/system/mdatp.service` in a text editor while running as the root user.</span></span> <span data-ttu-id="17229-129">그런 다음 다음 두 가지 방법 중 하나를 사용하여 변수를 서비스에 전파할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-129">You can then propagate the variable to the service in one of two ways:</span></span>

- <span data-ttu-id="17229-130">줄의 줄의 줄을 `#Environment="HTTPS_PROXY=http://address:port"` 지우고 정적 프록시 주소를 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-130">Uncomment the line `#Environment="HTTPS_PROXY=http://address:port"` and specify your static proxy address.</span></span>

- <span data-ttu-id="17229-131">선을 `EnvironmentFile=/path/to/env/file` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-131">Add a line `EnvironmentFile=/path/to/env/file`.</span></span> <span data-ttu-id="17229-132">이 경로는 다음 줄을 추가해야 하는 사용자 지정 파일 또는 사용자 지정 파일을 `/etc/environment` 지정합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-132">This path can point to `/etc/environment` or a custom file, either of which needs to add the following line:</span></span>
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

<span data-ttu-id="17229-133">파일을 수정한 `mdatp.service` 후 저장한 후 닫습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-133">After modifying the `mdatp.service` file, save and close it.</span></span> <span data-ttu-id="17229-134">변경 내용을 적용할 수 있도록 서비스를 다시 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="17229-134">Restart the service so the changes can be applied.</span></span> <span data-ttu-id="17229-135">Ubuntu에서 이 명령에는 다음 두 가지 명령이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="17229-135">In Ubuntu, this involves two commands:</span></span>  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
