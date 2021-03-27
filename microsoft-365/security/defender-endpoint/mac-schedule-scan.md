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
ms.openlocfilehash: 4694ff0c0d0892b9261e61683654dfb58dfd724b
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394768"
---
# <a name="schedule-scans-with-microsoft-defender-for-endpoint-for-mac"></a>Mac용 끝점에 대한 Microsoft Defender 검사 예약

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037) 
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Microsoft Defender for Endpoint를 사용하여 위협 검색을 시작할 수 있는 동안에는 엔터프라이즈에서 예약된 검사나 시간이 정해진 검사의 혜택을 받을 수 있습니다. 예를 들어 모든 작업일 또는 주가 시작될 때 검사 실행을 예약할 수 있습니다. 

## <a name="schedule-a-scan-with-launchd"></a>시작된 검사 *예약*

macOS 디바이스에서 시작된  데몬을 사용하여 스캔 일정을 만들 수 있습니다.

1. 다음 코드에서는 검색을 예약하는 데 필요한 스마마를 보여 주며, 텍스트 편집기를 열고 이 예제를 예약된 자체 검사 파일에 대한 가이드로 사용하세요.

    여기에 사용된 *.plist* 파일 형식에 대한 자세한 내용은 공식 Apple 개발자 웹 사이트에서 [정보 속성](https://developer.apple.com/library/archive/documentation/General/Reference/InfoPlistKeyReference/Articles/AboutInformationPropertyListFiles.html) 목록 파일 정보를 참조하세요.

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

2. 파일을 *com.microsoft.wdav.schedquickscan.plist 로 저장합니다.*

    > [!TIP]
    > 빠른 검사 대신 전체 검색을 실행하기 위해 줄 12, 를 변경하여 대신 옵션을 사용하여 파일을 `<string>/usr/local/bin/mdatp scan quick</string>` `full` `quick` `<string>/usr/local/bin/mdatp scan full</string>` *com.microsoft.wdav.sched quick scan.plist 대신com.microsoft.wdav.sched full scan.plist로* 저장합니다. **

3. **터미널을**
4. 다음 명령을 입력하여 파일을 로드합니다.

    ```bash
    launchctl load /Library/LaunchDaemons/<your file name.plist>
    launchctl start <your file name>
    ```

5. 예약된 검사는 p-list에 정의한 날짜, 시간 및 빈도에 실행됩니다. 이 예제에서는 검사가 매주 금요일 오전 2시에 실행됩니다. 

    값은 정수로 주 5일을 나타내거나 `Weekday` `StartCalendarInterval` 금요일을 나타냅니다.

 > [!IMPORTANT]
 > 시작된 에이전트는  장치가 잠기고 있는 동안 예약된 시간으로 실행되지 않습니다. 대신 장치가 절전 모드에서 다시 시작된 후 실행됩니다.
 >
 > 디바이스가 꺼져 있는 경우 다음에 예약된 검사 시에 검사가 실행됩니다.

## <a name="schedule-a-scan-with-intune"></a>Intune을 통해 검사 예약

Microsoft Intune을 사용하여 검색을 예약할 수 있습니다. 디바이스가 [runMDATPQuickScan.sh](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP#runmdatpquickscansh) 모드로 다시 시작되면 [Scripts for Microsoft Defender for Endpoint에서](https://github.com/microsoft/shell-intune-samples/tree/master/Misc/MDATP) 사용할 수 있는 runMDATPQuickScan.sh 셸 스크립트가 지속됩니다. 

엔터프라이즈에서 이 스크립트를 사용하는 방법에 대한 자세한 내용은 [Intune에서 macOS](https://docs.microsoft.com/mem/intune/apps/macos-shell-scripts) 장치에서 셸 스크립트 사용을 참조하세요.
