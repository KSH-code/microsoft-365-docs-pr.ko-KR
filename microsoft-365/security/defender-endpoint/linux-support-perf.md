---
title: Linux에서 끝점용 Microsoft Defender의 성능 문제 해결
description: Linux의 Microsoft Defender 끝점에서 성능 문제를 해결합니다.
keywords: microsoft, defender, atp, linux, 성능
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
mms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 5aaa95ef8202f3d0957113d8f20a39e4d3840227
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903989"
---
# <a name="troubleshoot-performance-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="59d1d-104">Linux에서 끝점용 Microsoft Defender의 성능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="59d1d-104">Troubleshoot performance issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="59d1d-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="59d1d-105">**Applies to:**</span></span>
- [<span data-ttu-id="59d1d-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="59d1d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="59d1d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="59d1d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)
> <span data-ttu-id="59d1d-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="59d1d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="59d1d-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="59d1d-110">이 문서에서는 Linux용 끝점용 Defender와 관련된 성능 문제를 좁히는 데 사용할 수 있는 몇 가지 일반적인 단계를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-110">This article provides some general steps that can be used to narrow down performance issues related to Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="59d1d-111">RTP(실시간 보호)는 지속적으로 위협으로부터 장치를 모니터링하고 보호하는 Linux용 Endpoint용 Defender의 기능입니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-111">Real-time protection (RTP) is a feature of Defender for Endpoint for Linux that continuously monitors and protects your device against threats.</span></span> <span data-ttu-id="59d1d-112">이 구성은 파일 및 프로세스 모니터링 및 기타추론으로 구성됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-112">It consists of file and process monitoring and other heuristics.</span></span>

<span data-ttu-id="59d1d-113">실행 중인 응용 프로그램 및 장치 특성에 따라 Linux용 끝점용 Defender를 실행하면 성능이 멀어질 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-113">Depending on the applications that you are running and your device characteristics, you may experience suboptimal performance when running Defender for Endpoint for Linux.</span></span> <span data-ttu-id="59d1d-114">특히 짧은 시간 동안 많은 리소스에 액세스하는 응용 프로그램 또는 시스템 프로세스는 Linux용 끝점용 Defender의 성능 문제를 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-114">In particular, applications or system processes that access many resources over a short timespan can lead to performance issues in Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="59d1d-115">시작하기 전에 다른 보안 제품이 장치에서 현재 실행되고 **있지 않은지 확인합니다.**</span><span class="sxs-lookup"><span data-stu-id="59d1d-115">Before starting, **please make sure that other security products are not currently running on the device**.</span></span> <span data-ttu-id="59d1d-116">여러 보안 제품이 충돌하여 호스트 성능에 영향을 줄 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-116">Multiple security products may conflict and impact the host performance.</span></span>

<span data-ttu-id="59d1d-117">다음 단계를 사용하여 이러한 문제를 해결하고 완화할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-117">The following steps can be used to troubleshoot and mitigate these issues:</span></span>

