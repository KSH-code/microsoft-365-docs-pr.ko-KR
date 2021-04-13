---
title: macOS용 MDATP를 통해 스캔을 예약하는 방법
description: 조직의 자산을 보다 잘 보호하기 위해 macOS에서 Microsoft Defender ATP에 대한 자동 검사 시간을 예약하는 방법을 학습합니다.
keywords: microsoft, defender, atp, mac, 검사, 바이러스 백신
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
ms.openlocfilehash: ecfae62bdc092a0b2544bf6f6a76dad1e86b8ab4
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689596"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-on-macos"></a><span data-ttu-id="0d461-104">MacOS의 끝점에 대한 Microsoft Defender 검사 예약</span><span class="sxs-lookup"><span data-stu-id="0d461-104">Schedule scans with Microsoft Defender for Endpoint on macOS</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0d461-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="0d461-105">**Applies to:**</span></span>
- <span data-ttu-id="0d461-106">[엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) </span><span class="sxs-lookup"><span data-stu-id="0d461-106">[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)</span></span>
- [<span data-ttu-id="0d461-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0d461-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="0d461-108">끝점용 Microsoft Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="0d461-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="0d461-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="0d461-110">Microsoft Defender for Endpoint를 사용하여 위협 검색을 시작할 수 있는 동안에는 엔터프라이즈에서 예약된 검사나 시간이 정해진 검사의 혜택을 받을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-110">While you can start a threat scan at any time with Microsoft Defender for Endpoint, your enterprise might benefit from scheduled or timed scans.</span></span> <span data-ttu-id="0d461-111">예를 들어 모든 작업일 또는 주가 시작될 때 검사 실행을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-111">For example, you can schedule a scan to run at the beginning of every workday or week.</span></span> 

## <a name="schedule-a-scan-with-launchd"></a><span data-ttu-id="0d461-112">시작된 검사 *예약*</span><span class="sxs-lookup"><span data-stu-id="0d461-112">Schedule a scan with *launchd*</span></span>

<span data-ttu-id="0d461-113">macOS 디바이스에서 시작된  데몬을 사용하여 스캔 일정을 만들 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-113">You can create a scanning schedule using the *launchd* daemon on a macOS device.</span></span>

1. <span data-ttu-id="0d461-114">다음 코드에서는 검색을 예약하는 데 필요한 스마마를 보여 주며,</span><span class="sxs-lookup"><span data-stu-id="0d461-114">The following code shows the schema you need to use to schedule a scan.</span></span> <span data-ttu-id="0d461-115">텍스트 편집기를 열고 이 예제를 예약된 자체 검사 파일에 대한 가이드로 사용하세요.</span><span class="sxs-lookup"><span data-stu-id="0d461-115">Open a text editor and use this example as a guide for your own scheduled scan file.</span></span>

    <span data-ttu-id="0d461-116">여기에 사용된 *.plist* 파일 형식에 대한 자세한 내용은 공식 Apple 개발자 웹 사이트에서 [정보 속성](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 목록 파일 정보를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d461-116">For more information on the *.plist* file format used here, see [About Information Property List Files](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) at the official Apple developer website.</span></span>

    ```XML
    <?xml version="1.0" encoding="UTF-8"?>
    <!DOCTYPE plist PUBLIC "-//Apple//DTD PLIST 1.0//EN"
      "http://www.apple.com/DTDs/PropertyList-1.0.dtd">
    <plist version="1.0">
    <dict>
        <key>Label</key>
        <string>com.microsoft.wdav.schedquickscan</string>
        <key>ProgramArguments</key>
        <array>
            <string>sh</string>
            <string>-c</string>
            <string>/usr/local/bin/mdatp scan quick</string>
        </array>
        <key>RunAtLoad</key>
        <true/>
        <key>StartCalendarInterval</key>
        <dict>
            <key>Day</key>
            <integer>3</integer>
            <key>Hour</key>
            <integer>2</integer>
            <key>Minute</key>
            <integer>0</integer>
            <key>Weekday</key>
            <integer>5</integer>
        </dict>
        <key>WorkingDirectory</key>
        <string>/usr/local/bin/</string>
    </dict>
    </plist>
     ```

2. <span data-ttu-id="0d461-117">파일을 *com.microsoft.wdav.schedquickscan.plist 로 저장합니다.*</span><span class="sxs-lookup"><span data-stu-id="0d461-117">Save the file as *com.microsoft.wdav.schedquickscan.plist*.</span></span>

    > [!TIP]
    > <span data-ttu-id="0d461-118">빠른 검사 대신 전체 검색을 실행하기 위해 줄 12, 를 변경하여 대신 옵션을 사용하여 파일을 `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched quick scan.plist 대신com.microsoft.wdav.sched full scan.plist로* 저장합니다. \*\*</span><span class="sxs-lookup"><span data-stu-id="0d461-118">To run a full scan instead of a quick scan, change line 12, `<string>/usr/local/bin/mdatp scan quick</string>`, to use the `full` option instead of `quick` (i.e. `<string>/usr/local/bin/mdatp scan full</string>`) and save the file as *com.microsoft.wdav.sched **full** scan.plist* instead of *com.microsoft.wdav.sched **quick** scan.plist*.</span></span>

3. <span data-ttu-id="0d461-119">**터미널을**</span><span class="sxs-lookup"><span data-stu-id="0d461-119">Open **Terminal**.</span></span>
4. <span data-ttu-id="0d461-120">다음 명령을 입력하여 파일을 로드합니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-120">Enter the following commands to load your file:</span></span>

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. <span data-ttu-id="0d461-121">예약된 검사는 p-list에 정의한 날짜, 시간 및 빈도에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-121">Your scheduled scan will run at the date, time, and frequency you defined in your p-list.</span></span> <span data-ttu-id="0d461-122">이 예제에서는 검사가 매주 금요일 오전 2시에 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-122">In the example, the scan runs at 2:00 AM every Friday.</span></span> 

    <span data-ttu-id="0d461-123">값은 정수로 주 5일을 나타내거나 `Weekday` `StartCalendarInterval` 금요일을 나타냅니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-123">The `Weekday` value of `StartCalendarInterval` uses an integer to indicate the fifth day of the week, or Friday.</span></span>

 > [!IMPORTANT]
 > <span data-ttu-id="0d461-124">시작된 에이전트는  장치가 잠기고 있는 동안 예약된 시간으로 실행되지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-124">Agents executed with *launchd* will not run at the scheduled time while the device is asleep.</span></span> <span data-ttu-id="0d461-125">대신 장치가 절전 모드에서 다시 시작된 후 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-125">They will instead run once the device resumes from sleep mode.</span></span>
 >
 > <span data-ttu-id="0d461-126">디바이스가 꺼져 있는 경우 다음에 예약된 검사 시에 검사가 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-126">If the device is turned off, the scan will run at the next scheduled scan time.</span></span>

## <a name="schedule-a-scan-with-intune"></a><span data-ttu-id="0d461-127">Intune을 통해 검사 예약</span><span class="sxs-lookup"><span data-stu-id="0d461-127">Schedule a scan with Intune</span></span>

<span data-ttu-id="0d461-128">Microsoft Intune을 사용하여 검색을 예약할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-128">You can also schedule scans with Microsoft Intune.</span></span> <span data-ttu-id="0d461-129">디바이스가 [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 모드로 다시 시작되면 [Scripts for Microsoft Defender for Endpoint에서](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) 사용할 수 있는 runMDATPQuickScan.sh 셸 스크립트가 지속됩니다.</span><span class="sxs-lookup"><span data-stu-id="0d461-129">The [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) shell script available at [Scripts for Microsoft Defender for Endpoint](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) will persist when the device resumes from sleep mode.</span></span> 

<span data-ttu-id="0d461-130">엔터프라이즈에서 이 스크립트를 사용하는 방법에 대한 자세한 내용은 [Intune에서 macOS](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 장치에서 셸 스크립트 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="0d461-130">See [Use shell scripts on macOS devices in Intune](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) for more detailed instructions on how to use this script in your enterprise.</span></span>
