---
title: macOS에서 끝점용 Microsoft Defender의 성능 문제 해결
description: MacOS의 끝점용 Microsoft Defender에서 성능 문제를 해결합니다.
keywords: Microsoft, defender, Endpoint용 Microsoft Defender, mac, 성능
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
ms.openlocfilehash: a4ebb360bc606845bfd3f80f31082c836b896477
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694260"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="60801-104">macOS에서 끝점용 Microsoft Defender의 성능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="60801-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="60801-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="60801-105">**Applies to:**</span></span>

- [<span data-ttu-id="60801-106">Microsoft Defender for Endpoint(macOS용)</span><span class="sxs-lookup"><span data-stu-id="60801-106">Microsoft Defender for Endpoint on macOS</span></span>](microsoft-defender-endpoint-mac.md)
- <span data-ttu-id="60801-107">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="60801-107">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="60801-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="60801-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="60801-109">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="60801-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="60801-110">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="60801-111">이 항목에서는 macOS의 끝점용 Microsoft Defender와 관련된 성능 문제를 좁히는 데 사용할 수 있는 몇 가지 일반적인 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-111">This topic provides some general steps that can be used to narrow down performance issues related to Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="60801-112">RTP(실시간 보호)는 지속적으로 위협으로부터 장치를 모니터링하고 보호하는 MacOS용 끝점용 Microsoft Defender의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="60801-112">Real-time protection (RTP) is a feature of Microsoft Defender for Endpoint on macOS that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="60801-113">이 구성은 파일 및 프로세스 모니터링 및 기타추론으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-113">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="60801-114">실행 중인 응용 프로그램 및 장치 특성에 따라 macOS에서 끝점용 Microsoft Defender를 실행하면 성능이 하될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-114">Depending on the applications that you're running and your device characteristics, you may experience suboptimal performance when running Microsoft Defender for Endpoint on macOS.</span></span> <span data-ttu-id="60801-115">특히 짧은 시간 동안 많은 리소스에 액세스하는 응용 프로그램 또는 시스템 프로세스는 macOS의 끝점용 Microsoft Defender에서 성능 문제가 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-115">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Microsoft Defender for Endpoint on macOS.</span></span>

<span data-ttu-id="60801-116">다음 단계를 사용하여 이러한 문제를 해결하고 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-116">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="60801-117">다음 방법 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정하고 성능이 향상될지 여부를 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-117">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="60801-118">이 방법은 macOS의 끝점용 Microsoft Defender가 성능 문제에 기여하는지 여부를 좁히는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-118">This approach helps narrow down whether Microsoft Defender for Endpoint on macOS is contributing to the performance issues.</span></span>

      <span data-ttu-id="60801-119">조직에서 장치를 관리하지 않는 경우 다음 옵션 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-119">If your device is not managed by your organization, real-time protection can be disabled using one of the following options:</span></span>

    - <span data-ttu-id="60801-120">사용자 인터페이스에서</span><span class="sxs-lookup"><span data-stu-id="60801-120">From the user interface.</span></span> <span data-ttu-id="60801-121">macOS에서 끝점용 Microsoft Defender를 열고 설정 **관리로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="60801-121">Open Microsoft Defender for Endpoint on macOS and navigate to **Manage settings**.</span></span>

      ![실시간 보호 스크린샷 관리](images/mdatp-36-rtp.png)

    - <span data-ttu-id="60801-123">터미널에서</span><span class="sxs-lookup"><span data-stu-id="60801-123">From the Terminal.</span></span> <span data-ttu-id="60801-124">보안을 위해 이 작업을 수행하려면 권한 상승이 필요합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-124">For security purposes, this operation requires elevation.</span></span>

      ```bash
      mdatp config real-time-protection --value disabled
      ```

      <span data-ttu-id="60801-125">조직에서 장치를 관리하는 경우 관리자가 [macOS의 끝점에 대한 Microsoft Defender](mac-preferences.md)기본 설정의 지침을 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-125">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Microsoft Defender for Endpoint on macOS](mac-preferences.md).</span></span>
      
      <span data-ttu-id="60801-126">실시간 보호가 해제된 동안 성능 문제가 지속되면 문제의 원점은 끝점 검색 및 응답 구성 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-126">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="60801-127">이 경우 고객 지원에 문의하여 추가 지침 및 완화를 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="60801-127">In this case, please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="60801-128">찾기를 열고 응용 **프로그램**  >  **유틸리티로 이동합니다.**</span><span class="sxs-lookup"><span data-stu-id="60801-128">Open Finder and navigate to **Applications** > **Utilities**.</span></span> <span data-ttu-id="60801-129">작업 **모니터를** 열고 시스템에서 리소스를 사용하는 응용 프로그램을 분석합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-129">Open **Activity Monitor** and analyze which applications are using the resources on your system.</span></span> <span data-ttu-id="60801-130">일반적인 예로는 소프트웨어 업데이트 프로그램 및 컴파일러가 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-130">Typical examples include software updaters and compilers.</span></span>

