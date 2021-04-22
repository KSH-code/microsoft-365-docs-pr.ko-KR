---
title: MacOS의 끝점용 Microsoft Defender에서 커널 확장 문제 해결
description: MacOS의 끝점용 Microsoft Defender에서 커널 확장 관련 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 커널, 확장
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
ms.openlocfilehash: 9dc3ee17d79972b5d36c5fff58fbe4cc486027bd
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934276"
---
# <a name="troubleshoot-kernel-extension-issues-in-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="102ae-104">MacOS의 끝점용 Microsoft Defender에서 커널 확장 문제 해결</span><span class="sxs-lookup"><span data-stu-id="102ae-104">Troubleshoot kernel extension issues in Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="102ae-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="102ae-105">**Applies to:**</span></span>

- [<span data-ttu-id="102ae-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="102ae-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- <span data-ttu-id="102ae-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="102ae-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="102ae-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="102ae-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="102ae-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="102ae-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="102ae-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="102ae-111">이 문서에서는 macOS에서 끝점용 Microsoft Defender의 일부로 설치된 커널 확장 문제를 해결하는 방법에 대한 정보를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-111">This article provides information on how to troubleshoot issues with the kernel extension that is installed as part of Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="102ae-112">macOS High Sierra(10.13)부터 macOS는 장치에서 실행이 허용되기 전에 모든 커널 확장을 명시적으로 승인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-112">Starting with macOS High Sierra (10.13), macOS requires all kernel extensions to be explicitly approved before they're allowed to run on the device.</span></span>

<span data-ttu-id="102ae-113">macOS에서 끝점용 Microsoft Defender를 배포/설치하는 동안 커널 확장을 승인하지 않은 경우 응용 프로그램에 사용하도록 설정할지 묻는 배너가 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-113">If you didn't approve the kernel extension during the deployment/installation of Microsoft Defender for Endpoint on macOS, the application displays a banner prompting you to enable it:</span></span>

   ![RTP를 사용하지 않도록 설정한 스크린샷](images/mdatp-32-main-app-fix.png)

<span data-ttu-id="102ae-115">를 실행할 수 ```mdatp health``` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-115">You can also run ```mdatp health```.</span></span> <span data-ttu-id="102ae-116">실시간 보호를 사용할 수 있지만 사용할 수 없는 경우 보고합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-116">It reports if real-time protection is enabled but not available.</span></span> <span data-ttu-id="102ae-117">이는 커널 확장이 장치에서 실행이 승인되지 않았다는 것을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-117">This indicates that the kernel extension isn't approved to run on your device.</span></span>

```bash
mdatp health
```
```Output
...
real_time_protection_enabled                : false
real_time_protection_available              : true
...
```

<span data-ttu-id="102ae-118">다음 섹션에서는 macOS에서 끝점용 Microsoft Defender를 배포하는 데 사용한 방법에 따라 이 문제를 해결 하는 방법에 대한 지침을 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-118">The following sections provide guidance on how to address this issue, depending on the method that you used to deploy Microsoft Defender for Endpoint on macOS.</span></span>

## <a name="managed-deployment"></a><span data-ttu-id="102ae-119">관리되는 배포</span><span class="sxs-lookup"><span data-stu-id="102ae-119">Managed deployment</span></span>

<span data-ttu-id="102ae-120">제품을 배포하는 데 사용한 관리 도구에 해당하는 지침을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="102ae-120">See the instructions corresponding to the management tool that you used to deploy the product:</span></span>

- [<span data-ttu-id="102ae-121">JAMF 기반 배포</span><span class="sxs-lookup"><span data-stu-id="102ae-121">JAMF-based deployment</span></span>](mac-install-with-jamf.md)
- [<span data-ttu-id="102ae-122">Microsoft Intune 기반 배포</span><span class="sxs-lookup"><span data-stu-id="102ae-122">Microsoft Intune-based deployment</span></span>](mac-install-with-intune.md#create-system-configuration-profiles)

## <a name="manual-deployment"></a><span data-ttu-id="102ae-123">수동 배포</span><span class="sxs-lookup"><span data-stu-id="102ae-123">Manual deployment</span></span>

<span data-ttu-id="102ae-124">제품이 설치된 후 30분 미만이 경과한 경우 시스템 기본 설정 보안 & 개인 정보로 이동합니다. 여기서  >  개발자 "Microsoft Corporation"의 시스템 소프트웨어를 허용해야 합니다. </span><span class="sxs-lookup"><span data-stu-id="102ae-124">If less than 30 minutes have passed since the product was installed, navigate to **System Preferences** > **Security & Privacy**, where you have to **Allow** system software from developers "Microsoft Corporation".</span></span>

<span data-ttu-id="102ae-125">이 프롬프트가 표시되지 않는 경우 30분 이상이 지났지만 커널 확장이 장치에서 실행이 승인되지 않은 것입니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-125">If you don't see this prompt, it means that 30 or more minutes have passed, and the kernel extension still not been approved to run on your device:</span></span>

![메시지가 만료된 후 보안 및 개인 정보 보호 창 스크린샷](images/mdatp-33-securityprivacysettings-noprompt.png)

<span data-ttu-id="102ae-127">이 경우 다음 단계를 수행하여 승인 흐름을 다시 트리거해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-127">In this case, you need to perform the following steps to trigger the approval flow again.</span></span>

1. <span data-ttu-id="102ae-128">터미널에서 드라이버를 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-128">In Terminal, attempt to install the driver.</span></span> <span data-ttu-id="102ae-129">커널 확장이 디바이스에서 실행이 승인되지 않은 경우 다음 작업이 실패합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-129">The following operation will fail, because the kernel extension wasn't approved to run on the device.</span></span> <span data-ttu-id="102ae-130">그러나 승인 흐름이 다시 트리거됩니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-130">However, it will trigger the approval flow again.</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```
    
    ```Output
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Kext rejected due to system policy: <OSKext 0x7fc34d528390 [0x7fffa74aa8e0]> { URL = "file:///Library/StagedExtensions/Library/Extensions/wdavkext.kext/", ID = "com.microsoft.wdavkext" }
    Diagnostics for /Library/Extensions/wdavkext.kext:
    ```

2. <span data-ttu-id="102ae-131">메뉴에서 **시스템** 기본 설정  >  **& 개인 정보** 보호를 여세요.</span><span class="sxs-lookup"><span data-stu-id="102ae-131">Open **System Preferences** > **Security & Privacy** from the menu.</span></span> <span data-ttu-id="102ae-132">(열면 먼저 닫습니다.)</span><span class="sxs-lookup"><span data-stu-id="102ae-132">(Close it first, if it's opened.)</span></span>

3. <span data-ttu-id="102ae-133">**개발자** "Microsoft Corporation"의 시스템 소프트웨어 허용</span><span class="sxs-lookup"><span data-stu-id="102ae-133">**Allow** system software from developers "Microsoft Corporation"</span></span>

4. <span data-ttu-id="102ae-134">터미널에서 드라이버를 다시 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-134">In Terminal, install the driver again.</span></span> <span data-ttu-id="102ae-135">이번에는 작업이 성공합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-135">This time the operation will succeed:</span></span>

    ```bash
    sudo kextutil /Library/Extensions/wdavkext.kext
    ```

    <span data-ttu-id="102ae-136">배너는 Defender 응용 프로그램에서 사라져야 하며, 이제 실시간 보호가 사용 가능하고 사용하도록 설정되어 있는 ```mdatp health``` 것으로 보고해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="102ae-136">The banner should disappear from the Defender application, and ```mdatp health``` should now report that real-time protection is both enabled and available:</span></span>

    ```bash
    mdatp health
    ```

    ```Output
    ...
    real_time_protection_enabled                : true
    real_time_protection_available              : true
    ...
    ```
