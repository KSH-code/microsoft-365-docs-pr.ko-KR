---
title: 명령줄을 사용하여 Microsoft Defender 바이러스 백신 관리
description: Microsoft Defender 바이러스 백신 검색을 실행하고 전용 명령줄 유틸리티를 사용하여 차세대 보호를 구성합니다.
keywords: Windows Defender 검사 실행, 명령줄에서 바이러스 백신 검사 실행, 명령줄에서 Windows Defender 검사 실행, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 03/19/2021
ms.technology: mde
ms.openlocfilehash: 2b20227ac27b90d142d263dfa4522aa41319b9d5
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691083"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="47340-104">명령줄 도구를 사용하여 Microsoft Defender 바이러스 mpcmdrun.exe 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="47340-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="47340-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="47340-105">**Applies to:**</span></span>

- <span data-ttu-id="47340-106">[엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) </span><span class="sxs-lookup"><span data-stu-id="47340-106">[Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)</span></span>

<span data-ttu-id="47340-107">전용 명령줄 도구인 를 사용하여 다양한 Microsoft Defender 바이러스 백신 기능을 수행할 **수mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="47340-107">You can perform various Microsoft Defender Antivirus functions with the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="47340-108">이 유틸리티는 Microsoft Defender 바이러스 백신 사용을 자동화하려는 경우 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-108">This utility is useful when you want to automate Microsoft Defender Antivirus use.</span></span> <span data-ttu-id="47340-109">유틸리티는 에서 찾을 수 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="47340-110">명령 프롬프트에서 실행해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-110">You must run it from a command prompt.</span></span>

> [!NOTE]
> <span data-ttu-id="47340-111">명령 프롬프트의 관리자 수준 버전을 열 필요가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="47340-112">시작 메뉴에서 **명령** 프롬프트를 검색할 때 관리자 권한으로 실행 **을 선택합니다.**</span><span class="sxs-lookup"><span data-stu-id="47340-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span>
> <span data-ttu-id="47340-113">업데이트된 Microsoft Defender 플랫폼 버전을 실행 중인 경우 다음 위치에서 `**MpCmdRun**` `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 실행합니다. .</span><span class="sxs-lookup"><span data-stu-id="47340-113">If you're running an updated Microsoft Defender Platform version, run `**MpCmdRun**` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>`.</span></span>

<span data-ttu-id="47340-114">유틸리티에는 다음 명령이 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-114">The utility has the following commands:</span></span>

```console
MpCmdRun.exe [command] [-options]
```
<span data-ttu-id="47340-115">예를 들면 다음과 같습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-115">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| <span data-ttu-id="47340-116">명령</span><span class="sxs-lookup"><span data-stu-id="47340-116">Command</span></span>  | <span data-ttu-id="47340-117">설명</span><span class="sxs-lookup"><span data-stu-id="47340-117">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="47340-118">`-?`**또는**`-h`</span><span class="sxs-lookup"><span data-stu-id="47340-118">`-?` **or** `-h`</span></span>   | <span data-ttu-id="47340-119">이 도구에 사용할 수 있는 모든 옵션 표시</span><span class="sxs-lookup"><span data-stu-id="47340-119">Displays all available options for this tool</span></span> |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="47340-120">악성 소프트웨어를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-120">Scans for malicious software.</span></span> <span data-ttu-id="47340-121">**ScanType의** 값은 **구성에 따라 기본값 0,** **-1** 빠른 검사, **-2** 전체 검사, **-3** 파일 및 디렉터리 사용자 지정 검사입니다.</span><span class="sxs-lookup"><span data-stu-id="47340-121">Values for **ScanType** are: **0** Default, according to your configuration, **-1** Quick scan, **-2** Full scan, **-3** File and directory custom scan.</span></span>  <span data-ttu-id="47340-122">CpuThrottling은 정책에서 구성된 CPU 스로틀을 적용합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-122">CpuThrottling will honor the configured CPU throttling from policy</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="47340-123">진단 추적 시작</span><span class="sxs-lookup"><span data-stu-id="47340-123">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="47340-124">지원 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-124">Collects support information.</span></span> <span data-ttu-id="47340-125">'진단[데이터 수집'](collect-diagnostic-data.md)참조</span><span class="sxs-lookup"><span data-stu-id="47340-125">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="47340-126">과 `-GetFiles` 동일하지만 임시 DiagTrack 폴더로 출력</span><span class="sxs-lookup"><span data-stu-id="47340-126">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="47340-127">설치된 보안 인텔리전스를 이전 백업 복사본 또는 원래 기본 집합으로 복원</span><span class="sxs-lookup"><span data-stu-id="47340-127">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="47340-128">동적으로 다운로드한 보안 인텔리전스만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-128">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="47340-129">이전 설치된 엔진 복원</span><span class="sxs-lookup"><span data-stu-id="47340-129">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="47340-130">새 보안 인텔리전스 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="47340-130">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="47340-131">분리된 항목 복원 또는 목록</span><span class="sxs-lookup"><span data-stu-id="47340-131">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="47340-132">동적 보안 인텔리전스 로드</span><span class="sxs-lookup"><span data-stu-id="47340-132">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="47340-133">로드된 동적 보안 인텔리전스 나열</span><span class="sxs-lookup"><span data-stu-id="47340-133">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="47340-134">동적 보안 인텔리전스 제거</span><span class="sxs-lookup"><span data-stu-id="47340-134">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="47340-135">경로 제외 여부 확인</span><span class="sxs-lookup"><span data-stu-id="47340-135">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="47340-136">네트워크가 Microsoft Defender 바이러스 백신 클라우드 서비스와 통신할 수 있는지 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-136">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="47340-137">이 명령은 Windows 10 버전 1703 이상에서만 작동됩니다.</span><span class="sxs-lookup"><span data-stu-id="47340-137">This command will only work on Windows 10, version 1703 or higher.</span></span>|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="47340-138">명령을 실행하는 데 발생하는 일반적인 오류는 mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="47340-138">Common errors in running commands via mpcmdrun.exe</span></span> 

