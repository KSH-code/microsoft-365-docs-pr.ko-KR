---
title: 실시간 대응 명령 예제
description: 끝점용 Microsoft Defender에 대한 기본 또는 고급 라이브 응답 명령을 실행하고 사용 방법에 대한 예제를 참조합니다.
keywords: 예, 명령, cli, 원격, 셸, 연결, 라이브, 응답, 실시간, 명령, 스크립트, 수정, 헌트, 내보내기, 로그, 놓기, 다운로드, 파일
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b234a27ccf011cdc20b7c1c5ab34e4322bfc5fd
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60587720"
---
# <a name="live-response-command-examples"></a>실시간 대응 명령 예제

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigateip-abovefoldlink)

라이브 응답에 사용되는 일반적인 명령에 대해 알아보고 일반적으로 사용되는 방법에 대한 예를 참조합니다.

부여된 역할에 따라 기본 또는 고급 라이브 응답 명령을 실행할 수 있습니다. 기본 및 고급 명령에 대한 자세한 내용은 라이브 응답을 사용하여 디바이스에서 엔터티 [조사를 참조하세요.](live-response.md)

## <a name="analyze"></a>analyze

```console
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```console
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a>connections

```console
# List active connections in json format using parameter name
connections -output json
```

```console
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a>dir

```console
# List files and sub-folders in the current folder
dir
```

```console
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```console
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a>fileinfo

```console
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a>findfile

```console
# Find file by name
findfile test.txt
```

## <a name="getfile"></a>getfile

```console
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```console
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

> [!NOTE]
>
> 다음 파일 형식은 **Live** Response 내에서 이 명령을 사용하여 다운로드할 수 없습니다.
>
> - [지점 파일 재분석](/windows/desktop/fileio/reparse-points/)
> - [스파스 파일](/windows/desktop/fileio/sparse-files/)
> - 빈 파일
> - 가상 파일 또는 로컬에 완전히 존재하지 않는 파일
>
> 이러한 파일 **형식은** [PowerShell에서 지원됩니다.](/powershell/scripting/overview)
>
> Live Response 내에서 이 명령을 사용하는 데 문제가 있는 경우 PowerShell을 대신 사용할 수 있습니다.

## <a name="library"></a>library

```console
# List files in the library
library
```

```console
# Delete a file from the library
library delete script.ps1
```

## <a name="processes"></a>프로세스

```console
# Show all processes
processes
```

```console
# Get process by pid
processes 123
```

```console
# Get process by pid with argument name
processes -pid 123
```

```console
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a>putfile

```console
# Upload file from library
putfile get-process-by-name.ps1
```

```console
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```console
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a>registry

```console
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```console
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a>재구성

```console
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```console
# Remediate process with specific PID
remediate process 7960
```

```console
# See list of all remediated entities
remediate list
```

## <a name="run"></a>run

```console
# Run PowerShell script from the library without arguments
run script.ps1
```

```console
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

> [!NOTE]
>
> '**run**' 또는 '**getfile**'과 같은 장기 실행 명령의 경우 명령 끝에 ' 기호를 사용하여 백그라운드에서 해당 작업을 수행할 **&** 수 있습니다.
> 이렇게 하면 **'fg'** 기본 명령을 사용하여 컴퓨터 조사를 계속하고 백그라운드 명령으로 [돌아갈 수 있습니다.](live-response.md#basic-commands)

## <a name="scheduledtask"></a>scheduledtask

```console
# Get all scheduled tasks
scheduledtasks
```

```console
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```

## <a name="undo"></a>취소

```console
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```console
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```console
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```
