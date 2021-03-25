---
title: 라이브 응답 명령 예제
description: 끝점용 Microsoft Defender에 대한 기본 또는 고급 라이브 응답 명령을 실행하고 사용 방법에 대한 예제를 참조합니다.
keywords: 예, 명령, cli, 원격, 셸, 연결, 라이브, 응답, 실시간, 명령, 스크립트, 수정, 헌트, 내보내기, 로그, 놓기, 다운로드, 파일
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 0e00464b5d5dcf348fcc76a3f093ac8bac373627
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187712"
---
# <a name="live-response-command-examples"></a><span data-ttu-id="6bdfa-104">라이브 응답 명령 예제</span><span class="sxs-lookup"><span data-stu-id="6bdfa-104">Live response command examples</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="6bdfa-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="6bdfa-105">**Applies to:**</span></span>
- [<span data-ttu-id="6bdfa-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="6bdfa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="6bdfa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6bdfa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="6bdfa-108">Endpoint용 Defender를 경험하고 싶나요?</span><span class="sxs-lookup"><span data-stu-id="6bdfa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="6bdfa-109">무료 평가판에 등록합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdfa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="6bdfa-110">라이브 응답에 사용되는 일반적인 명령에 대해 알아보고 일반적으로 사용되는 방법에 대한 예를 참조합니다.</span><span class="sxs-lookup"><span data-stu-id="6bdfa-110">Learn about common commands used in live response and see examples on how they are typically used.</span></span>

<span data-ttu-id="6bdfa-111">부여된 역할에 따라 기본 또는 고급 라이브 응답 명령을 실행할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdfa-111">Depending on the role that's been granted to you, you can run basic or advanced live response commands.</span></span> <span data-ttu-id="6bdfa-112">기본 및 고급 명령에 대한 자세한 내용은 라이브 응답을 사용하여 디바이스에서 엔터티 [조사를 참조하세요.](live-response.md)</span><span class="sxs-lookup"><span data-stu-id="6bdfa-112">For more information on basic and advanced commands, see [Investigate entities on devices using live response](live-response.md).</span></span>


## <a name="analyze"></a><span data-ttu-id="6bdfa-113">analyze</span><span class="sxs-lookup"><span data-stu-id="6bdfa-113">analyze</span></span> 

```
# Analyze the file malware.txt
analyze file c:\Users\user\Desktop\malware.txt
```

```
# Analyze the process by PID
analyze process 1234
```

## <a name="connections"></a><span data-ttu-id="6bdfa-114">connections</span><span class="sxs-lookup"><span data-stu-id="6bdfa-114">connections</span></span>

```
# List active connections in json format using parameter name
connections -output json
```

```
# List active connections in json format without parameter name
connections json
```

## <a name="dir"></a><span data-ttu-id="6bdfa-115">dir</span><span class="sxs-lookup"><span data-stu-id="6bdfa-115">dir</span></span>

```
# List files and sub-folders in the current folder
dir
```

```
# List files and sub-folders in a specific folder
dir C:\Users\user\Desktop\
```

```
# List files and subfolders in the current folder in json format
dir -output json
```

## <a name="fileinfo"></a><span data-ttu-id="6bdfa-116">fileinfo</span><span class="sxs-lookup"><span data-stu-id="6bdfa-116">fileinfo</span></span>

```
# Display information about a file
fileinfo C:\Windows\notepad.exe
```

## <a name="findfile"></a><span data-ttu-id="6bdfa-117">findfile</span><span class="sxs-lookup"><span data-stu-id="6bdfa-117">findfile</span></span>

```
# Find file by name
findfile test.txt
```

## <a name="getfile"></a><span data-ttu-id="6bdfa-118">getfile</span><span class="sxs-lookup"><span data-stu-id="6bdfa-118">getfile</span></span>

```
# Download a file from a machine
getfile c:\Users\user\Desktop\work.txt
```

```
# Download a file from a machine, automatically run prerequisite commands
getfile c:\Users\user\Desktop\work.txt -auto
```

>[!NOTE]
>
> <span data-ttu-id="6bdfa-119">다음 파일 형식은 **Live** Response 내에서 이 명령을 사용하여 다운로드할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdfa-119">The following file types **cannot** be downloaded using this command from within Live Response:</span></span>
>
> * [<span data-ttu-id="6bdfa-120">지점 파일 재분석</span><span class="sxs-lookup"><span data-stu-id="6bdfa-120">Reparse point files</span></span>](/windows/desktop/fileio/reparse-points/)
> * [<span data-ttu-id="6bdfa-121">스파스 파일</span><span class="sxs-lookup"><span data-stu-id="6bdfa-121">Sparse files</span></span>](/windows/desktop/fileio/sparse-files/)
> * <span data-ttu-id="6bdfa-122">빈 파일</span><span class="sxs-lookup"><span data-stu-id="6bdfa-122">Empty files</span></span>
> * <span data-ttu-id="6bdfa-123">가상 파일 또는 로컬에 완전히 존재하지 않는 파일</span><span class="sxs-lookup"><span data-stu-id="6bdfa-123">Virtual files, or files that are not fully present locally</span></span>
>
> <span data-ttu-id="6bdfa-124">이러한 파일 **형식은** [PowerShell에서 지원됩니다.](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true)</span><span class="sxs-lookup"><span data-stu-id="6bdfa-124">These file types **are** supported by [PowerShell](/powershell/scripting/overview?view=powershell-6/?&preserve-view=true).</span></span>
>
> <span data-ttu-id="6bdfa-125">Live Response 내에서 이 명령을 사용하는 데 문제가 있는 경우 PowerShell을 대신 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="6bdfa-125">Use PowerShell as an alternative, if you have problems using this command from within Live Response.</span></span>

## <a name="processes"></a><span data-ttu-id="6bdfa-126">프로세스</span><span class="sxs-lookup"><span data-stu-id="6bdfa-126">processes</span></span>
```
# Show all processes
processes
```

```
# Get process by pid
processes 123
```

```
# Get process by pid with argument name
processes -pid 123
```

```
# Get process by name
processes -name notepad.exe
```

## <a name="putfile"></a><span data-ttu-id="6bdfa-127">putfile</span><span class="sxs-lookup"><span data-stu-id="6bdfa-127">putfile</span></span>

```
# Upload file from library
putfile get-process-by-name.ps1
```

```
# Upload file from library, overwrite file if it exists
putfile get-process-by-name.ps1 -overwrite
```

```
# Upload file from library, keep it on the machine after a restart
putfile get-process-by-name.ps1 -keep
```

## <a name="registry"></a><span data-ttu-id="6bdfa-128">registry</span><span class="sxs-lookup"><span data-stu-id="6bdfa-128">registry</span></span>

```
# Show information about the values in a registry key
registry HKEY_CURRENT_USER\Console
```

```
# Show information about a specific registry value
registry HKEY_CURRENT_USER\Console\\ScreenBufferSize
```


## <a name="remediate"></a><span data-ttu-id="6bdfa-129">재구성</span><span class="sxs-lookup"><span data-stu-id="6bdfa-129">remediate</span></span>

```
# Remediate file in specific path
remediate file c:\Users\user\Desktop\malware.exe
```

```
# Remediate process with specific PID
remediate process 7960
```

```
# See list of all remediated entities
remediate list
```

## <a name="run"></a><span data-ttu-id="6bdfa-130">run</span><span class="sxs-lookup"><span data-stu-id="6bdfa-130">run</span></span>

```
# Run PowerShell script from the library without arguments
run script.ps1
```

```
# Run PowerShell script from the library with arguments
run get-process-by-name.ps1 -parameters "-processName Registry"
```

## <a name="scheduledtask"></a><span data-ttu-id="6bdfa-131">scheduledtask</span><span class="sxs-lookup"><span data-stu-id="6bdfa-131">scheduledtask</span></span>

```
# Get all scheduled tasks
scheduledtasks
```

```
# Get specific scheduled task by location and name
scheduledtasks Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Get specific scheduled task by location and name with spacing
scheduledtasks "Microsoft\Configuration Manager\Configuration Manager Health Evaluation"
```


## <a name="undo"></a><span data-ttu-id="6bdfa-132">취소</span><span class="sxs-lookup"><span data-stu-id="6bdfa-132">undo</span></span>

```
# Restore remediated registry
undo registry HKEY_CURRENT_USER\Console\ScreenBufferSize
```

```
# Restore remediated scheduledtask
undo scheduledtask Microsoft\Windows\Subscription\LicenseAcquisition
```

```
# Restore remediated file
undo file c:\Users\user\Desktop\malware.exe
```

