---
title: 성능 문제 해결
description: 끝점용 Microsoft Defender의 실시간 보호 서비스와 관련된 높은 CPU 사용량 문제를 해결합니다.
keywords: 문제 해결, 성능, 높은 CPU 사용률, 높은 CPU 사용, 오류, 수정, 업데이트 준수, oms, 모니터, 보고서, Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: normal
manager: dansimp
ms.date: 04/14/2021
audience: ITPro
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 71c2391361c645d26cdaddff0bff86796da50391
ms.sourcegitcommit: f000358c01a8006e5749a86b256300ee3a73174c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/24/2021
ms.locfileid: "51995084"
---
# <a name="troubleshoot-performance-issues-related-to-real-time-protection"></a><span data-ttu-id="7fd4a-104">실시간 보호와 관련된 성능 문제 해결</span><span class="sxs-lookup"><span data-stu-id="7fd4a-104">Troubleshoot performance issues related to real-time protection</span></span>


[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="7fd4a-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-105">**Applies to:**</span></span>

- [<span data-ttu-id="7fd4a-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="7fd4a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
 
<span data-ttu-id="7fd4a-107">시스템에 끝점용 Microsoft Defender의 실시간 보호 서비스와 관련된 높은 CPU 사용량 또는 성능 문제가 있는 경우 Microsoft 지원에 티켓을 제출할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-107">If your system is having high CPU usage or performance issues related to the real-time protection service in Microsoft Defender for Endpoint, you can submit a ticket to Microsoft support.</span></span> <span data-ttu-id="7fd4a-108">[Microsoft Defender 바이러스](collect-diagnostic-data.md)백신 진단 데이터 수집의 단계를 따릅니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-108">Follow the steps in [Collect Microsoft Defender Antivirus diagnostic data](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="7fd4a-109">관리자는 이러한 문제를 직접 해결할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-109">As an admin, you can also troubleshoot these issues on your own.</span></span> 

<span data-ttu-id="7fd4a-110">먼저 다른 소프트웨어로 인해 문제가 발생하고 있는지 확인할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-110">First, you might want to check if the issue is being caused by another software.</span></span> <span data-ttu-id="7fd4a-111">공급업체에 바이러스 백신 제외 [확인을 읽어야 합니다.](#check-with-vendor-for-antivirus-exclusions)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-111">Read [Check with vendor for antivirus exclusions](#check-with-vendor-for-antivirus-exclusions).</span></span>

<span data-ttu-id="7fd4a-112">그렇지 않으면 Microsoft 보호 로그 분석의 단계에 따라 식별된 성능 문제와 관련된 소프트웨어를 [식별할 수 있습니다.](#analyze-the-microsoft-protection-log)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-112">Otherwise, you can identify which software is related to the identified performance issue by following the steps in [Analyze the Microsoft Protection Log](#analyze-the-microsoft-protection-log).</span></span> 

<span data-ttu-id="7fd4a-113">다음 단계에 따라 Microsoft 지원에 제출에 추가 로그를 제공할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-113">You can also provide additional logs to your submission to Microsoft support by following the steps in:</span></span>
- [<span data-ttu-id="7fd4a-114">프로세스 모니터를 사용하여 프로세스 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-114">Capture process logs using Process Monitor</span></span>](#capture-process-logs-using-process-monitor)
- [<span data-ttu-id="7fd4a-115">Windows Performance Recorder를 사용하여 성능 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-115">Capture performance logs using Windows Performance Recorder</span></span>](#capture-performance-logs-using-windows-performance-recorder) 

## <a name="check-with-vendor-for-antivirus-exclusions"></a><span data-ttu-id="7fd4a-116">공급업체에 바이러스 백신 제외 확인</span><span class="sxs-lookup"><span data-stu-id="7fd4a-116">Check with vendor for antivirus exclusions</span></span>

<span data-ttu-id="7fd4a-117">시스템 성능에 영향을 주는 소프트웨어를 쉽게 식별할 수 있는 경우 소프트웨어 공급업체의 기술 자료 또는 지원 센터로 이동하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-117">If you can readily identify the software affecting system performance, go to the software vendor's knowledge base or support center.</span></span> <span data-ttu-id="7fd4a-118">바이러스 백신 제외에 대한 권장 사항이 있는 경우 검색합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-118">Search if they have recommendations about antivirus exclusions.</span></span> <span data-ttu-id="7fd4a-119">공급업체의 웹 사이트에 해당 웹 사이트가 없는 경우 지원 티켓을 열어서 게시할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-119">If the vendor's website does not have them, you can open a support ticket with them and ask them to publish one.</span></span> 

<span data-ttu-id="7fd4a-120">소프트웨어 공급업체는 업계와 파트너 관계의 다양한 지침을 따라 가극적 긍정을 [최소화하는 것이 좋습니다.](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-120">We recommend that software vendors follow the various guidelines in [Partnering with the industry to minimize false positives](https://www.microsoft.com/security/blog/2018/08/16/partnering-with-the-industry-to-minimize-false-positives/).</span></span> <span data-ttu-id="7fd4a-121">공급업체는 Microsoft Defender 보안 인텔리전스 포털(MDSI)을 통해 소프트웨어를 [제출할 수 있습니다.](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-121">The vendor can submit their software through the [Microsoft Defender Security Intelligence portal (MDSI)](https://www.microsoft.com/wdsi/filesubmission?persona=SoftwareDeveloper).</span></span>


## <a name="analyze-the-microsoft-protection-log"></a><span data-ttu-id="7fd4a-122">Microsoft 보호 로그 분석</span><span class="sxs-lookup"><span data-stu-id="7fd4a-122">Analyze the Microsoft Protection Log</span></span>

<span data-ttu-id="7fd4a-123">**MPLog-xxxxxx-xxxxxx.log에서** 실행 중인 소프트웨어의 예상 성능 영향 정보를 *EstimatedImpact*:</span><span class="sxs-lookup"><span data-stu-id="7fd4a-123">In **MPLog-xxxxxxxx-xxxxxx.log**, you can find the estimated performance impact information of running software as *EstimatedImpact*:</span></span>
    
`Per-process counts:ProcessImageName: smsswd.exe, TotalTime: 6597, Count: 1406, MaxTime: 609, MaxTimeFile: \Device\HarddiskVolume3\_SMSTaskSequence\Packages\WQ1008E9\Files\FramePkg.exe, EstimatedImpact: 65%`

| <span data-ttu-id="7fd4a-124">필드 이름</span><span class="sxs-lookup"><span data-stu-id="7fd4a-124">Field name</span></span> | <span data-ttu-id="7fd4a-125">설명</span><span class="sxs-lookup"><span data-stu-id="7fd4a-125">Description</span></span> |
|---|---|
|<span data-ttu-id="7fd4a-126">ProcessImageName</span><span class="sxs-lookup"><span data-stu-id="7fd4a-126">ProcessImageName</span></span> | <span data-ttu-id="7fd4a-127">프로세스 이미지 이름</span><span class="sxs-lookup"><span data-stu-id="7fd4a-127">Process image name</span></span> |
| <span data-ttu-id="7fd4a-128">TotalTime</span><span class="sxs-lookup"><span data-stu-id="7fd4a-128">TotalTime</span></span> | <span data-ttu-id="7fd4a-129">이 프로세스에서 액세스한 파일 검색에 소요된 누적 기간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-129">The cumulative duration in milliseconds spent in scans of files accessed by this process</span></span> |
|<span data-ttu-id="7fd4a-130">Count</span><span class="sxs-lookup"><span data-stu-id="7fd4a-130">Count</span></span> | <span data-ttu-id="7fd4a-131">이 프로세스에서 액세스하는 검사된 파일 수</span><span class="sxs-lookup"><span data-stu-id="7fd4a-131">The number of scanned files accessed by this process</span></span> |
|<span data-ttu-id="7fd4a-132">MaxTime</span><span class="sxs-lookup"><span data-stu-id="7fd4a-132">MaxTime</span></span> |  <span data-ttu-id="7fd4a-133">이 프로세스에서 액세스하는 파일의 가장 긴 단일 검색 기간(밀리초)입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-133">The duration in milliseconds in the longest single scan of a file accessed by this process</span></span> |
| <span data-ttu-id="7fd4a-134">MaxTimeFile</span><span class="sxs-lookup"><span data-stu-id="7fd4a-134">MaxTimeFile</span></span> | <span data-ttu-id="7fd4a-135">가장 긴 기간 스캔이 기록된 이 프로세스에서 액세스하는 `MaxTime` 파일의 경로입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-135">The path of the file accessed by this process for which the longest scan of `MaxTime` duration was recorded</span></span> |
| <span data-ttu-id="7fd4a-136">EstimatedImpact</span><span class="sxs-lookup"><span data-stu-id="7fd4a-136">EstimatedImpact</span></span> | <span data-ttu-id="7fd4a-137">이 프로세스에서 검색 활동을 경험한 기간을 지난 기간 동안 이 프로세스에서 액세스한 파일을 검색하는 데 소요된 시간의 백분율</span><span class="sxs-lookup"><span data-stu-id="7fd4a-137">The percentage of time spent in scans for files accessed by this process out of the period in which this process experienced scan activity</span></span> |

<span data-ttu-id="7fd4a-138">성능에 큰 영향을 미치는 경우 [Configure and validate exclusions for Microsoft Defender Antivirus scans의](collect-diagnostic-data.md)단계에 따라 경로/프로세스 제외에 프로세스를 추가해 세요.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-138">If the performance impact is high, try adding the process to the Path/Process exclusions by following the steps in [Configure and validate exclusions for Microsoft Defender Antivirus scans](collect-diagnostic-data.md).</span></span>

<span data-ttu-id="7fd4a-139">이전 단계로 문제가 해결되지 않는 경우 다음 섹션의 [](#capture-process-logs-using-process-monitor) 프로세스 모니터 또는 [Windows Performance Recorder를](#capture-performance-logs-using-windows-performance-recorder) 통해 추가 정보를 수집할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-139">If the previous step doesn't solve the problem, you can collect more information through the [Process Monitor](#capture-process-logs-using-process-monitor) or the [Windows Performance Recorder](#capture-performance-logs-using-windows-performance-recorder) in the following sections.</span></span>
     
## <a name="capture-process-logs-using-process-monitor"></a><span data-ttu-id="7fd4a-140">프로세스 모니터를 사용하여 프로세스 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-140">Capture process logs using Process Monitor</span></span>

<span data-ttu-id="7fd4a-141">프로세스 모니터(ProcMon)는 실시간 프로세스를 표시하는 고급 모니터링 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-141">Process Monitor (ProcMon) is an advanced monitoring tool that can show real-time processes.</span></span> <span data-ttu-id="7fd4a-142">이 기능을 사용하여 발생하는 성능 문제를 캡처할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-142">You can use this to capture the performance issue as it is occurring.</span></span>

1. <span data-ttu-id="7fd4a-143">프로세스 [모니터 v3.60을](/sysinternals/downloads/procmon) 같은 폴더로 다운로드합니다. `C:\temp`</span><span class="sxs-lookup"><span data-stu-id="7fd4a-143">Download [Process Monitor v3.60](/sysinternals/downloads/procmon) to a folder like `C:\temp`.</span></span>

2. <span data-ttu-id="7fd4a-144">웹의 파일 표시를 제거하려면</span><span class="sxs-lookup"><span data-stu-id="7fd4a-144">To remove the file's mark of the web:</span></span>
    1. <span data-ttu-id="7fd4a-145">마우스 오른쪽 **단추로ProcessMonitor.zip** 속성을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-145">Right-click **ProcessMonitor.zip** and select **Properties**.</span></span>
    1. <span data-ttu-id="7fd4a-146">일반 *탭에서* 보안 을 *찾아 봐야 합니다.*</span><span class="sxs-lookup"><span data-stu-id="7fd4a-146">Under the *General* tab, look for *Security*.</span></span>
    1. <span data-ttu-id="7fd4a-147">차단 해제 **옆의 확인란을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-147">Check the box beside **Unblock**.</span></span>
    1. <span data-ttu-id="7fd4a-148">**적용** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-148">Select **Apply**.</span></span>
    
    ![MOTW 제거](images/procmon-motw.png) 

3. <span data-ttu-id="7fd4a-150">폴더 경로가 으로 표시될 수 있도록 파일에서 `C:\temp` 파일의zip을 `C:\temp\ProcessMonitor` 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-150">Unzip the file in `C:\temp` so that the folder path will be `C:\temp\ProcessMonitor`.</span></span> 

4. <span data-ttu-id="7fd4a-151">문제를 **ProcMon.exe**  Windows 클라이언트 또는 Windows 서버에 복사합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-151">Copy **ProcMon.exe**  to the Windows client or Windows server you're troubleshooting.</span></span>  

5. <span data-ttu-id="7fd4a-152">ProcMon을 실행하기 전에 CPU 사용량이 높은 문제와 관련이 없는 다른 모든 응용 프로그램을 닫아야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-152">Before running ProcMon, make sure all other applications not related to the high CPU usage issue are closed.</span></span> <span data-ttu-id="7fd4a-153">이렇게 하면 확인할 프로세스 수가 최소화됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-153">Doing this will minimize the number of processes to check.</span></span>

6. <span data-ttu-id="7fd4a-154">ProcMon은 두 가지 방법으로 실행될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-154">You can launch ProcMon in two ways.</span></span>
    1. <span data-ttu-id="7fd4a-155">마우스 오른쪽 **단추로ProcMon.exe** 관리자 **권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-155">Right-click **ProcMon.exe** and select **Run as administrator**.</span></span> 
    

        <span data-ttu-id="7fd4a-156">로깅이 자동으로 시작되면 돋보기 아이콘을 선택하여 현재 캡처를 중지하거나 바로 가기 **키 Ctrl+E를 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-156">Since logging starts automatically, select the magnifying glass icon  to stop the current capture or use the keyboard shortcut **Ctrl+E**.</span></span>
 
        ![돋보기 아이콘](images/procmon-magglass.png)

        <span data-ttu-id="7fd4a-158">캡처를 중지했다는 확인을 위해 돋보기 아이콘이 빨간색 X와 함께 나타나는지 여부를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-158">To verify that you have stopped the capture, check if the magnifying glass icon now appears with a red X.</span></span>

        ![빨간색 슬래시](images/procmon-magglass-stop.png)         

        <span data-ttu-id="7fd4a-160">다음으로, 이전 캡처를 지우기 위해 지우개 아이콘을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-160">Next, to clear the earlier capture, select the eraser icon.</span></span>

        ![지우기 아이콘](images/procmon-eraser-clear.png)

        <span data-ttu-id="7fd4a-162">또는 바로 가기 키 **Ctrl+X를 사용합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-162">Or use the keyboard shortcut **Ctrl+X**.</span></span>

    2. <span data-ttu-id="7fd4a-163">두 번째 방법은 명령줄을 관리자로 실행한 다음 프로세스 모니터 경로에서 다음을 실행하는 것입니다. </span><span class="sxs-lookup"><span data-stu-id="7fd4a-163">The second way is to run the **command line** as admin, then from the Process Monitor path, run:</span></span>

        ![cmd procmon](images/cmd-procmon.png)
 
        ```console
        Procmon.exe /AcceptEula /Noconnect /Profiling
        ```
        
        >[!TIP] 
        ><span data-ttu-id="7fd4a-165">데이터를 캡처할 때 ProcMon 창을 최대한 작게 만들어 추적을 쉽게 시작 및 중지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-165">Make the ProcMon window as small as possible when capturing data so you can easily start and stop the trace.</span></span>
        > 
        >![Procmon 최소화](images/procmon-minimize.png)
    
7. <span data-ttu-id="7fd4a-167">6단계의 절차 중 하나를 수행한 후 필터를 설정하는 옵션이 표시될 것입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-167">After following one of the procedures in step 6, you'll next see an option to set filters.</span></span> <span data-ttu-id="7fd4a-168">**확인** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-168">Select **OK**.</span></span> <span data-ttu-id="7fd4a-169">캡처가 완료된 후 항상 결과를 필터링할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-169">You can always filter the results after the capture is completed.</span></span>
 
    ![시스템 제외 프로세스 이름 필터링](images/procmon-filter-options.png) 

8. <span data-ttu-id="7fd4a-171">캡처를 시작하려면 돋보기 아이콘을 다시 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-171">To start the capture, select the magnifying glass icon again.</span></span>
     
9. <span data-ttu-id="7fd4a-172">문제를 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-172">Reproduce the problem.</span></span>
 
    >[!TIP] 
    ><span data-ttu-id="7fd4a-173">문제가 완전히 재현될 때까지 기다렸다가 추적이 시작될 때 타임스탬프를 기록합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-173">Wait for the problem to be fully reproduced, then take note of the timestamp when the trace started.</span></span>

10. <span data-ttu-id="7fd4a-174">높은 CPU 사용량 조건에서 2-4분의 프로세스 활동이 있는 경우 돋보기 아이콘을 선택하여 캡처를 중지합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-174">Once you have two to four minutes of process activity during the high CPU usage condition, stop the capture by selecting the magnifying glass icon.</span></span>

11. <span data-ttu-id="7fd4a-175">고유한 이름과 .pml 형식으로 캡처를 저장하려면 **파일,** **저장... 을 선택합니다.** 라디오 단추 모든 이벤트  및 네이티브 프로세스 모니터 **형식(PML)을 선택해야 합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-175">To save the capture with a unique name and with the .pml format, select **File** then select **Save...**. Make sure to select the radio buttons **All events** and **Native Process Monitor Format (PML)**.</span></span>

    ![설정 저장](images/procmon-savesettings1.png)

12. <span data-ttu-id="7fd4a-177">더 나은 추적을 위해 기본 경로를 다음 위치로 `C:\temp\ProcessMonitor\LogFile.PML` `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` 변경합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-177">For better tracking, change the default path from `C:\temp\ProcessMonitor\LogFile.PML` to `C:\temp\ProcessMonitor\%ComputerName%_LogFile_MMDDYEAR_Repro_of_issue.PML` where:</span></span>
    - <span data-ttu-id="7fd4a-178">`%ComputerName%` 은 장치 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-178">`%ComputerName%` is the device name</span></span>
    - <span data-ttu-id="7fd4a-179">`MMDDYEAR` 은 월, 일 및 연도입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-179">`MMDDYEAR` is the month, day, and year</span></span>
    -  <span data-ttu-id="7fd4a-180">`Repro_of_issue` 은 재현하려는 문제의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-180">`Repro_of_issue` is the name of the issue you're trying to reproduce</span></span>

    >[!TIP] 
    > <span data-ttu-id="7fd4a-181">작업 시스템이 있는 경우 비교할 샘플 로그를 얻을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-181">If you have a working system, you might want to get a sample log to compare.</span></span>

13. <span data-ttu-id="7fd4a-182">.pml 파일을 압축하고 Microsoft 지원에 제출합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-182">Zip the .pml file and submit it to Microsoft support.</span></span>


## <a name="capture-performance-logs-using-windows-performance-recorder"></a><span data-ttu-id="7fd4a-183">Windows Performance Recorder를 사용하여 성능 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-183">Capture performance logs using Windows Performance Recorder</span></span>

<span data-ttu-id="7fd4a-184">WPR(Windows Performance Recorder)을 사용하여 Microsoft 지원에 제출할 추가 정보를 포함할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-184">You can use Windows Performance Recorder (WPR) to include additional information in your submission to Microsoft support.</span></span> <span data-ttu-id="7fd4a-185">WPR은 Windows 기록에 대한 이벤트 추적을 만드는 강력한 기록 도구입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-185">WPR is a powerful recording tool that creates Event Tracing for Windows recordings.</span></span> 

<span data-ttu-id="7fd4a-186">WPR은 Windows ADK(Windows Assessment and Deployment Kit)의 일부로, Windows ADK 다운로드 및 설치에서 [다운로드할 수 있습니다.](/windows-hardware/get-started/adk-install)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-186">WPR is part of the Windows Assessment and Deployment Kit (Windows ADK) and can be downloaded from [Download and install the Windows ADK](/windows-hardware/get-started/adk-install).</span></span> <span data-ttu-id="7fd4a-187">Windows 10 [SDK에서 Windows 10](https://developer.microsoft.com/windows/downloads/windows-10-sdk/)소프트웨어 개발 키트의 일부로 다운로드할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-187">You can also download it as part of the Windows 10 Software Development Kit at [Windows 10 SDK](https://developer.microsoft.com/windows/downloads/windows-10-sdk/).</span></span>

<span data-ttu-id="7fd4a-188">WPR UI를 사용하여 성능 로그 캡처의 단계에 따라 WPR 사용자 인터페이스를 [사용할 수 있습니다.](#capture-performance-logs-using-the-wpr-ui)</span><span class="sxs-lookup"><span data-stu-id="7fd4a-188">You can use the WPR user interface by following the steps in [Capture performance logs using the WPR UI](#capture-performance-logs-using-the-wpr-ui).</span></span> 

<span data-ttu-id="7fd4a-189">또는 [WPR CLI를](#capture-performance-logs-using-the-wpr-cli)사용하여 성능 *로그 캡처의 단계에* 따라 Windows 8 이상 버전에서 사용할wpr.exe명령줄 도구인 를 사용할 수도 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-189">Alternatively, you can also use the command-line tool *wpr.exe*, which is available in Windows 8 and later versions  by following the steps in [Capture performance logs using the WPR CLI](#capture-performance-logs-using-the-wpr-cli).</span></span>


### <a name="capture-performance-logs-using-the-wpr-ui"></a><span data-ttu-id="7fd4a-190">WPR UI를 사용하여 성능 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-190">Capture performance logs using the WPR UI</span></span>

>[!TIP]
><span data-ttu-id="7fd4a-191">문제가 발생하는 디바이스가 여러 개 있는 경우 RAM이 가장 많은 장치를 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-191">If you have multiple devices where the issue is occurring, use the one which has the most amount of RAM.</span></span>

1. <span data-ttu-id="7fd4a-192">WPR을 다운로드하여 설치합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-192">Download and install WPR.</span></span>

2. <span data-ttu-id="7fd4a-193">*Windows 키트에서* **Windows Performance Recorder 를 마우스 오른쪽 단추로 클릭합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-193">Under *Windows Kits*, right-click **Windows Performance Recorder**.</span></span> 

    ![시작 메뉴](images/wpr-01.png)

    <span data-ttu-id="7fd4a-195">추가 **를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-195">Select **More**.</span></span> <span data-ttu-id="7fd4a-196">관리자 **권한으로 실행을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-196">Select **Run as administrator**.</span></span>

3. <span data-ttu-id="7fd4a-197">사용자 계정 컨트롤 대화 상자가 나타나면 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-197">When the User Account Control dialog box appears, select **Yes**.</span></span>

    ![UAC](images/wpt-yes.png)

4. <span data-ttu-id="7fd4a-199">그런 다음 [끝점용 Microsoft Defender 분석](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) 프로필을 다운로드하고 과 같은 `WD.wprp` 폴더에 `C:\temp` 저장합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-199">Next, download the [Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp) profile and save as `WD.wprp` to a folder like `C:\temp`.</span></span> 
     
5. <span data-ttu-id="7fd4a-200">WPR 대화 상자에서 추가 옵션을 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-200">On the WPR dialog box, select **More options**.</span></span>

    ![다른 옵션 선택](images/wpr-03.png)

6. <span data-ttu-id="7fd4a-202">프로필 **추가...를** 선택하고 파일의 경로를 `WD.wprp` 탐색합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-202">Select **Add Profiles...** and browse to the path of the `WD.wprp` file.</span></span>

7. <span data-ttu-id="7fd4a-203">그런 다음 사용자 지정 측정 아래에  끝점 *분석용 Microsoft Defender라는* 새 프로필 집합이 표시됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-203">After that, you should see a new profile set under *Custom measurements* named *Microsoft Defender for Endpoint analysis* underneath it.</span></span>

    ![파일 내](images/wpr-infile.png)

    >[!WARNING]
    ><span data-ttu-id="7fd4a-205">Windows Server에 64GB 이상의 RAM이 있는 경우 대신 사용자 지정 측정을 `Microsoft Defender for Endpoint analysis for large servers` `Microsoft Defender for Endpoint analysis` 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-205">If your Windows Server has 64 GB of RAM or more, use the custom measurement `Microsoft Defender for Endpoint analysis for large servers` instead of `Microsoft Defender for Endpoint analysis`.</span></span> <span data-ttu-id="7fd4a-206">그렇지 않으면 시스템에서 많은 양의 비페이지 풀 메모리 또는 버퍼를 사용할 수 있으며, 이로 인해 시스템 비보안이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-206">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span> <span data-ttu-id="7fd4a-207">자원 분석을 확장하여 추가할 **프로필을 선택할 수 있습니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-207">You can choose which profiles to add by expanding **Resource Analysis**.</span></span> <span data-ttu-id="7fd4a-208">이 사용자 지정 프로필은 자세한 성능 분석에 필요한 컨텍스트를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-208">This custom profile provides the necessary context for in-depth performance analysis.</span></span>
 
8. <span data-ttu-id="7fd4a-209">WPR UI에서 사용자 지정 측정 Microsoft Defender for Endpoint 자세한 분석 프로필을 사용하려면</span><span class="sxs-lookup"><span data-stu-id="7fd4a-209">To use the custom measurement Microsoft Defender for Endpoint verbose analysis profile in the WPR UI:</span></span>

    1. <span data-ttu-id="7fd4a-210">첫 번째 수준 *Triage,* Resource Analysis and Scenario *Analysis* groups에서 프로필을 *선택하지 않도록* 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-210">Ensure no profiles are selected under the *First-level triage*, *Resource Analysis* and *Scenario Analysis* groups.</span></span>
    2. <span data-ttu-id="7fd4a-211">사용자 **지정 측정을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-211">Select **Custom measurements**.</span></span>
    3. <span data-ttu-id="7fd4a-212">끝점 **분석용 Microsoft Defender를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-212">Select **Microsoft Defender for Endpoint analysis**.</span></span>
    4. <span data-ttu-id="7fd4a-213">세부 **정보 수준에서 자세한** *정보를* 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-213">Select **Verbose** under *Detail* level.</span></span>
    1. <span data-ttu-id="7fd4a-214">로깅 **모드에서** 파일 또는 **메모리를** 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-214">Select **File** or **Memory** under Logging mode.</span></span> 

    >[!important]
    ><span data-ttu-id="7fd4a-215">사용자가 성능  문제를 직접 재현할 수 있는 경우 파일 로깅 모드를 사용하려면 파일을 선택해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-215">You should select *File* to use the file logging mode if the performance issue can be reproduced directly by the user.</span></span> <span data-ttu-id="7fd4a-216">대부분의 문제는 이 범주에 속합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-216">Most issues fall under this category.</span></span> <span data-ttu-id="7fd4a-217">그러나 사용자가 직접 문제를 재현할 수 없지만 문제가 발생하면 쉽게 알 수  있는 경우 메모리를 선택하여 메모리 로깅 모드를 사용해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-217">However, if the user cannot directly reproduce the issue but can easily notice it once the issue occurs, the user should select *Memory* to use the memory logging mode.</span></span> <span data-ttu-id="7fd4a-218">이렇게 하면 추적 로그가 장기 실행 시간으로 인해 과도하게 노출되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-218">This ensures that the trace log will not inflate excessively due to the long run time.</span></span>

9. <span data-ttu-id="7fd4a-219">이제 데이터를 수집할 준비가 완료되었습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-219">Now you're ready to collect data.</span></span> <span data-ttu-id="7fd4a-220">성능 문제를 다시 재현하는 데 관련이 없는 모든 응용 프로그램을 종료합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-220">Exit all the applications that are not relevant to reproducing the performance issue.</span></span> <span data-ttu-id="7fd4a-221">옵션 **숨기기** 옵션을 선택하여 WPR 창에 차지하는 공간을 작게 유지할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-221">You can select **Hide options** to keep the space occupied by the WPR window small.</span></span>

    ![Hipe 옵션](images/wpr-08.png)

    >[!TIP]
    ><span data-ttu-id="7fd4a-223">정수 초에 추적을 시작해 하세요.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-223">Try starting the trace at whole number seconds.</span></span> <span data-ttu-id="7fd4a-224">예를 들어 01:30:00입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-224">For instance, 01:30:00.</span></span> <span data-ttu-id="7fd4a-225">이렇게 하면 데이터를 보다 쉽게 분석할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-225">This will make it easier to analyze the data.</span></span> <span data-ttu-id="7fd4a-226">또한 문제가 재현된 정확한 타임스탬프를 추적하려고 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-226">Also try to keep track of the timestamp of exactly when the issue is reproduced.</span></span>

10. <span data-ttu-id="7fd4a-227">**시작** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-227">Select **Start**.</span></span>

    ![추적 시작 선택](images/wpr-09.png)

11. <span data-ttu-id="7fd4a-229">문제를 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-229">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="7fd4a-230">데이터 수집을 5분까지 유지하십시오.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-230">Keep the data collection to no more than five minutes.</span></span> <span data-ttu-id="7fd4a-231">2~3분은 많은 데이터가 수집되고 있는 것이 좋은 범위입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-231">Two to three minutes is a good range since a lot of data is being collected.</span></span>

12. <span data-ttu-id="7fd4a-232">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-232">Select **Save**.</span></span>

    ![저장 선택](images/wpr-10.png)

13. <span data-ttu-id="7fd4a-234">문제 **및** 문제를 재현한 방법에 대한 정보를 입력하여 자세한 문제 설명을 입력합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-234">Fill up **Type in a detailed description of the problem:** with information about the problem and how you reproduced the issue.</span></span>

    ![세부 정보 채우기](images/wpr-12.png)

    1. <span data-ttu-id="7fd4a-236">파일 **이름:** 추적 파일을 저장할 위치를 결정하려면 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-236">Select **File Name:** to determine where your trace file will be saved.</span></span> <span data-ttu-id="7fd4a-237">기본적으로 에 1.is `%user%\Documents\WPR Files\` 저장됩니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-237">By default, it 1.is saved to `%user%\Documents\WPR Files\`.</span></span>
    1. <span data-ttu-id="7fd4a-238">**저장** 을 선택합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-238">Select **Save**.</span></span>

14. <span data-ttu-id="7fd4a-239">추적이 병합되는 동안 기다릴 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-239">Wait while the trace is being merged.</span></span>

    ![WPR 수집 일반 추적](images/wpr-13.png)

15. <span data-ttu-id="7fd4a-241">추적이 저장되고 나면 폴더 **열기 를 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-241">Once the trace is saved, select **Open folder**.</span></span>

    ![저장된 WPR 추적](images/wpr-14.png)

    <span data-ttu-id="7fd4a-243">Microsoft 지원에 제출할 파일과 폴더를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-243">Include both the file and the folder in your submission to Microsoft support.</span></span>

    ![파일 및 폴더](images/wpr-15.png)

### <a name="capture-performance-logs-using-the-wpr-cli"></a><span data-ttu-id="7fd4a-245">WPR CLI를 사용하여 성능 로그 캡처</span><span class="sxs-lookup"><span data-stu-id="7fd4a-245">Capture performance logs using the WPR CLI</span></span>

<span data-ttu-id="7fd4a-246">명령줄 *도구는* wpr.exeWindows 8부터 운영 체제의 일부입니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-246">The command-line tool *wpr.exe* is part of the operating system starting with Windows 8.</span></span> <span data-ttu-id="7fd4a-247">명령줄 도구를 사용하여 WPR 추적을 수집하려면 다음을 wpr.exe.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-247">To collect a WPR trace using the command-line tool wpr.exe:</span></span>

1. <span data-ttu-id="7fd4a-248">성능 추적을 위해 끝점 분석 프로필에 대한 **[Microsoft Defender를](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** 다운로드하여 같은 로컬 디렉터리에 있는 파일에 `WD.wprp` 대한 성능 추적을 다운로드합니다. `C:\traces`</span><span class="sxs-lookup"><span data-stu-id="7fd4a-248">Download **[Microsoft Defender for Endpoint analysis](https://github.com/YongRhee-MDE/Scripts/blob/master/MDAV.wprp)** profile for performance traces to a file named `WD.wprp` in a local directory such as `C:\traces`.</span></span>

3. <span data-ttu-id="7fd4a-249">시작 메뉴  아이콘을 마우스 **오른쪽 단추로 클릭하고 Windows PowerShell(관리자)** 또는 명령 프롬프트(관리자)를 선택하여 관리자 명령 프롬프트 창을 열 수 있습니다. </span><span class="sxs-lookup"><span data-stu-id="7fd4a-249">Right-click the **Start Menu** icon and select **Windows PowerShell (Admin)** or **Command Prompt (Admin)** to open an Admin command prompt window.</span></span>

4. <span data-ttu-id="7fd4a-250">사용자 계정 컨트롤 대화 상자가 나타나면 예를 **선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="7fd4a-250">When the User Account Control dialog box appears, select **Yes**.</span></span>

5. <span data-ttu-id="7fd4a-251">승격된 프롬프트에서 다음 명령을 실행하여 끝점 성능 추적에 대한 Microsoft Defender를 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-251">At the elevated prompt, run the following command to start a Microsoft Defender for Endpoint performance trace:</span></span>

    ```console
    wpr.exe -start C:\traces\WD.wprp!WD.Verbose -filemode
    ```
    
    >[!WARNING]
    ><span data-ttu-id="7fd4a-252">Windows Server에 64GB 이상의 RAM이 있는 경우 각각 프로필 및 대신 프로필을 `WDForLargeServers.Light` `WDForLargeServers.Verbose` `WD.Light` `WD.Verbose` 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-252">If your Windows Server has 64 GB or RAM or more, use profiles `WDForLargeServers.Light` and `WDForLargeServers.Verbose` instead of profiles `WD.Light` and `WD.Verbose`, respectively.</span></span> <span data-ttu-id="7fd4a-253">그렇지 않으면 시스템에서 많은 양의 비페이지 풀 메모리 또는 버퍼를 사용할 수 있으며, 이로 인해 시스템 비보안이 발생할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-253">Otherwise, your system could consume a high amount of non-paged pool memory or buffers which can lead to system instability.</span></span>

6. <span data-ttu-id="7fd4a-254">문제를 재현합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-254">Reproduce the issue.</span></span>

    >[!TIP]
    ><span data-ttu-id="7fd4a-255">데이터 수집을 5분 이상 유지하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-255">Keep the data collection no to more than five minutes.</span></span>  <span data-ttu-id="7fd4a-256">시나리오에 따라 많은 데이터가 수집되고 있는 것이 2~3분 정도면 좋습니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-256">Depending on the scenario, two to three minutes is a good range since a lot of data is being collected.</span></span>

7. <span data-ttu-id="7fd4a-257">승강된 프롬프트에서 다음 명령을 실행하여 성능 추적을 중지하고 문제 및 문제를 재현한 방법에 대한 정보를 제공해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-257">At the elevated prompt, run the following command to stop the performance trace, making sure to provide information about the problem and how you reproduced the issue:</span></span>

    ```console
    wpr.exe -stop merged.etl "Timestamp when the issue was reproduced, in HH:MM:SS format" "Description of the issue" "Any error that popped up"
    ```

8. <span data-ttu-id="7fd4a-258">추적이 병합될 때까지 기다렸다가</span><span class="sxs-lookup"><span data-stu-id="7fd4a-258">Wait until the trace is merged.</span></span> 

9. <span data-ttu-id="7fd4a-259">Microsoft 지원에 제출할 파일과 폴더를 모두 포함합니다.</span><span class="sxs-lookup"><span data-stu-id="7fd4a-259">Include both the file and the folder in your submission to Microsoft support.</span></span>

## <a name="see-also"></a><span data-ttu-id="7fd4a-260">참고 항목</span><span class="sxs-lookup"><span data-stu-id="7fd4a-260">See also</span></span>

- [<span data-ttu-id="7fd4a-261">Microsoft Defender 바이러스 백신 진단 데이터 수집</span><span class="sxs-lookup"><span data-stu-id="7fd4a-261">Collect Microsoft Defender Antivirus diagnostic data</span></span>](collect-diagnostic-data.md)
- [<span data-ttu-id="7fd4a-262">Microsoft Defender 바이러스 백신 검사에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="7fd4a-262">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
