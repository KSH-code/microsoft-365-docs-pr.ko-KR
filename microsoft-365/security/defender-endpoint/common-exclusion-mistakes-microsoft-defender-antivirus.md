---
title: 제외를 정의할 때 피해야 하는 일반적인 실수
description: Microsoft Defender 바이러스 백신 검사에 대한 제외를 정의할 때 일반적인 실수를 방지합니다.
keywords: 제외, 파일, 확장명, 파일 형식, 폴더 이름, 파일 이름, 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: eb3ac89eb05b39ff3337aa8e9c5ead1c308fbefb
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764918"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>제외를 정의할 때 피해야 하는 일반적인 실수

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

Microsoft Defender 바이러스 백신을 검사하지 않는 항목에 대한 제외 목록을 정의할 수 있습니다. 이러한 제외된 항목에는 장치를 취약하게 만드는 위협이 포함될 수 있습니다. 

이 문서에서는 제외를 정의할 때 피해야 하는 몇 가지 일반적인 실수에 대해 설명합니다. 

제외 목록을 정의하기 전에 제외 정의에 대한 권장 사항을 [참조하세요.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>신뢰할 수 있는 특정 항목 제외

특정 파일, 파일 형식, 폴더 또는 프로세스는 악성이 아닌 것으로 신뢰하는 경우에도 검사에서 제외하면 안 됩니다. 

다음 표에 나열된 폴더 위치, 파일 확장명 및 프로세스에 대한 제외를 정의하지 않습니다.

| 폴더 위치 | 파일 확장명 | 프로세스 |
|:--|:--|:--|
| `%systemdrive%` <br/> `C:`<br/> `C:\` <br/> `C:\*` <br/> `%ProgramFiles%\Java` <br/> `C:\Program Files\Java` <br/> `%ProgramFiles%\Contoso\` <br/> `C:\Program Files\Contoso\` <br/> `%ProgramFiles(x86)%\Contoso\` <br/> `C:\Program Files (x86)\Contoso\` <br/> `C:\Temp` <br/> `C:\Temp\` <br/> `C:\Temp\*` <br/> `C:\Users\` <br/> `C:\Users\*` <br/> `C:\Users\<UserProfileName>\AppData\Local\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\LocalLow\Temp\` <br/> `C:\Users\<UserProfileName>\AppData\Roaming\Temp\` <br/> `%Windir%\Prefetch` <br/> `C:\Windows\Prefetch` <br/> `C:\Windows\Prefetch\` <br/> `C:\Windows\Prefetch\*` <br/> `%Windir%\System32\Spool` <br/> `C:\Windows\System32\Spool` <br/> `C:\Windows\System32\CatRoot2` <br/> `%Windir%\Temp` <br/> `C:\Windows\Temp` <br/> `C:\Windows\Temp\` <br/> `C:\Windows\Temp\*` | `.7z` <br/> `.bat` <br/> `.bin` <br/> `.cab` <br/> `.cmd` <br/> `.com` <br/> `.cpl` <br/> `.dll` <br/> `.exe` <br/> `.fla` <br/> `.gif` <br/> `.gz` <br/> `.hta` <br/> `.inf` <br/> `.java` <br/> `.jar` <br/> `.job` <br/> `.jpeg` <br/> `.jpg` <br/> `.js` <br/> `.ko` <br/> `.ko.gz` <br/> `.msi` <br/> `.ocx` <br/> `.png` <br/> `.ps1` <br/> `.py` <br/> `.rar` <br/> `.reg` <br/> `.scr` <br/> `.sys` <br/> `.tar` <br/> `.tmp` <br/> `.url` <br/> `.vbe` <br/> `.vbs` <br/> `.wsf` <br/> `.zip` | `AcroRd32.exe` <br/> `bitsadmin.exe` <br/> `excel.exe` <br/> `iexplore.exe` <br/> `java.exe` <br/> `outlook.exe` <br/> `psexec.exe` <br/> `powerpnt.exe` <br/> `powershell.exe` <br/> `schtasks.exe`  <br/> `svchost.exe` <br/>`wmic.exe` <br/> `winword.exe` <br/> `wuauclt.exe` <br/> `addinprocess.exe` <br/> `addinprocess32.exe` <br/> `addinutil.exe` <br/> `bash.exe` <br/> `bginfo.exe`[1] <br/>`cdb.exe` <br/> `csi.exe` <br/> `dbghost.exe` <br/> `dbgsvc.exe` <br/> `dnx.exe` <br/> `fsi.exe` <br/> `fsiAnyCpu.exe` <br/> `kd.exe` <br/> `ntkd.exe` <br/> `lxssmanager.dll` <br/> `msbuild.exe`[2] <br/> `mshta.exe` <br/> `ntsd.exe` <br/> `rcsi.exe` <br/> `system.management.automation.dll` <br/> `windbg.exe` |

> [!NOTE]
> , , 등의 파일 형식을 제외하거나, 환경에 취약성을 처리하기 위한 엄격한 업데이트 정책이 있는 최신 소프트웨어가 있는 `.gif` `.jpg` 경우 `.jpeg` `.png` 제외할 수 있습니다.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>제외 목록에 파일 이름만 사용

맬웨어는 신뢰하고 검사에서 제외하려는 파일의 이름과 같을 수 있습니다. 따라서 잠재적인 맬웨어가 검색에서 제외되지 않도록 파일 이름만 사용하는 대신 제외하려는 파일의 정식 경로를 사용합니다. 예를 들어 검사에서 제외하려는 경우 파일의 전체 경로(예: )를 `Filename.exe` 사용 `C:\program files\contoso\Filename.exe` 합니다.

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>여러 서버 워크로드에 단일 제외 목록 사용

단일 제외 목록을 사용하여 여러 서버 워크로드에 대한 제외를 정의하지 않습니다. 서로 다른 응용 프로그램 또는 서비스 워크로드에 대한 제외를 여러 제외 목록으로 분할합니다. 예를 들어 IIS Server 작업의 제외 목록은 해당 작업 부하에 대한 제외 SQL Server 달라야 합니다.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 잘못된 환경 변수를 와일드카드로 사용

Microsoft Defender 바이러스 백신 서비스는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다. 즉, 사용자 환경 변수가 아니라 시스템 환경 변수에서 정보를 얻습니다. 제외 목록에서 환경 변수를 와일드카드로 사용하는 것은 시스템 변수 및 NT AUTHORITY\SYSTEM 계정으로 실행되는 프로세스에 해당되는 변수로 제한됩니다. 따라서 Microsoft Defender 바이러스 백신 폴더 및 프로세스 제외를 추가할 때 사용자 환경 변수를 와일드카드로 사용하지 않습니다. 시스템 환경 [변수의](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 전체 목록은 시스템 환경 변수 아래 표를 참조하세요.

제외 [목록에서](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 와일드카드를 사용하는 방법에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 사용을 참조하세요.

## <a name="related-articles"></a>관련 문서

- [Microsoft Defender 바이러스 백신 검사에서 제외 구성 및 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md)
- [파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Windows Server에서 Microsoft Defender 바이러스 백신 제외 구성](configure-server-exclusions-microsoft-defender-antivirus.md)
