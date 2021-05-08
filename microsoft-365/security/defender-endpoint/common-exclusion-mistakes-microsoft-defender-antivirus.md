---
title: 제외 정의 시 피해야 하는 일반적인 실수
description: 검사에 대한 제외를 정의할 때 일반적인 Microsoft Defender 바이러스 백신 방지합니다.
keywords: 제외, 파일, 확장명, 파일 형식, 폴더 이름, 파일 이름, 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: de739ca3c6a4ab305b575fa7e2f419d044d997a8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274974"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a><span data-ttu-id="bc45a-104">제외 정의 시 피해야 하는 일반적인 실수</span><span class="sxs-lookup"><span data-stu-id="bc45a-104">Common mistakes to avoid when defining exclusions</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="bc45a-105">검사하지 않는 항목에 대한 제외 목록을 Microsoft Defender 바이러스 백신 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-105">You can define an exclusion list for items that you don't want Microsoft Defender Antivirus to scan.</span></span> <span data-ttu-id="bc45a-106">이러한 제외된 항목에는 장치를 취약하게 만드는 위협이 포함될 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-106">Such excluded items could contain threats that make your device vulnerable.</span></span> 

<span data-ttu-id="bc45a-107">이 문서에서는 제외를 정의할 때 피해야 하는 몇 가지 일반적인 실수에 대해 설명합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-107">This article describes some common mistake that you should avoid when defining exclusions.</span></span> 

<span data-ttu-id="bc45a-108">제외 목록을 정의하기 전에 권장 사항 [정의하기를 참조하세요.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)</span><span class="sxs-lookup"><span data-stu-id="bc45a-108">Before defining your exclusion lists, see [Recommendations for defining exclusions](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions).</span></span>

## <a name="excluding-certain-trusted-items"></a><span data-ttu-id="bc45a-109">신뢰할 수 있는 특정 항목 제외</span><span class="sxs-lookup"><span data-stu-id="bc45a-109">Excluding certain trusted items</span></span>

<span data-ttu-id="bc45a-110">특정 파일, 파일 형식, 폴더 또는 프로세스는 악성이 아닌 것으로 신뢰하는 경우에도 검사에서 제외하면 안 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-110">Certain files, file types, folders, or processes should not be excluded from scanning even though you trust them to be not malicious.</span></span> 

<span data-ttu-id="bc45a-111">다음 표에 나열된 폴더 위치, 파일 확장명 및 프로세스에 대한 제외를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-111">Do not define exclusions for the folder locations, file extensions, and processes that are listed in the following table:</span></span>

| <span data-ttu-id="bc45a-112">폴더 위치</span><span class="sxs-lookup"><span data-stu-id="bc45a-112">Folder locations</span></span> | <span data-ttu-id="bc45a-113">파일 확장명</span><span class="sxs-lookup"><span data-stu-id="bc45a-113">File extensions</span></span> | <span data-ttu-id="bc45a-114">프로세스</span><span class="sxs-lookup"><span data-stu-id="bc45a-114">Processes</span></span> |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> <span data-ttu-id="bc45a-115">`bginfo.exe`[1]</span><span class="sxs-lookup"><span data-stu-id="bc45a-115">`bginfo.exe`[1]</span></span> <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> <span data-ttu-id="bc45a-116">`msbuild.exe`[2]</span><span class="sxs-lookup"><span data-stu-id="bc45a-116">`msbuild.exe`[2]</span></span> <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> <span data-ttu-id="bc45a-117">, , 등의 파일 형식을 제외하거나, 환경에 취약성을 처리하기 위한 엄격한 업데이트 정책이 있는 최신 소프트웨어가 있는 `.gif` `.jpg` 경우 `.jpeg` `.png` 제외할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-117">You can choose to exclude file types, such as `.gif`, `.jpg`, `.jpeg`, or `.png` if your environment has a modern, up-to-date software with a strict update policy to handle any vulnerabilities.</span></span>

## <a name="using-just-the-file-name-in-the-exclusion-list"></a><span data-ttu-id="bc45a-118">제외 목록에 파일 이름만 사용</span><span class="sxs-lookup"><span data-stu-id="bc45a-118">Using just the file name in the exclusion list</span></span>

