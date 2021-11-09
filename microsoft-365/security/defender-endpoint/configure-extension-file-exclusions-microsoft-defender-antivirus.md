---
title: 확장명, 이름 또는 위치를 기준으로 제외 구성 및 유효성 검사
description: 파일 확장명Microsoft Defender 바이러스 백신 이름 또는 위치에 따라 파일 검색에서 파일을 제외합니다.
keywords: 제외, 파일, 확장명, 파일 형식, 폴더 이름, 파일 이름, 검사
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.date: 11/02/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 7c939b43edf206d31cf62678fa0984aa26707fab
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882408"
---
# <a name="configure-and-validate-exclusions-based-on-file-extension-and-folder-location"></a>파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Microsoft Defender 바이러스 백신

예약된 검사, Microsoft Defender 바이러스 백신 검사 및 무중단 [](schedule-antivirus-scans.md)실시간 보호 및 [](run-scan-microsoft-defender-antivirus.md)모니터링에 적용되는 제외를 정의할 [수 있습니다.](configure-real-time-protection-microsoft-defender-antivirus.md) **일반적으로 제외를** 적용할 필요가 없습니다. 제외를 적용해야 하는 경우 여러 가지 종류에서 선택할 수 있습니다.

- 파일 확장명 및 폴더 위치에 기반한 제외(이 문서에서 설명)
- [프로세스에서 연 파일의 제외](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 끝점 감지 및 응답(EDR), [ASR(공격](/microsoft-365/security/defender-endpoint/attack-surface-reduction)표면 축소) 규칙 및 제어된 폴더 액세스 등 다른 Microsoft Defender for [Endpoint](/microsoft-365/security/defender-endpoint/overview-endpoint-detection-response)기능에는 제외가 적용되지 [않습니다.](/microsoft-365/security/defender-endpoint/controlled-folders) 이 문서에 설명된 방법을 사용하여 제외하는 파일은 경고 및 기타 EDR 트리거할 수 있습니다.
> 파일을 광범위하게 제외하려면 끝점 사용자 지정 표시기용 Microsoft [Defender에 추가합니다.](/microsoft-365/security/defender-endpoint/manage-indicators)

## <a name="before-you-begin"></a>시작하기 전에...

제외 [권장 사항](configure-exclusions-microsoft-defender-antivirus.md) 정의하기 전에 제외를 정의하는 방법을 참조하세요.

## <a name="exclusion-lists"></a>제외 목록

특정 파일을 Microsoft Defender 바이러스 백신 제외 목록을 수정합니다. Microsoft Defender 바이러스 백신 운영 체제 동작 및 일반적인 관리 파일(예: 엔터프라이즈 관리, 데이터베이스 관리 및 기타 엔터프라이즈 시나리오 및 상황에 사용되는 파일)을 기반으로 하는 많은 자동 제외가 포함됩니다.

> [!NOTE]
> 제외는 PUA(잠재적으로 원치 않는 앱) 검색에도 적용됩니다.
>
> 자동 제외는 Windows Server 2016 이상에만 적용됩니다. 이러한 제외는 Windows 보안 PowerShell에서 표시되지 않습니다.

다음 표에는 파일 확장명 및 폴더 위치에 따라 제외의 몇 가지 예가 나열됩니다. 
<br/><br/>

|제외|예제|제외 목록|
|---|---|---|
|특정 확장명을 사용 하는 모든 파일|지정된 확장명을 사용 하는 모든 파일, 컴퓨터의 아무 곳이나. <p> 유효한 구문: `.test` 및 `test`|확장 제외|
|특정 폴더 아래에 있는 모든 파일|폴더 아래에 있는 `c:\test\sample` 모든 파일|파일 및 폴더 제외|
|특정 폴더의 특정 파일|파일만 `c:\sample\sample.test`|파일 및 폴더 제외|
|특정 프로세스|실행 파일 `c:\test\process.exe`|파일 및 폴더 제외|

## <a name="characteristics-of-exclusion-lists"></a>제외 목록의 특성

- 폴더 제외는 하위 폴더가 재분석 지점이 없는 한 해당 폴더 아래에 있는 모든 파일 및 폴더에 적용됩니다. 재분석 지점 하위폴더는 별도로 제외해야 합니다.
- 경로 또는 폴더가 정의되어 있지 않은 경우 파일 확장명은 정의된 확장명을 적용하는 모든 파일 이름에 적용됩니다.

## <a name="important-notes-about-exclusions-based-on-file-extensions-and-folder-locations"></a>파일 확장명 및 폴더 위치에 기반한 제외에 대한 중요 참고 사항

- 와일드카드(예: Asterisk( )를 사용하는 경우 제외 규칙이 해석된 \* 방식이 변경됩니다. 와일드카드 작동 방식에 대한 중요한 정보는 파일 이름 및 폴더 경로 또는 확장명 제외 목록에서 와일드카드 사용 섹션을 참조하세요. [](#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)

- 매핑된 네트워크 드라이브를 제외하지 않습니다. 실제 네트워크 경로를 지정합니다.

- Microsoft Defender 바이러스 백신 서비스가 시작된 후 만들어지며 제외 목록에 추가된 재분석 지점인 폴더는 포함되지 않습니다. 새 재분석 지점이 유효한 제외 대상으로 인식될 Windows 서비스를 다시 시작합니다(다시 시작).

- 제외는 예약된 [검사,](scheduled-catch-up-scans-microsoft-defender-antivirus.md)요구 시 [](run-scan-microsoft-defender-antivirus.md)검사 및 실시간 [](configure-real-time-protection-microsoft-defender-antivirus.md)보호에 적용되지만 끝점용 Defender에는 적용되지 않습니다. 끝점용 Defender에서 제외를 정의하기 위해 사용자 지정 [표시기를 사용 합니다.](manage-indicators.md)

- 기본적으로 PowerShell 및 WMI를 통해 변경한 내용을 포함하여 관리자 권한이 있는 사용자에 의해 목록에 대한 로컬 변경 내용은 그룹 정책, Configuration Manager 또는 Intune에서 정의(및 배포)된 목록과 병합됩니다. 충돌이 있는 경우 그룹 정책 목록이 우선합니다. 또한 그룹 정책으로 변경된 제외 목록은 앱의 Windows 보안 [표시됩니다.](microsoft-defender-security-center-antivirus.md)

- 로컬 변경 내용이 관리되는 배포 설정을 다시 정의하도록 허용하려면 로컬 및 전역으로 정의된 제외 목록이 병합되는 방법을 [구성합니다.](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists)

## <a name="configure-the-list-of-exclusions-based-on-folder-name-or-file-extension"></a>폴더 이름 또는 파일 확장명에 따라 제외 목록 구성

여러 가지 메서드에서 선택을 통해 사용자에 대한 제외를 정의할 수 Microsoft Defender 바이러스 백신.

### <a name="use-intune-to-configure-file-name-folder-or-file-extension-exclusions"></a>Intune을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성

다음 문서를 참조합니다.

- [장치에서 장치 제한 Microsoft Intune](/intune/device-restrictions-configure)
- [Microsoft Defender 바이러스 백신 Intune의 Windows 10 장치 제한 설정](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)

### <a name="use-configuration-manager-to-configure-file-name-folder-or-file-extension-exclusions"></a>Configuration Manager를 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성

맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 제외 설정에서 맬웨어 방지 정책(현재 분기)Microsoft Endpoint Manager 참조하세요.

### <a name="use-group-policy-to-configure-folder-or-file-extension-exclusions"></a>그룹 정책을 사용하여 폴더 또는 파일 확장명 제외 구성

> [!NOTE]
> 파일의 정식 경로를 지정하면 해당 파일만 제외됩니다. 제외에 폴더가 정의되어 있는 경우 해당 폴더의 모든 파일 및 하위 폴더는 제외됩니다.

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 열고 구성하려는 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 **편집** 을 선택합니다.

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하고** 관리 템플릿 **을 선택합니다.**

3. 트리를 확장하여 **Windows 구성 요소 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

4. 편집할 **경로** 제외 설정을 열고 제외를 추가합니다.
    1. 옵션을 사용으로 **설정합니다.**
    2. 옵션 **섹션에서** 표시를 **선택합니다.**
    3. 값 이름 열 아래에 각 폴더를 자체 **줄에 지정합니다.**
    4. 파일을 지정하는 경우 드라이브 문자, 폴더 경로, 파일 이름 및 확장명을 포함하여 파일의 정식 경로를 입력해야 합니다. 값 **열에 0을** **입력합니다.**

5. **확인** 을 선택합니다.

6. 편집할 **확장 제외** 설정을 열고 제외를 추가합니다.
    1. 옵션을 사용으로 **설정합니다.**
    2. 옵션 **섹션에서** 표시를 **선택합니다.**
    3. 값 열의 값 이름 **열Enter** **0** 아래에 각 파일 확장명을 자체 **줄에 입력합니다.**

7. **확인** 을 선택합니다.

<a id="ps"></a>

### <a name="use-powershell-cmdlets-to-configure-file-name-folder-or-file-extension-exclusions"></a>PowerShell cmdlet을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성

PowerShell을 사용하여 확장명, 위치 또는 파일 이름에 따라 파일의 제외를 추가하거나 제거하려면 세 개의 cmdlet과 적절한 제외 목록 매개 변수의 조합을 사용해야 합니다. cmdlet은 [모두 Defender 모듈에 있습니다.](/powershell/module/defender/)

cmdlet의 형식은 다음과 같습니다.

```PowerShell
<cmdlet> -<exclusion list> "<item>"
```

다음 표에는 PowerShell cmdlet 부분에서 사용할 수 있는 `<cmdlet>` cmdlet이 나열됩니다.

<br/>

|구성 작업|PowerShell cmdlet|
|:---|:---|
|목록 만들기 또는 덮어 덮어 사용|`Set-MpPreference`|
|목록에 추가|`Add-MpPreference`|
|목록에서 항목 제거|`Remove-MpPreference`|

다음 표에는 PowerShell cmdlet 부분에서 사용할 수 있는 `<exclusion list>` 값이 나열됩니다.

<br/>

|제외 유형|PowerShell 매개 변수|
|---|---|
|파일 확장명을 지정한 모든 파일|`-ExclusionExtension`|
|폴더의 모든 파일(하위 폴더의 파일 포함) 또는 특정 파일|`-ExclusionPath`|

> [!IMPORTANT]
> 또는 를 사용하여 목록을 만든 경우 cmdlet을 다시 사용하여 기존 목록을 덮어 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 덮어 니다.

예를 들어 다음 코드 Microsoft Defender 바이러스 백신 확장명을 사용하여 모든 파일을 `.test` 제외합니다.

```PowerShell
Add-MpPreference -ExclusionExtension ".test"
```

> [!TIP]
> 자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/)을 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-configure-file-name-folder-or-file-extension-exclusions"></a>WMI(Windows Management Instruction)를 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성

다음 [속성에 대해](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) MSFT_MpPreference 클래스의 Set, Add 및 Remove 메서드를 사용할 수 있습니다.

```WMI
ExclusionExtension
ExclusionPath
```

**Set,** **Add** 및 **Remove를** 사용하는 것은 PowerShell에서 , 및 의 대응하는 경우와 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 유사합니다.

> [!TIP]
> 자세한 내용은 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

<a id="man-tools"></a>

### <a name="use-the-windows-security-app-to-configure-file-name-folder-or-file-extension-exclusions"></a>Windows 보안 앱을 사용하여 파일 이름, 폴더 또는 파일 확장명 제외 구성

지침은 앱의 Windows 보안 [제외 추가를](microsoft-defender-security-center-antivirus.md) 참조하세요.

<a id="wildcards"></a>

## <a name="use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists"></a>파일 이름 및 폴더 경로 또는 확장명 제외 목록에 와일드카드 사용

파일 이름 또는 폴더 경로 제외 목록에서 항목을 정의할 때 추가, 물음표 또는 환경 변수(예: )를 와일드카드로 사용할 `*` `?` 수 `%ALLUSERSPROFILE%` 있습니다. 이러한 와일드카드가 해석되는 방식은 다른 앱 및 언어에서 일반적인 사용법과 다릅니다. 특정 제한 사항을 이해하기 위해 이 섹션을 읽어야 합니다.

> [!IMPORTANT]
> 이러한 와일드카드에 대한 주요 제한 사항 및 사용 시나리오가 있습니다.
>
> - 환경 변수 사용은 컴퓨터 변수 및 NT AUTHORITY\SYSTEM 계정으로 실행되는 프로세스에 적용할 수 있는 변수로 제한됩니다.
> - 드라이브 문자 대신 와일드카드를 사용할 수 없습니다.
> - 폴더 제외의 추가 표시는 단일 `*` 폴더를 위한 것입니다. 여러 인스턴스를 사용하여 지정되지 않은 이름을 사용하여 여러 개의 중첩된 폴더를 `\*\` 나타냅니다.
> - 현재는 Microsoft Endpoint Configuration Manager 와일드카드 문자(예: 또는 )를 지원하지 `*` `?` 않습니다.
    
다음 표에서는 와일드카드를 사용하는 방법을 설명하고 몇 가지 예를 제공합니다.

<br/>

|와일드카드|예제|
|---|---|
|`*` (asterisk) <p> 파일 **이름** 및 파일 확장명 포함에서, 추가 기능은 모든 문자를 대체하며 인수에 정의된 마지막 폴더의 파일에만 적용됩니다. <p> 폴더 **제외에서는** 단일 폴더를 대체하는 추가 표시가 됩니다. 여러 개의 폴더 슬래시를 사용하여 여러 개의 `*` `\` 중첩된 폴더를 나타냅니다. 와일드 카드 및 명명된 폴더 수와 일치하면 모든 하위 폴더도 포함됩니다.|`C:\MyData\*.txt` 포함 `C:\MyData\notes.txt` <p> `C:\somepath\*\Data` 파일 및 해당 하위폴더와 해당 하위폴더를 `C:\somepath\Archives\Data` `C:\somepath\Authorized\Data` 포함합니다. <p> `C:\Serv\*\*\Backup` 파일 및 해당 하위폴더와 해당 `C:\Serv\Primary\Denied\Backup` `C:\Serv\Secondary\Allowed\Backup` 하위폴더를 포함합니다.|
|`?` (물음표)  <p> 파일 **이름** 및 파일 확장명 포함에서 물음표는 단일 문자를 대체하며 인수에 정의된 마지막 폴더의 파일에만 적용됩니다. <p> 폴더 **제외에서** 물음표는 폴더 이름의 단일 문자를 대체합니다. 와일드 카드 및 명명된 폴더 수와 일치하면 모든 하위 폴더도 포함됩니다.|`C:\MyData\my?.zip` 포함 `C:\MyData\my1.zip` <p> `C:\somepath\?\Data` 모든 파일 포함 및 해당 `C:\somepath\P\Data` 하위폴더  <p> `C:\somepath\test0?\Data` 은 모든 파일과 해당 `C:\somepath\test01\Data` 하위폴더를 포함합니다.|
|환경 변수 <p> 제외를 평가할 때 정의된 변수가 경로로 채워지는 경우|`%ALLUSERSPROFILE%\CustomLogFiles` 다음을 포함합니다. `C:\ProgramData\CustomLogFiles\Folder1\file1.txt`|

> [!IMPORTANT]
> 파일 제외 인수와 폴더 제외 인수를 함께 사용하면 규칙은 일치하는 폴더의 파일 인수 일치에서 중지하고 하위 폴더에서 파일 일치를 검색하지 않습니다.
>
> 예를 들어 폴더에서 규칙 인수 를 사용하여 "date"로 시작하는 모든 파일을 `c:\data\final\marked` `c:\data\review\marked` 제외할 수 `c:\data\*\marked\date*` 있습니다.
>
> 그러나 이 인수는 또는 의 하위 폴더에 있는 파일과 일치하지 `c:\data\final\marked` `c:\data\review\marked` 않습니다.

<a id="review"></a>

### <a name="system-environment-variables"></a>시스템 환경 변수

다음 표에서는 시스템 계정 환경 변수를 나열하고 설명합니다.

<br/>

|이 시스템 환경 변수...|리디렉션|
|---|---|
|`%APPDATA%`|`C:\Users\UserName.DomainName\AppData\Roaming`|
|`%APPDATA%\Microsoft\Internet Explorer\Quick Launch`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Internet Explorer\Quick Launch`|
|`%APPDATA%\Microsoft\Windows\Start Menu`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu`|
|`%APPDATA%\Microsoft\Windows\Start Menu\Programs`|`C:\Windows\System32\config\systemprofile\AppData\Roaming\Microsoft\Windows\Start Menu\Programs`|
|`%LOCALAPPDATA%`|`C:\Windows\System32\config\systemprofile\AppData\Local`|
|`%ProgramData%`|`C:\ProgramData`|
|`%ProgramFiles%`|`C:\Program Files`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles%\Windows Sidebar\Gadgets`|`C:\Program Files\Windows Sidebar\Gadgets`|
|`%ProgramFiles%\Common Files`|`C:\Program Files\Common Files`|
|`%ProgramFiles(x86)%`|`C:\Program Files (x86)`|
|`%ProgramFiles(x86)%\Common Files`|`C:\Program Files (x86)\Common Files`|
|`%SystemDrive%`|`C:`|
|`%SystemDrive%\Program Files`|`C:\Program Files`|
|`%SystemDrive%\Program Files (x86)`|`C:\Program Files (x86)`|
|`%SystemDrive%\Users`|`C:\Users`|
|`%SystemDrive%\Users\Public`|`C:\Users\Public`|
|`%SystemRoot%`|`C:\Windows`|
|`%windir%`|`C:\Windows`|
|`%windir%\Fonts`|`C:\Windows\Fonts`|
|`%windir%\Resources`|`C:\Windows\Resources`|
|`%windir%\resources\0409`|`C:\Windows\resources\0409`|
|`%windir%\system32`|`C:\Windows\System32`|
|`%ALLUSERSPROFILE%`|`C:\ProgramData`|
|`%ALLUSERSPROFILE%\Application Data`|`C:\ProgramData\Application Data`|
|`%ALLUSERSPROFILE%\Documents`|`C:\ProgramData\Documents`|
|`%ALLUSERSPROFILE%\Documents\My Music\Sample Music`|`C:\ProgramData\Documents\My Music\Sample Music`|
|`%ALLUSERSPROFILE%\Documents\My Music`|`C:\ProgramData\Documents\My Music`|
|`%ALLUSERSPROFILE%\Documents\My Pictures`|`C:\ProgramData\Documents\My Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Pictures\Sample Pictures`|`C:\ProgramData\Documents\My Pictures\Sample Pictures`|
|`%ALLUSERSPROFILE%\Documents\My Videos`|`C:\ProgramData\Documents\My Videos`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\DeviceMetadataStore`|`C:\ProgramData\Microsoft\Windows\DeviceMetadataStore`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\GameExplorer`|`C:\ProgramData\Microsoft\Windows\GameExplorer`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Ringtones`|`C:\ProgramData\Microsoft\Windows\Ringtones`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu`|`C:\ProgramData\Microsoft\Windows\Start Menu`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Start Menu\Programs\StartUp`|`C:\ProgramData\Microsoft\Windows\Start Menu\Programs\StartUp`|
|`%ALLUSERSPROFILE%\Microsoft\Windows\Templates`|`C:\ProgramData\Microsoft\Windows\Templates`|
|`%ALLUSERSPROFILE%\Start Menu`|`C:\ProgramData\Start Menu`|
|`%ALLUSERSPROFILE%\Start Menu\Programs`| `C:\ProgramData\Start Menu\Programs`|
|`%ALLUSERSPROFILE%\Start Menu\Programs\Administrative Tools`|`C:\ProgramData\Start Menu\Programs\Administrative Tools`|
|`%ALLUSERSPROFILE%\Templates`|`C:\ProgramData\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\ConnectedSearch\Templates`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\ConnectedSearch\Templates`|
|`%LOCALAPPDATA%\Microsoft\Windows\History`|`C:\Windows\System32\config\systemprofile\AppData\Local\Microsoft\Windows\History`|
|`%PUBLIC%`|`C:\Users\Public`|
|`%PUBLIC%\AccountPictures`|`C:\Users\Public\AccountPictures`|
|`%PUBLIC%\Desktop`|`C:\Users\Public\Desktop`|
|`%PUBLIC%\Documents`|`C:\Users\Public\Documents`|
|`%PUBLIC%\Downloads`|`C:\Users\Public\Downloads`|
|`%PUBLIC%\Music\Sample Music`|`C:\Users\Public\Music\Sample Music`|
|`%PUBLIC%\Music\Sample Playlists`|`C:\Users\Public\Music\Sample Playlists`|
|`%PUBLIC%\Pictures\Sample Pictures`|`C:\Users\Public\Pictures\Sample Pictures`|
|`%PUBLIC%\RecordedTV.library-ms`|`C:\Users\Public\RecordedTV.library-ms`|
|`%PUBLIC%\Videos`|`C:\Users\Public\Videos`|
|`%PUBLIC%\Videos\Sample Videos`|`C:\Users\Public\Videos\Sample Videos`|
|`%USERPROFILE%`|`C:\Users\UserName`|
|`%USERPROFILE%\AppData\Local`|`C:\Users\UserName\AppData\Local`|
|`%USERPROFILE%\AppData\LocalLow`|`C:\Users\UserName\AppData\LocalLow`|
|`%USERPROFILE%\AppData\Roaming`|`C:\Users\UserName\AppData\Roaming`|

## <a name="review-the-list-of-exclusions"></a>제외 목록 검토

다음 방법 중 하나를 사용하여 제외 목록의 항목을 검색할 수 있습니다.

- [Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)
- [Microsoft Endpoint Configuration Manager](/configmgr/protect/deploy-use/endpoint-antimalware-policies)
- MpCmdRun
- PowerShell
- [Windows 보안 앱](microsoft-defender-security-center-antivirus.md)

> [!IMPORTANT]
> 그룹 정책으로 변경된 제외  목록은 앱의 목록에 [Windows 보안 표시됩니다.](microsoft-defender-security-center-antivirus.md)
>
> 앱의 Windows 보안 **그룹** 정책 목록에는 변경 내용이 표시되지 않습니다.

PowerShell을 사용하는 경우 다음 두 가지 방법으로 목록을 검색할 수 있습니다.

- 모든 기본 설정의 Microsoft Defender 바이러스 백신 검색합니다. 각 목록은 별도의 줄에 표시되지만 각 목록 내의 항목이 같은 줄로 결합됩니다.
- 모든 기본 설정의 상태를 변수에 기록하고 해당 변수를 사용하여 관심 있는 특정 목록만 호출합니다. 각 `Add-MpPreference` 사용은 새 줄에 기록됩니다.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun을 사용하여 제외 목록 유효성 검사

전용 명령줄 도구에서 제외를 확인하려면 mpcmdrun.exe[명령을 ](./command-line-arguments-microsoft-defender-antivirus.md)사용합니다.

```console
Start, CMD (Run as admin)
cd "%programdata%\microsoft\windows defender\platform"
cd 4.18.2110-5.0 (Where 4.18.2110-5.0 is this month's Microsoft Defender Antivirus "Platform Update".)
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun을 통해 제외를 확인하려면 MICROSOFT DEFENDER 바이러스 백신 CAMP 버전 4.18.2110-5.0(2021년 10월에 출시) 이상이 필요합니다.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell을 사용하여 다른 모든 Microsoft Defender 바이러스 백신 제외 목록 검토

다음 cmdlet을 사용 합니다.

```PowerShell
Get-MpPreference
```

다음 예제에서는 목록에 포함된 항목이 `ExclusionExtension` 강조 표시됩니다.

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="Get-MpPreference에 대한 PowerShell 출력.":::

자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/)을 참조하세요.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell을 사용하여 특정 제외 목록 검색

다음 코드 코드 코드를 사용하여 각 줄을 별도의 명령으로 입력합니다. **WDAVprefs를** 변수의 이름을 지정하려는 레이블로 대체합니다.

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionExtension
$WDAVprefs.ExclusionPath
```

다음 예제에서는 cmdlet을 사용할 때마다 목록을 새 `Add-MpPreference` 줄로 분할합니다.

:::image type="content" source="../../media/wdav-powershell-get-exclusions-variable.png" alt-text="제외 목록의 항목만 표시하는 PowerShell 출력입니다.":::

자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/)을 참조하세요.

<a id="validate"></a>

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a>EICAR 테스트 파일을 사용하여 제외 목록 유효성 검사

cmdlet 또는 .NET WebClient 클래스와 함께 PowerShell을 사용하여 테스트 파일을 다운로드하여 제외 목록이 작동하고 있는지 확인할 `Invoke-WebRequest` 수 있습니다.

다음 PowerShell 코드 코드에서 제외 규칙을 준수하는 파일로 `test.txt` 대체합니다. 예를 들어 확장을 제외한 `.testing` 경우 를 로 `test.txt` 바) `test.testing` 합니다. 경로를 테스트하는 경우 해당 경로 내에서 cmdlet을 실행해야 합니다.