|<span data-ttu-id="47340-139">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="47340-139">Error message</span></span> | <span data-ttu-id="47340-140">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="47340-140">Possible reason</span></span>
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | <span data-ttu-id="47340-141">Microsoft Defender 바이러스 백신 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-141">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="47340-142">서비스를 사용하도록 설정하고 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-142">Enable the service and try again.</span></span> <br>   <span data-ttu-id="47340-143">**참고:**  Windows 10 1909 이상 및 Windows Server 2019 이상에서는 "Windows Defender 바이러스 백신" 서비스라고 불리는 서비스를 사용했습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-143">**Note:**  In Windows 10 1909 or older, and Windows Server 2019 or older, the service used to be called "Windows Defender Antivirus" service.</span></span>|
| `0x80070667` | <span data-ttu-id="47340-144">`-ValidateMapsConnection`Windows 10 버전 1607 또는 Windows Server 2016 이상인 컴퓨터에서 명령을 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-144">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="47340-145">Windows 10 버전 1703 이상 또는 Windows Server 2019 이상인 컴퓨터로부터 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-145">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | <span data-ttu-id="47340-146">도구는 다음 중 하나에서 실행해야 합니다. (플랫폼 업데이트는 월별을 제외하고 다를 `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` 수 `2012.4-0` 있습니다).</span><span class="sxs-lookup"><span data-stu-id="47340-146">The tool needs to be run from either: `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | <span data-ttu-id="47340-147">권한이 부족합니다.</span><span class="sxs-lookup"><span data-stu-id="47340-147">Not enough privileges.</span></span> <span data-ttu-id="47340-148">명령 프롬프트(cmd.exe)를 관리자 권한으로 사용</span><span class="sxs-lookup"><span data-stu-id="47340-148">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | <span data-ttu-id="47340-149">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-149">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | <span data-ttu-id="47340-150">이름 확인 문제와 같은 네트워크 관련 문제 발생 가능</span><span class="sxs-lookup"><span data-stu-id="47340-150">Possible network-related issues, like name resolution problems</span></span>|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | <span data-ttu-id="47340-151">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-151">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | <span data-ttu-id="47340-152">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-152">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | <span data-ttu-id="47340-153">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="47340-153">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="47340-154">참고 항목</span><span class="sxs-lookup"><span data-stu-id="47340-154">See also</span></span>

- [<span data-ttu-id="47340-155">Microsoft Defender 바이러스 백신 기능 구성</span><span class="sxs-lookup"><span data-stu-id="47340-155">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="47340-156">비즈니스에서 Microsoft Defender 바이러스 백신 관리</span><span class="sxs-lookup"><span data-stu-id="47340-156">Manage Microsoft Defender Antivirus in your business</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47340-157">관리 및 구성 도구에 대한 참조 항목</span><span class="sxs-lookup"><span data-stu-id="47340-157">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
- [<span data-ttu-id="47340-158">Windows 10의 Microsoft Defender 바이러스 백신</span><span class="sxs-lookup"><span data-stu-id="47340-158">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)