<span data-ttu-id="bc45a-119">맬웨어는 신뢰하고 검사에서 제외하려는 파일의 이름과 같을 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-119">A malware may have the same name as that of the file that you trust and want to exclude from scanning.</span></span> <span data-ttu-id="bc45a-120">따라서 잠재적인 맬웨어가 검색에서 제외되지 않도록 파일 이름만 사용하는 대신 제외하려는 파일의 정식 경로를 사용합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-120">Therefore, to avoid excluding a potential malware from scanning, use a fully qualified path to the file that you want to exclude instead of using just the file name.</span></span> <span data-ttu-id="bc45a-121">예를 들어 검사에서 제외하려는 경우 파일의 전체 경로(예: )를 `Filename.exe` 사용 `C:\program files\contoso\Filename.exe` 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-121">For example, if you want to exclude `Filename.exe` from scanning, use the complete path to the file, such as `C:\program files\contoso\Filename.exe`.</span></span>

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a><span data-ttu-id="bc45a-122">여러 서버 워크로드에 단일 제외 목록 사용</span><span class="sxs-lookup"><span data-stu-id="bc45a-122">Using a single exclusion list for multiple server workloads</span></span>

<span data-ttu-id="bc45a-123">단일 제외 목록을 사용하여 여러 서버 워크로드에 대한 제외를 정의하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-123">Do not use a single exclusion list to define exclusions for multiple server workloads.</span></span> <span data-ttu-id="bc45a-124">서로 다른 응용 프로그램 또는 서비스 워크로드에 대한 제외를 여러 제외 목록으로 분할합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-124">Split the exclusions for different application or service workloads into multiple exclusion lists.</span></span> <span data-ttu-id="bc45a-125">예를 들어 IIS Server 작업의 제외 목록은 해당 작업 부하에 대한 제외 목록과 SQL Server 합니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-125">For example, the exclusion list for your IIS Server workload must be different from the exclusion list for your SQL Server workload.</span></span>

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a><span data-ttu-id="bc45a-126">파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 잘못된 환경 변수를 와일드카드로 사용</span><span class="sxs-lookup"><span data-stu-id="bc45a-126">Using incorrect environment variables as wildcards in the file name and folder path or extension exclusion lists</span></span>

<span data-ttu-id="bc45a-127">Microsoft Defender 바이러스 백신 서비스는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다. 즉, 사용자 환경 변수가 아니라 시스템 환경 변수에서 정보를 얻게 됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-127">Microsoft Defender Antivirus Service runs in system context using the LocalSystem account, which means it gets information from the system environment variable, and not from the user environment variable.</span></span> <span data-ttu-id="bc45a-128">제외 목록에서 환경 변수를 와일드카드로 사용하는 것은 시스템 변수 및 NT AUTHORITY\SYSTEM 계정으로 실행되는 프로세스에 해당되는 변수로 제한됩니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-128">Use of environment variables as a wildcard in exclusion lists is limited to system variables and those applicable to processes running as an NT AUTHORITY\SYSTEM account.</span></span> <span data-ttu-id="bc45a-129">따라서 폴더 및 프로세스 제외를 추가할 때 사용자 환경 변수를 와일드카드로 Microsoft Defender 바이러스 백신 않습니다.</span><span class="sxs-lookup"><span data-stu-id="bc45a-129">Therefore, do not use user environment variables as wildcards when adding Microsoft Defender Antivirus folder and process exclusions.</span></span> <span data-ttu-id="bc45a-130">시스템 환경 [변수의](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 전체 목록은 시스템 환경 변수 아래 표를 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc45a-130">See the table under [System environment variables](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) for a complete list of system environment variables.</span></span>

<span data-ttu-id="bc45a-131">제외 [목록에서](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 와일드카드를 사용하는 방법에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 사용을 참조하세요.</span><span class="sxs-lookup"><span data-stu-id="bc45a-131">See [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) for information on how to use wildcards in exclusion lists.</span></span>

## <a name="related-articles"></a><span data-ttu-id="bc45a-132">관련 문서</span><span class="sxs-lookup"><span data-stu-id="bc45a-132">Related articles</span></span>

- [<span data-ttu-id="bc45a-133">검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bc45a-133">Configure and validate exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bc45a-134">파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bc45a-134">Configure and validate exclusions based on file extension and folder location</span></span>](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bc45a-135">프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사</span><span class="sxs-lookup"><span data-stu-id="bc45a-135">Configure and validate exclusions for files opened by processes</span></span>](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="bc45a-136">Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성</span><span class="sxs-lookup"><span data-stu-id="bc45a-136">Configure Microsoft Defender Antivirus exclusions on Windows Server</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