1. <span data-ttu-id="59d1d-118">다음 방법 중 하나를 사용하여 실시간 보호를 사용하지 않도록 설정하고 성능이 향상될지 여부를 관찰합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-118">Disable real-time protection using one of the following methods and observe whether the performance improves.</span></span> <span data-ttu-id="59d1d-119">이 방법은 Linux용 Endpoint용 Defender가 성능 문제에 기여하는지 여부를 좁히는 데 도움이 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-119">This approach helps narrow down whether Defender for Endpoint for Linux is contributing to the performance issues.</span></span>

    <span data-ttu-id="59d1d-120">조직에서 디바이스를 관리하지 않는 경우 명령줄에서 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-120">If your device is not managed by your organization, real-time protection can be disabled from the command line:</span></span>

    ```bash
    mdatp config real-time-protection --value disabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="59d1d-121">조직에서 디바이스를 관리하는 경우 관리자가 [Linux용 끝점에](linux-preferences.md)대한 Defender 기본 설정의 지침을 사용하여 실시간 보호를 사용하지 않도록 설정할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-121">If your device is managed by your organization, real-time protection can be disabled by your administrator using the instructions in [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

    <span data-ttu-id="59d1d-122">실시간 보호가 해제된 동안 성능 문제가 지속되면 문제의 원점은 끝점 검색 및 응답 구성 요소일 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-122">If the performance problem persists while real-time protection is off, the origin of the problem could be the endpoint detection and response component.</span></span> <span data-ttu-id="59d1d-123">이 경우 고객 지원에 문의하여 추가 지침 및 완화를 요청하세요.</span><span class="sxs-lookup"><span data-stu-id="59d1d-123">In this case please contact customer support for further instructions and mitigation.</span></span>

2. <span data-ttu-id="59d1d-124">가장 많은 검색을 트리거하는 응용 프로그램을 찾기 위해 Linux용 Endpoint용 Defender에서 수집한 실시간 통계를 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-124">To find the applications that are triggering the most scans, you can use real-time statistics gathered by Defender for Endpoint for Linux.</span></span>

    > [!NOTE]
    > <span data-ttu-id="59d1d-125">이 기능은 버전 100.90.70 이상에서 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-125">This feature is available in version 100.90.70 or newer.</span></span>

    <span data-ttu-id="59d1d-126">이 기능은 및 채널에서 기본적으로 `Dogfood` `InsiderFast` 사용하도록 설정됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-126">This feature is enabled by default on the `Dogfood` and `InsiderFast` channels.</span></span> <span data-ttu-id="59d1d-127">다른 업데이트 채널을 사용하는 경우 명령줄에서 이 기능을 사용하도록 설정하면 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-127">If you're using a different update channel, this feature can be enabled from the command line:</span></span>
    ```bash
    mdatp config real-time-protection-statistics --value enabled
    ```

    <span data-ttu-id="59d1d-128">이 기능을 사용하려면 실시간 보호를 사용하도록 설정해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-128">This feature requires real-time protection to be enabled.</span></span> <span data-ttu-id="59d1d-129">실시간 보호 상태를 확인하기 위해 다음 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-129">To check the status of real-time protection, run the following command:</span></span>

    ```bash
    mdatp health --field real_time_protection_enabled
    ```

    <span data-ttu-id="59d1d-130">항목이 `real_time_protection_enabled` `true` 입니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-130">Verify that the `real_time_protection_enabled` entry is `true`.</span></span> <span data-ttu-id="59d1d-131">그렇지 않으면 다음 명령을 실행하여 사용하도록 설정하십시오.</span><span class="sxs-lookup"><span data-stu-id="59d1d-131">Otherwise, run the following command to enable it:</span></span>

    ```bash
    mdatp config real-time-protection --value enabled
    ```
    ```Output
    Configuration property updated
    ```

    <span data-ttu-id="59d1d-132">현재 통계를 수집하기 위해 다음을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-132">To collect current statistics, run:</span></span>

    ```bash
    mdatp diagnostic real-time-protection-statistics --output json > real_time_protection.json
    ```

    > [!NOTE]
    > <span data-ttu-id="59d1d-133">이중 대시를 사용하면 출력 형식을 구문 분석할 ```--output json``` 준비가 됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-133">Using ```--output json``` (note the double dash) ensures that the output format is ready for parsing.</span></span>

    <span data-ttu-id="59d1d-134">이 명령의 출력에는 모든 프로세스 및 관련 검사 활동이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-134">The output of this command will show all processes and their associated scan activity.</span></span>

3. <span data-ttu-id="59d1d-135">Linux 시스템에서 다음 명령을 사용하여 샘플 Python **high_cpu_parser.py를** 다운로드합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-135">On your Linux system, download the sample Python parser **high_cpu_parser.py** using the command:</span></span>

    ```bash
    wget -c https://raw.githubusercontent.com/microsoft/mdatp-xplat/master/linux/diagnostic/high_cpu_parser.py
    ```
    <span data-ttu-id="59d1d-136">이 명령의 출력은 다음과 유사해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-136">The output of this command should be similar to the following:</span></span>

    ```Output
    --2020-11-14 11:27:27-- https://raw.githubusercontent.com/microsoft.mdatp-xplat/master/linus/diagnostic/high_cpu_parser.py
    Resolving raw.githubusercontent.com (raw.githubusercontent.com)... 151.101.xxx.xxx
    Connecting to raw.githubusercontent.com (raw.githubusercontent.com)| 151.101.xxx.xxx| :443... connected.
    HTTP request sent, awaiting response... 200 OK
    Length: 1020 [text/plain]
    Saving to: 'high_cpu_parser.py'

    100%[===========================================>] 1,020    --.-K/s   in 0s
    ```

4. <span data-ttu-id="59d1d-137">다음으로 다음 명령을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-137">Next, type the following commands:</span></span>

    ```bash
    chmod +x high_cpu_parser.py
    ```

    ```bash
    cat real_time_protection.json | python high_cpu_parser.py  > real_time_protection.log
    ```

      <span data-ttu-id="59d1d-138">위의 출력은 성능 문제에 대한 가장 많은 기여자 목록입니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-138">The output of the above is a list of the top contributors to performance issues.</span></span> <span data-ttu-id="59d1d-139">첫 번째 열은 PID(프로세스 식별자)이고, 두 번째 열은 te 프로세스 이름이고, 마지막 열은 검사된 파일 수로, 영향별로 정렬됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-139">The first column is the process identifier (PID), the second column is te process name, and the last column is the number of scanned files, sorted by impact.</span></span>
    <span data-ttu-id="59d1d-140">예를 들어 명령의 출력은 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-140">For example, the output of the command will be something like the below:</span></span> 

    ```Output
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

    <span data-ttu-id="59d1d-141">Linux용 Endpoint용 Defender의 성능을 개선하기 위해 행 아래에 있는 가장 높은 숫자를 찾아 제외를 `Total files scanned` 추가합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-141">To improve the performance of Defender for Endpoint for Linux, locate the one with the highest number under the `Total files scanned` row and add an exclusion for it.</span></span> <span data-ttu-id="59d1d-142">자세한 내용은 [Linux용 끝점용 Defender에](linux-exclusions.md)대한 제외 구성 및 유효성 검사를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d1d-142">For more information, see [Configure and validate exclusions for Defender for Endpoint for Linux](linux-exclusions.md).</span></span>

    >[!NOTE]
    > <span data-ttu-id="59d1d-143">응용 프로그램은 통계를 메모리에 저장하고 시작된 후 실시간 보호를 사용하도록 설정한 이후에만 파일 활동을 추적합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-143">The application stores statistics in memory and only keeps track of file activity since it was started and real-time protection was enabled.</span></span> <span data-ttu-id="59d1d-144">실시간 보호가 해제된 이전 또는 기간 동안 시작된 프로세스는 계산되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-144">Processes that were launched before or during periods when real time protection was off are not counted.</span></span> <span data-ttu-id="59d1d-145">또한 검사가 트리거된 이벤트만 계산됩니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-145">Additionally, only events which triggered scans are counted.</span></span>

5. <span data-ttu-id="59d1d-146">성능 문제에 기여하는 프로세스 또는 디스크 위치에 대한 제외를 사용하여 Linux에서 Microsoft Defender 끝점을 구성하고 실시간 보호를 다시 활성화합니다.</span><span class="sxs-lookup"><span data-stu-id="59d1d-146">Configure Microsoft Defender Endpoint on Linux with exclusions for the processes or disk locations that contribute to the performance issues and re-enable real-time protection.</span></span>

    <span data-ttu-id="59d1d-147">자세한 내용은 [Linux용 끝점용 Microsoft Defender에](linux-exclusions.md)대한 제외 구성 및 유효성 검사를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="59d1d-147">For more information, see [Configure and validate exclusions for Microsoft Defender for Endpoint for Linux](linux-exclusions.md).</span></span>
