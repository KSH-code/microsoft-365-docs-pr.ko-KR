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
ms.date: 09/22/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 85c3aee098786d75a7a2f17d1c9c4d11c0c87aeb
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490910"
---
# <a name="common-mistakes-to-avoid-when-defining-exclusions"></a>제외 정의 시 피해야 하는 일반적인 실수

검사하지 않는 항목에 대한 제외 목록을 Microsoft Defender 바이러스 백신 있습니다. 이러한 제외된 항목에는 장치를 취약하게 만드는 위협이 포함될 수 있습니다. 이 문서에서는 제외를 정의할 때 피해야 하는 몇 가지 일반적인 실수에 대해 설명합니다.

제외 목록을 정의하기 전에 권장 사항 [정의하기를 참조하세요.](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions)

## <a name="excluding-certain-trusted-items"></a>신뢰할 수 있는 특정 항목 제외

특정 파일, 파일 형식, 폴더 또는 프로세스는 악성이 아닌 것으로 신뢰하는 경우에도 검사에서 제외하면 안 됩니다.

다음 섹션에 나열된 폴더 위치, 파일 확장명 및 프로세스에 대한 제외를 정의하지 않습니다.
- 폴더 위치
- 파일 확장명
- 프로세스

### <a name="folder-locations"></a>폴더 위치

일반적으로 다음 폴더 위치에 대한 제외를 정의하지 않습니다.

`%systemdrive%`

`C:`

`C:\`

`C:\*`

`%ProgramFiles%\Java`

`C:\Program Files\Java`

`%ProgramFiles%\Contoso\`

`C:\Program Files\Contoso\`

`%ProgramFiles(x86)%\Contoso\`

`C:\Program Files (x86)\Contoso\`

`C:\Temp`

`C:\Temp\`

`C:\Temp\*`

`C:\Users\`

`C:\Users\*`

`C:\Users\<UserProfileName>\AppData\Local\Temp\`**다음 예외에 유의하십시오SharePoint** 파일 수준 바이러스 백신 보호를 사용하는 경우 제외를 `C:\Users\ServiceAccount\AppData\Local\Temp` SharePoint. [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`C:\Users\<UserProfileName>\AppData\LocalLow\Temp\`**다음 예외에 유의하십시오SharePoint** 파일 수준 바이러스 백신 보호를 사용하는 경우 제외를 `C:\Users\Default\AppData\Local\Temp` SharePoint. [](https://support.microsoft.com/office/certain-folders-may-have-to-be-excluded-from-antivirus-scanning-when-you-use-file-level-antivirus-software-in-sharepoint-01cbc532-a24e-4bba-8d67-0b1ed733a3d9)

`%Windir%\Prefetch`

`C:\Windows\Prefetch`

`C:\Windows\Prefetch\`

`C:\Windows\Prefetch\*`

`%Windir%\System32\Spool`

`C:\Windows\System32\Spool`

`C:\Windows\System32\CatRoot2`
`%Windir%\Temp`

`C:\Windows\Temp`

`C:\Windows\Temp\`

`C:\Windows\Temp\*`

#### <a name="linux-and-macos-platforms"></a>Linux 및 macOS 플랫폼

`/`

`/bin`

`/sbin`

`/usr/lib`


### <a name="file-extensions"></a>파일 확장명

일반적으로 다음 파일 확장명에 대한 제외를 정의하지 않습니다.

`.7z`

`.bat`

`.bin`

`.cab`

`.cmd`

`.com`

`.cpl`

`.dll`

`.exe`

`.fla`

`.gif`

`.gz`

`.hta`

`.inf`

`.java`

`.jar`

`.job`

`.jpeg`

`.jpg`

`.js`

`.ko`

`.ko.gz`

`.msi`

`.ocx`

`.png`

`.ps1`

`.py`

`.rar`

`.reg`

`.scr`

`.sys`

`.tar`

`.tmp`

`.url`

`.vbe`

`.vbs`

`.wsf`

`.zip`

### <a name="processes"></a>프로세스

일반적으로 다음 프로세스에 대한 제외를 정의하지 않습니다.

`AcroRd32.exe`

`bitsadmin.exe`

`excel.exe`

`iexplore.exe`

`java.exe`

`outlook.exe`

`psexec.exe`

`powerpnt.exe`

`powershell.exe`

`schtasks.exe`

`svchost.exe`

`wmic.exe`

`winword.exe`

`wuauclt.exe`

`addinprocess.exe`

`addinprocess32.exe`

`addinutil.exe`

`bash.exe`

`bginfo.exe`

`cdb.exe`

`csi.exe`

`dbghost.exe`

`dbgsvc.exe`

`dnx.exe`

`dotnet.exe`

`fsi.exe`

`fsiAnyCpu.exe`

`kd.exe`

`ntkd.exe`

`lxssmanager.dll`

`msbuild.exe`

`mshta.exe`

`ntsd.exe`

`rcsi.exe`

`system.management.automation.dll`

`windbg.exe`

#### <a name="linux-and-macos-platforms"></a>Linux 및 macOS 플랫폼

`bash`

`sh`

`python` 및 `python3`

`java`

`zsh`

> [!NOTE]
> , , 등의 파일 형식을 제외하거나, 환경에 취약성을 처리하기 위한 엄격한 업데이트 정책이 있는 최신 소프트웨어가 있는 `.gif` `.jpg` 경우 `.jpeg` `.png` 제외할 수 있습니다.

## <a name="using-just-the-file-name-in-the-exclusion-list"></a>제외 목록에 파일 이름만 사용

맬웨어는 신뢰하고 검사에서 제외하려는 파일의 이름과 같을 수 있습니다. 따라서 잠재적인 맬웨어가 검색에서 제외되지 않도록 파일 이름만 사용하는 대신 제외하려는 파일의 정식 경로를 사용합니다. 예를 들어 검사에서 제외하려는 경우 파일의 전체 경로(예: )를 `Filename.exe` 사용 `C:\program files\contoso\Filename.exe` 합니다.

## <a name="using-a-single-exclusion-list-for-multiple-server-workloads"></a>여러 서버 워크로드에 단일 제외 목록 사용

단일 제외 목록을 사용하여 여러 서버 워크로드에 대한 제외를 정의하지 않습니다. 서로 다른 응용 프로그램 또는 서비스 워크로드에 대한 제외를 여러 제외 목록으로 분할합니다. 예를 들어 IIS Server 작업의 제외 목록은 해당 작업 부하에 대한 제외 목록과 SQL Server 합니다.

## <a name="using-incorrect-environment-variables-as-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 잘못된 환경 변수를 와일드카드로 사용

Microsoft Defender 바이러스 백신 서비스는 LocalSystem 계정을 사용하여 시스템 컨텍스트에서 실행됩니다. 즉, 사용자 환경 변수가 아니라 시스템 환경 변수에서 정보를 얻게 됩니다. 제외 목록에서 환경 변수를 와일드카드로 사용하는 것은 시스템 변수 및 NT AUTHORITY\SYSTEM 계정으로 실행되는 프로세스에 해당되는 변수로 제한됩니다. 따라서 폴더 및 프로세스 제외를 추가할 때 사용자 환경 변수를 와일드카드로 Microsoft Defender 바이러스 백신 않습니다. 시스템 환경 [변수의](configure-extension-file-exclusions-microsoft-defender-antivirus.md#system-environment-variables) 전체 목록은 시스템 환경 변수 아래 표를 참조하세요.

제외 [목록에서](configure-extension-file-exclusions-microsoft-defender-antivirus.md#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists) 와일드카드를 사용하는 방법에 대한 자세한 내용은 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 사용을 참조하세요.
