---
title: Mac용 끝점용 Microsoft Defender의 커널 확장 문제 해결
description: Mac용 끝점용 Microsoft Defender에서 커널 확장 관련 문제를 해결합니다.
keywords: microsoft, defender, atp, mac, 커널, 확장
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
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 877cc619d3ba048cdf6ecc8149f073461d9eac8e
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379519"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-for-mac"></a><span data-ttu-id="2631e-104">Mac용 끝점용 Microsoft Defender의 커널 확장 문제 해결</span><span class="sxs-lookup"><span data-stu-id="2631e-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint for Mac</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2631e-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="2631e-105">**Applies to:**</span></span>

- [<span data-ttu-id="2631e-106">엔드포인트용 Microsoft Defender(Mac용)</span><span class="sxs-lookup"><span data-stu-id="2631e-106">Microsoft Defender for Endpoint for Mac</span></span>](microsoft-defender-endpoint-mac.md)
- [<span data-ttu-id="2631e-107">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="2631e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2631e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2631e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="2631e-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="2631e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2631e-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="2631e-111">이 문서에서는 Mac용 끝점용 Microsoft Defender의 일부로 설치된 커널 확장 문제를 해결하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint for Mac.</span></span>

<span data-ttu-id="2631e-112">macOS High Sierra(10.13)부터 macOS는 장치에서 실행이 허용되기 전에 모든 커널 확장을 명시적으로 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they're allowed to run on the device.</span></span>

<span data-ttu-id="2631e-113">Mac용 끝점용 Microsoft Defender를 배포/설치하는 동안 커널 확장을 승인하지 않은 경우 응용 프로그램에 사용하도록 설정할지 묻는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-113">If you didn't approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint for Mac, the application displays a banner prompting you to enable it:</span></span>

   ![RTP를 사용하지 않도록 설정한 스크린샷](images/mdatp-32-main-app-fix.png)

<span data-ttu-id="2631e-115">를 실행할 수 ```mdatp health``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="2631e-116">실시간 보호를 사용할 수 있지만 사용할 수 없는 경우 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="2631e-117">이는 커널 확장이 장치에서 실행이 승인되지 않았다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-117">This indicates that the kernel extension isn't approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="2631e-118">다음 섹션에서는 Mac용 끝점용 Microsoft Defender를 배포하는 데 사용한 방법에 따라 이 문제를 해결 하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint for Mac.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="2631e-119">관리되는 배포</span><span class="sxs-lookup"><span data-stu-id="2631e-119">Managed deployment</span></span>

<span data-ttu-id="2631e-120">제품을 배포하는 데 사용한 관리 도구에 해당하는 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="2631e-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="2631e-121">JAMF 기반 배포</span><span class="sxs-lookup"><span data-stu-id="2631e-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="2631e-122">Microsoft Intune 기반 배포</span><span class="sxs-lookup"><span data-stu-id="2631e-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="2631e-123">수동 배포</span><span class="sxs-lookup"><span data-stu-id="2631e-123">Manual deployment</span></span>

<span data-ttu-id="2631e-124">제품이 설치된 후 30분 미만이 경과한 경우 시스템 기본 설정 보안 & 개인 정보로 이동합니다. 여기서  >  개발자 "Microsoft Corporation"의 시스템 소프트웨어를 허용해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="2631e-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="2631e-125">이 프롬프트가 표시되지 않는 경우 30분 이상이 지났지만 커널 확장이 장치에서 실행이 승인되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![메시지가 만료된 후 보안 및 개인 정보 보호 창 스크린샷](images/mdatp-33-securityprivacysettings-noprompt.png)

<span data-ttu-id="2631e-127">이 경우 다음 단계를 수행하여 승인 흐름을 다시 트리거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="2631e-128">터미널에서 드라이버를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="2631e-129">커널 확장이 디바이스에서 실행이 승인되지 않은 경우 다음 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-129">The following operation will fail, because the kernel extension wasn't approved to run on the device.</span></span> <span data-ttu-id="2631e-130">그러나 승인 흐름이 다시 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="2631e-131">메뉴에서 **시스템** 기본 설정  >  **& 개인 정보** 보호를 여세요.</span><span class="sxs-lookup"><span data-stu-id="2631e-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="2631e-132">(열면 먼저 닫습니다.)</span><span class="sxs-lookup"><span data-stu-id="2631e-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="2631e-133">**개발자** "Microsoft Corporation"의 시스템 소프트웨어 허용</span><span class="sxs-lookup"><span data-stu-id="2631e-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="2631e-134">터미널에서 드라이버를 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="2631e-135">이번에는 작업이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="2631e-136">배너는 Defender 응용 프로그램에서 사라져야 하며, 이제 실시간 보호가 사용 가능하고 사용하도록 설정되어 있는 ```mdatp health``` 것으로 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="2631e-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