1. <span data-ttu-id="60801-131">가장 많은 검색을 트리거하는 응용 프로그램을 찾으기 위해 Mac의 Endpoint용 Defender에서 수집한 실시간 통계를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-131">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint on Mac.</span></span>

      > [!NOTE]
      > <span data-ttu-id="60801-132">이 기능은 버전 100.90.70 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-132">This feature is available in version 100.90.70 or newer.</span></span>
      <span data-ttu-id="60801-133">이 기능은 **Dogfood** 및 **InsiderFast** 채널에서 기본적으로 사용됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-133">This feature is enabled by default on the **Dogfood** and **InsiderFast** channels.</span></span> <span data-ttu-id="60801-134">다른 업데이트 채널을 사용하는 경우 명령줄에서 이 기능을 사용하도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-134">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
      ```bash
      mdatp config real-time-protection-statistics  --value enabled
      ```

      <span data-ttu-id="60801-135">이 기능을 사용하려면 실시간 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-135">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="60801-136">실시간 보호 상태를 확인하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-136">To check the status of real-time protection, run the following command:</span></span>

      ```bash
      mdatp health --field real_time_protection_enabled
      ```

    <span data-ttu-id="60801-137">real_time_protection_enabled **항목이** true인지 확인해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-137">Verify that the **real_time_protection_enabled** entry is true.</span></span> <span data-ttu-id="60801-138">그렇지 않으면 다음 명령을 실행하여 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="60801-138">Otherwise, run the following command to enable it:</span></span>

      ```bash
      mdatp config real-time-protection --value enabled
      ```

      ```output
      Configuration property updated
      ```

      <span data-ttu-id="60801-139">현재 통계를 수집하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-139">To collect current statistics, run:</span></span>

      ```bash
      mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
      ```

      > [!NOTE]
      > <span data-ttu-id="60801-140">**--output json(이중** 파선 참고)을 사용하면 출력 형식을 구문 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-140">Using **--output json** (note the double dash) ensures that the output format is ready for parsing.</span></span>
      <span data-ttu-id="60801-141">이 명령의 출력에는 모든 프로세스 및 관련 검사 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-141">The output of this command will show all processes and their associated scan activity.</span></span>

1. <span data-ttu-id="60801-142">Mac 시스템에서 다음 명령을 사용하여 샘플 Python 파서 high_cpu_parser.py를 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-142">On your Mac system, download the sample Python parser high_cpu_parser.py using the command:</span></span>

    ```bash
    curl -O https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```

    <span data-ttu-id="60801-143">이 명령의 출력은 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-143">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.
    mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'
    100%[===========================================>] 1,020    --.-K/s   in 
    0s
    ```

1. <span data-ttu-id="60801-144">다음으로 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-144">Next, type the following commands:</span></span>

      ```bash
        chmod +x high_cpu_parser.py
      ```

      ```bash
        cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
      ```

      <span data-ttu-id="60801-145">위의 출력은 성능 문제에 대한 가장 많은 기여자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="60801-145">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="60801-146">첫 번째 열은 PID(프로세스 식별자)이고, 두 번째 열은 te 프로세스 이름이고, 마지막 열은 검사된 파일 수로, 영향별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-146">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>

      <span data-ttu-id="60801-147">예를 들어 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-147">For example, the output of the command will be something like the below:</span></span>

      ```output
        ... > python ~/repo/mdatp-xplat/linux/diagnostic/high_cpu_parser.py <~Downloads/output.json | head -n 10
        27432 None 76703
        73467 actool     1249
        73914 xcodebuild 1081
        73873 bash 1050
        27475 None 836
        1    launchd    407
        73468 ibtool     344
        549  telemetryd_v1   325
        4764 None 228
        125  CrashPlanService 164
      ```

      <span data-ttu-id="60801-148">Mac에서 끝점용 Defender의 성능을 향상하려면 검색된 총 파일 행에서 가장 높은 수의 끝점을 찾고 제외를 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-148">To improve the performance of Defender for Endpoint on Mac, locate the one with the highest number under the Total files scanned row and add an exclusion for it.</span></span> <span data-ttu-id="60801-149">자세한 내용은 [Linux에서 끝점용 Defender에](linux-exclusions.md)대한 제외 구성 및 유효성 검사를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="60801-149">For more information, see [Configure and validate exclusions for Defender for Endpoint on Linux](linux-exclusions.md).</span></span>

      > [!NOTE]
      > <span data-ttu-id="60801-150">응용 프로그램은 통계를 메모리에 저장하고 시작된 후 실시간 보호를 사용하도록 설정한 이후에만 파일 활동을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-150">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="60801-151">실시간 보호가 해제된 이전 또는 기간 동안 시작된 프로세스는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="60801-151">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="60801-152">또한 검사가 트리거된 이벤트만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="60801-152">Additionally, only events which triggered scans are counted.</span></span>
      > 
1. <span data-ttu-id="60801-153">성능 문제에 기여하는 프로세스 또는 디스크 위치에 대한 제외를 사용하여 macOS의 끝점에 대한 Microsoft Defender를 구성하고 실시간 보호를 다시 사용하도록 설정하세요.</span><span class="sxs-lookup"><span data-stu-id="60801-153">Configure Microsoft Defender for Endpoint on macOS with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

     <span data-ttu-id="60801-154">자세한 [내용은 MacOS의 끝점에 대한 Microsoft Defender 제외](mac-exclusions.md) 구성 및 유효성 검사를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="60801-154">See [Configure and validate exclusions for Microsoft Defender for Endpoint on macOS](mac-exclusions.md) for details.</span></span>