```PowerShell
Invoke-WebRequest "http://www.eicar.org/download/eicar.com.txt" -OutFile "test.txt"
```

맬 Microsoft Defender 바이러스 백신 보고하는 경우 규칙이 작동하지 않습니다. 맬웨어에 대한 보고서가 없는 경우 다운로드한 파일이 있으면 제외가 작동하고 있습니다. 파일을 열어 [EICAR](http://www.eicar.org/86-0-Intended-use.html)테스트 파일 웹 사이트에 설명된 내용과 동일한지 확인할 수 있습니다.

또한 cmdlet과 같이 .NET WebClient 클래스를 호출하여 테스트 파일을 다운로드하는 다음 PowerShell 코드를 사용할 수 있습니다. 유효성을 검사할 규칙을 준수하는 파일로 `Invoke-WebRequest` `c:\test.txt` 바꾸면 됩니다.

```PowerShell
$client = new-object System.Net.WebClient
$client.DownloadFile("http://www.eicar.org/download/eicar.com.txt","c:\test.txt")
```

인터넷에 액세스할 수 없는 경우 다음 PowerShell 명령을 사용하여 새 텍스트 파일에 EICAR 문자열을 작성하여 자체 EICAR 테스트 파일을 만들 수 있습니다.

```PowerShell
[io.file]::WriteAllText("test.txt",'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*')
```

또한 문자열을 빈 텍스트 파일에 복사하여 파일 이름이나 제외하려는 폴더에 저장할 수도 있습니다.

## <a name="see-also"></a>참고 항목

- [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성](configure-server-exclusions-microsoft-defender-antivirus.md)
- [제외 정의 시 피해야 하는 일반적인 실수](common-exclusion-mistakes-microsoft-defender-antivirus.md)
