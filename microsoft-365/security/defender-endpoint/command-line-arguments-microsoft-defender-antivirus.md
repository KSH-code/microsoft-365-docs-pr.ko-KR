---
title: 명령줄을 사용하여 명령줄을 Microsoft Defender 바이러스 백신
description: 검사 Microsoft Defender 바이러스 백신 실행하고 전용 명령줄 유틸리티를 사용하여 차세대 보호를 구성합니다.
keywords: Windows Defender 검사 실행, 명령줄에서 바이러스 백신 검사 실행, 명령줄에서 Windows Defender 검사 실행, mpcmdrun, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.date: 05/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: efeb49b2741bdc45f7924032c2deb8a27458ca29
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289418"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a><span data-ttu-id="f51ac-104">명령줄 Microsoft Defender 바이러스 백신 사용하여 mpcmdrun.exe 구성 및 관리</span><span class="sxs-lookup"><span data-stu-id="f51ac-104">Configure and manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>

<span data-ttu-id="f51ac-105">**적용 대상:**</span><span class="sxs-lookup"><span data-stu-id="f51ac-105">**Applies to:**</span></span>

- [<span data-ttu-id="f51ac-106">엔드포인트용 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f51ac-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="f51ac-107">의 전용 명령줄 도구를 사용하여 Microsoft Defender 바이러스 백신 다양한 기능을 수행할 **수mpcmdrun.exe.**</span><span class="sxs-lookup"><span data-stu-id="f51ac-107">You can perform various functions in Microsoft Defender Antivirus using the dedicated command-line tool **mpcmdrun.exe**.</span></span> <span data-ttu-id="f51ac-108">이 유틸리티는 모든 작업을 자동화하려는 Microsoft Defender 바이러스 백신 유용합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-108">This utility is useful when you want to automate Microsoft Defender Antivirus tasks.</span></span> <span data-ttu-id="f51ac-109">유틸리티는 에서 찾을 수 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-109">You can find the utility in `%ProgramFiles%\Windows Defender\MpCmdRun.exe`.</span></span> <span data-ttu-id="f51ac-110">명령 프롬프트에서 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-110">Run it from a command prompt.</span></span>

> [!TIP]
> <span data-ttu-id="f51ac-111">명령 프롬프트의 관리자 수준 버전을 열 필요가 있을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-111">You might need to open an administrator-level version of the command prompt.</span></span> <span data-ttu-id="f51ac-112">명령 **프롬프트에서** 명령 프롬프트를 시작 메뉴 관리자 권한으로 **실행을 선택 합니다.**</span><span class="sxs-lookup"><span data-stu-id="f51ac-112">When you search for **Command Prompt** on the Start menu, choose **Run as administrator**.</span></span> <span data-ttu-id="f51ac-113">업데이트된 Microsoft Defender 플랫폼 버전을 실행 중인 경우 다음 위치에서 `MpCmdRun` `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 실행합니다. .</span><span class="sxs-lookup"><span data-stu-id="f51ac-113">If you're running an updated Microsoft Defender Platform version, run `MpCmdRun` from the following location: `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>`.</span></span> <span data-ttu-id="f51ac-114">맬웨어 방지 플랫폼에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 [및 기준을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="f51ac-114">For more information about the antimalware platform, see [Microsoft Defender Antivirus updates and baselines](manage-updates-baselines-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="f51ac-115">MpCmdRun 유틸리티는 다음 구문을 사용 합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-115">The MpCmdRun utility uses the following syntax:</span></span>

```console
MpCmdRun.exe [command] [-options]
```

<span data-ttu-id="f51ac-116">다음은 예입니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-116">Here's an example:</span></span>

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

<span data-ttu-id="f51ac-117">이 예제에서는 MpCmdRun 유틸리티가 장치에서 전체 바이러스 백신 검색을 시작합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-117">In our example, the MpCmdRun utility starts a full antivirus scan on the device.</span></span>

## <a name="commands"></a><span data-ttu-id="f51ac-118">명령</span><span class="sxs-lookup"><span data-stu-id="f51ac-118">Commands</span></span>

| <span data-ttu-id="f51ac-119">명령</span><span class="sxs-lookup"><span data-stu-id="f51ac-119">Command</span></span>  | <span data-ttu-id="f51ac-120">설명</span><span class="sxs-lookup"><span data-stu-id="f51ac-120">Description</span></span>   |
|:----|:----|
| <span data-ttu-id="f51ac-121">`-?` **또는** `-h`</span><span class="sxs-lookup"><span data-stu-id="f51ac-121">`-?` **or** `-h`</span></span>   | <span data-ttu-id="f51ac-122">MpCmdRun 도구에 대해 사용 가능한 모든 옵션을 표시</span><span class="sxs-lookup"><span data-stu-id="f51ac-122">Displays all available options for the MpCmdRun tool</span></span> |
| `-Scan [-ScanType [<value>]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | <span data-ttu-id="f51ac-123">악성 소프트웨어를 검사합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-123">Scans for malicious software.</span></span> <span data-ttu-id="f51ac-124">**ScanType의 값은:**</span><span class="sxs-lookup"><span data-stu-id="f51ac-124">Values for **ScanType** are:</span></span><p><span data-ttu-id="f51ac-125">**0** 구성에 따라 기본값</span><span class="sxs-lookup"><span data-stu-id="f51ac-125">**0** Default, according to your configuration</span></span><p><span data-ttu-id="f51ac-126">**1** 빠른 검사</span><span class="sxs-lookup"><span data-stu-id="f51ac-126">**1** Quick scan</span></span><p><span data-ttu-id="f51ac-127">**2** 전체 검사</span><span class="sxs-lookup"><span data-stu-id="f51ac-127">**2** Full scan</span></span><p><span data-ttu-id="f51ac-128">**3** 파일 및 디렉터리 사용자 지정 검사.</span><span class="sxs-lookup"><span data-stu-id="f51ac-128">**3** File and directory custom scan.</span></span><p><span data-ttu-id="f51ac-129">CpuThrottling은 정책 구성에 따라 실행됩니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-129">CpuThrottling runs according to policy configurations</span></span> |
| `-Trace [-Grouping #] [-Level #]` | <span data-ttu-id="f51ac-130">진단 추적 시작</span><span class="sxs-lookup"><span data-stu-id="f51ac-130">Starts diagnostic tracing</span></span> |
| `-GetFiles [-SupportLogLocation <path>]` | <span data-ttu-id="f51ac-131">지원 정보를 수집합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-131">Collects support information.</span></span> <span data-ttu-id="f51ac-132">'진단[데이터 수집'](collect-diagnostic-data.md)참조</span><span class="sxs-lookup"><span data-stu-id="f51ac-132">See '[collecting diagnostic data](collect-diagnostic-data.md)'</span></span>  |
| `-GetFilesDiagTrack`  | <span data-ttu-id="f51ac-133">과 `-GetFiles` 동일하지만 임시 DiagTrack 폴더로 출력</span><span class="sxs-lookup"><span data-stu-id="f51ac-133">Same as `-GetFiles`, but outputs to temporary DiagTrack folder</span></span> |
| `-RemoveDefinitions [-All]` | <span data-ttu-id="f51ac-134">설치된 보안 인텔리전스를 이전 백업 복사본 또는 원래 기본 집합으로 복원</span><span class="sxs-lookup"><span data-stu-id="f51ac-134">Restores the installed Security intelligence to a previous backup copy or to the original default set</span></span> |
| `-RemoveDefinitions [-DynamicSignatures]` | <span data-ttu-id="f51ac-135">동적으로 다운로드한 보안 인텔리전스만 제거합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-135">Removes only the dynamically downloaded Security intelligence</span></span> |
| `-RemoveDefinitions [-Engine]` | <span data-ttu-id="f51ac-136">이전 설치된 엔진 복원</span><span class="sxs-lookup"><span data-stu-id="f51ac-136">Restores the previous installed engine</span></span> |
| `-SignatureUpdate [-UNC \| -MMPC]` | <span data-ttu-id="f51ac-137">새 보안 인텔리전스 업데이트 확인</span><span class="sxs-lookup"><span data-stu-id="f51ac-137">Checks for new Security intelligence updates</span></span> |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | <span data-ttu-id="f51ac-138">분리된 항목 복원 또는 목록</span><span class="sxs-lookup"><span data-stu-id="f51ac-138">Restores or lists quarantined item(s)</span></span> |
| `-AddDynamicSignature [-Path]` | <span data-ttu-id="f51ac-139">동적 보안 인텔리전스 로드</span><span class="sxs-lookup"><span data-stu-id="f51ac-139">Loads dynamic Security intelligence</span></span> |
| `-ListAllDynamicSignatures` | <span data-ttu-id="f51ac-140">로드된 동적 보안 인텔리전스 나열</span><span class="sxs-lookup"><span data-stu-id="f51ac-140">Lists the loaded dynamic Security intelligence</span></span> |
| `-RemoveDynamicSignature [-SignatureSetID]` | <span data-ttu-id="f51ac-141">동적 보안 인텔리전스 제거</span><span class="sxs-lookup"><span data-stu-id="f51ac-141">Removes dynamic Security intelligence</span></span> |
| `-CheckExclusion -path <path>` | <span data-ttu-id="f51ac-142">경로 제외 여부 확인</span><span class="sxs-lookup"><span data-stu-id="f51ac-142">Checks whether a path is excluded</span></span> |
| `-ValidateMapsConnection` | <span data-ttu-id="f51ac-143">네트워크가 클라우드 서비스 및 통신할 Microsoft Defender 바이러스 백신 확인합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-143">Verifies that your network can communicate with the Microsoft Defender Antivirus cloud service.</span></span> <span data-ttu-id="f51ac-144">이 명령은 버전 Windows 10 버전 1703 이상에서만 사용할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-144">This command will only work on Windows 10, version 1703 or higher.</span></span>|

## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a><span data-ttu-id="f51ac-145">명령을 실행하는 데 발생하는 일반적인 오류는 mpcmdrun.exe</span><span class="sxs-lookup"><span data-stu-id="f51ac-145">Common errors in running commands via mpcmdrun.exe</span></span> 

<span data-ttu-id="f51ac-146">다음 표에는 MpCmdRun 도구를 사용하는 동안 발생할 수 있는 일반적인 오류가 나열됩니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-146">The following table lists common errors that can occur while using the MpCmdRun tool.</span></span>

|<span data-ttu-id="f51ac-147">오류 메시지</span><span class="sxs-lookup"><span data-stu-id="f51ac-147">Error message</span></span> | <span data-ttu-id="f51ac-148">가능한 이유</span><span class="sxs-lookup"><span data-stu-id="f51ac-148">Possible reason</span></span> |
|:----|:----|
| <span data-ttu-id="f51ac-149">**ValidateMapsConnection이 실패(800106BA)** 또는 **0x800106BA**</span><span class="sxs-lookup"><span data-stu-id="f51ac-149">**ValidateMapsConnection failed (800106BA)** or **0x800106BA**</span></span> | <span data-ttu-id="f51ac-150">Microsoft Defender 바이러스 백신 서비스를 사용할 수 없습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-150">The Microsoft Defender Antivirus service is disabled.</span></span> <span data-ttu-id="f51ac-151">서비스를 사용하도록 설정하고 다시 시도합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-151">Enable the service and try again.</span></span> <span data-ttu-id="f51ac-152">다시 사용하도록 설정하는 데 도움이 필요한 Microsoft Defender 바이러스 백신 끝점에서 다시 [설치/Microsoft Defender 바이러스 백신 설정을 참조합니다.](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints)</span><span class="sxs-lookup"><span data-stu-id="f51ac-152">If you need help re-enabling Microsoft Defender Antivirus, see [Reinstall/enable Microsoft Defender Antivirus on your endpoints](switch-to-microsoft-defender-setup.md#reinstallenable-microsoft-defender-antivirus-on-your-endpoints).</span></span><p> <span data-ttu-id="f51ac-153">**팁:** Windows 10 1909 이상 및 Windows Server 2019 이상에서는 이 서비스를 이전의 *Windows Defender 바이러스 백신.*</span><span class="sxs-lookup"><span data-stu-id="f51ac-153">**TIP**: In Windows 10 1909 or older, and Windows Server 2019 or older, the service was formerly called *Windows Defender Antivirus*.</span></span> |
| <span data-ttu-id="f51ac-154">**0x80070667**</span><span class="sxs-lookup"><span data-stu-id="f51ac-154">**0x80070667**</span></span> | <span data-ttu-id="f51ac-155">버전 1607 또는 Windows 10 또는 Windows Server 2016 `-ValidateMapsConnection` 컴퓨터에서 명령을 실행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-155">You're running the `-ValidateMapsConnection` command from a computer that is Windows 10 version 1607 or older, or Windows Server 2016 or older.</span></span> <span data-ttu-id="f51ac-156">1703 이상 Windows 10 또는 Server 2019 이상 버전인 Windows 명령을 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-156">Run the command from a machine that is Windows 10 version 1703 or newer, or Windows Server 2019 or newer.</span></span>|
| <span data-ttu-id="f51ac-157">**MpCmdRun은 내부 또는 외부 명령, 작동 프로그램 또는 배치 파일로 인식되지 않습니다.**</span><span class="sxs-lookup"><span data-stu-id="f51ac-157">**MpCmdRun is not recognized as an internal or external command, operable program, or batch file.**</span></span> | <span data-ttu-id="f51ac-158">도구를 실행해야 합니다(플랫폼 업데이트는 월별을 제외하고 다를 수 `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` `2012.4-0` 있습니다).</span><span class="sxs-lookup"><span data-stu-id="f51ac-158">The tool must be run from either `%ProgramFiles%\Windows Defender` or `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` (where `2012.4-0` might differ since platform updates are monthly except for March)</span></span>|
| <span data-ttu-id="f51ac-159">**ValidateMapsConnection에서 MAPS에 연결하지 못했습니다(hr=80070005 httpcode=450).**</span><span class="sxs-lookup"><span data-stu-id="f51ac-159">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)**</span></span> | <span data-ttu-id="f51ac-160">명령이 부족한 권한을 사용하려고 했습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-160">The command was attempted using insufficient privileges.</span></span> <span data-ttu-id="f51ac-161">명령 프롬프트(cmd.exe)를 관리자 권한으로 사용</span><span class="sxs-lookup"><span data-stu-id="f51ac-161">Use the command prompt (cmd.exe) as an administrator.</span></span>|
| <span data-ttu-id="f51ac-162">**ValidateMapsConnection이 MAPS에 연결하지 못했습니다(hr=80070006 httpcode=451).**</span><span class="sxs-lookup"><span data-stu-id="f51ac-162">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)**</span></span> | <span data-ttu-id="f51ac-163">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-163">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="f51ac-164">**ValidateMapsConnection이 MAPS에 연결하지 못했습니다(hr=80004005 httpcode=450).**</span><span class="sxs-lookup"><span data-stu-id="f51ac-164">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)**</span></span> | <span data-ttu-id="f51ac-165">이름 확인 문제와 같은 네트워크 관련 문제 발생 가능</span><span class="sxs-lookup"><span data-stu-id="f51ac-165">Possible network-related issues, like name resolution problems</span></span>|
| <span data-ttu-id="f51ac-166">**ValidateMapsConnection이 MAPS에 연결하지 못했습니다(hr=0x80508015**</span><span class="sxs-lookup"><span data-stu-id="f51ac-166">**ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015**</span></span> | <span data-ttu-id="f51ac-167">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-167">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="f51ac-168">**ValidateMapsConnection이 MAPS에 연결하지 못했습니다(hr=800722F0D**</span><span class="sxs-lookup"><span data-stu-id="f51ac-168">**ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D**</span></span> | <span data-ttu-id="f51ac-169">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-169">The firewall is blocking the connection or conducting SSL inspection.</span></span> |
| <span data-ttu-id="f51ac-170">**ValidateMapsConnection에서 MAPS에 연결하지 못했습니다(hr=80072EE7 httpcode=451).**</span><span class="sxs-lookup"><span data-stu-id="f51ac-170">**ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)**</span></span> | <span data-ttu-id="f51ac-171">방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다.</span><span class="sxs-lookup"><span data-stu-id="f51ac-171">The firewall is blocking the connection or conducting SSL inspection.</span></span> |

## <a name="see-also"></a><span data-ttu-id="f51ac-172">참고 항목</span><span class="sxs-lookup"><span data-stu-id="f51ac-172">See also</span></span>

- [<span data-ttu-id="f51ac-173">Microsoft Defender 바이러스 백신 기능 구성</span><span class="sxs-lookup"><span data-stu-id="f51ac-173">Configure Microsoft Defender Antivirus features</span></span>](configure-microsoft-defender-antivirus-features.md)
- [<span data-ttu-id="f51ac-174">Microsoft Defender 바이러스 백신 네트워크 연결 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="f51ac-174">Configure and validate Microsoft Defender Antivirus network connections</span></span>](configure-network-connections-microsoft-defender-antivirus.md)
- [<span data-ttu-id="f51ac-175">관리 및 구성 도구에 대한 참조 항목</span><span class="sxs-lookup"><span data-stu-id="f51ac-175">Reference topics for management and configuration tools</span></span>](configuration-management-reference-microsoft-defender-antivirus.md)
