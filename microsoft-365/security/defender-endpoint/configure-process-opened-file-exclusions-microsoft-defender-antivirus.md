---
title: 특정 프로세스에서 연 파일에 대한 제외 구성
description: 특정 프로세스에서 파일을 연 경우 검사에서 파일을 제외할 수 있습니다.
keywords: Microsoft Defender 바이러스 백신, 프로세스, 제외, 파일, 검사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: ea06094121f9c6a654234da1cb6d7757db5c78dd
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59212292"
---
# <a name="configure-exclusions-for-files-opened-by-processes"></a>프로세스에서 연 파일에 대한 제외 구성


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

특정 프로세스에서 연 파일은 검사에서 제외할 Microsoft Defender 바이러스 백신 있습니다. 제외 [권장 사항](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 정의하기 전에 제외를 정의하는 방법을 참조하세요.

이 문서에서는 제외 목록을 구성하는 방법에 대해 설명합니다.

## <a name="examples-of-exclusions"></a>제외의 예

<br>

****

|제외|예제|
|---|---|
|특정 파일 이름을 사용 하 고 모든 프로세스에서 열 수 있는 컴퓨터의 모든 파일|다음을 `test.exe` 통해 연 파일은 제외됩니다. <p>`c:\sample\test.exe` <p> `d:\internal\files\test.exe`|
|특정 폴더의 모든 프로세스에서 연 컴퓨터의 모든 파일|다음을 `c:\test\sample\*` 통해 연 파일은 제외됩니다. <p> `c:\test\sample\test.exe` <p> `c:\test\sample\test2.exe` <p> `c:\test\sample\utility.exe`|
|특정 폴더의 특정 프로세스에서 연 컴퓨터의 모든 파일|지정하면 `c:\test\process.exe` 열 때만 열 수 있는 파일 제외 `c:\test\process.exe`|
|

프로세스 제외 목록에 프로세스를 추가하면 Microsoft Defender 바이러스 백신 위치와 상관없이 해당 프로세스에서 연 파일을 검색하지 않습니다. 그러나 프로세스 자체는 파일 제외 목록에도 추가되지 않은 경우 [검사됩니다.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

제외는 항상 실시간 보호 및 모니터링에만 [적용됩니다.](configure-real-time-protection-microsoft-defender-antivirus.md) 예약된 검사나 요구 시 검사에는 적용되지 않습니다.

제외 목록에 대한 그룹 정책으로 **변경한** 내용은 Windows 보안 [앱의 목록에 표시됩니다.](microsoft-defender-security-center-antivirus.md) 그러나 그룹 정책 Windows 보안 **변경** 내용은 그룹 정책 목록에 표시되지 않습니다.

그룹 정책, Microsoft Endpoint Configuration Manager, Microsoft Intune 및 Windows 보안 앱에서 제외 목록을 추가, 제거 및 검토할 수 있으며, 와일드카드를 사용하여 목록을 추가로 사용자 지정할 수 있습니다.

PowerShell cmdlet 및 WMI를 사용하여 목록 검토를 포함하여 제외 목록을 구성할 수도 있습니다.

기본적으로 목록에 대한 로컬 변경 내용(관리자 권한이 있는 사용자, PowerShell 및 WMI로 변경한 내용은 그룹 정책, Configuration Manager 또는 Intune에서 정의하고 배포한 목록)과 병합됩니다. 충돌이 있는 경우 그룹 정책 목록이 우선합니다.

로컬 [및](configure-local-policy-overrides-microsoft-defender-antivirus.md#merge-lists) 전역으로 정의된 제외 목록이 병합되는 방법을 구성하여 로컬 변경 내용이 관리되는 배포 설정을 다시 정의할 수 있도록 할 수 있습니다.

## <a name="configure-the-list-of-exclusions-for-files-opened-by-specified-processes"></a>지정된 프로세스에서 연 파일의 제외 목록 구성

### <a name="use-microsoft-intune-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>이 Microsoft Intune 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

자세한 내용은 [Microsoft Intune에서 디바이스 제한 설정 구성](/intune/device-restrictions-configure) 및 [Intune에서 Windows 10의 Microsoft Defender 바이러스 백신 디바이스 제한 설정](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)을 참조하세요.

### <a name="use-microsoft-endpoint-manager-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>이 Microsoft Endpoint Manager 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) 제외 설정에서 맬웨어 방지 정책(현재 분기)Microsoft Endpoint Manager 참조하세요.

### <a name="use-group-policy-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>그룹 정책을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

1. 그룹 정책 관리 컴퓨터에서 그룹 [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))정책 관리 콘솔을 열고 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 템플릿 **을 클릭합니다.**

3. 트리를 확장하여 Windows **구성 Microsoft Defender 바이러스 백신 \> \> 확장합니다.**

4. 프로세스 **제외를** 두 번 클릭하고 제외를 추가합니다.
    1. 옵션을 사용으로 **설정합니다.**
    2. 옵션 **섹션에서** **표시...를 클릭합니다.**
    3. 값 이름 열 아래에 각 프로세스를 자체 **줄에 입력합니다.** 다양한 유형의 프로세스 제외에 대한 예제 표를 참조합니다. 모든 프로세스의 값 **열에** **0을** 입력합니다.

5. **확인** 을 클릭합니다.

### <a name="use-powershell-cmdlets-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>PowerShell cmdlet을 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

PowerShell을 사용하여 프로세스에서 연 파일에 대한 제외를 추가하거나 제거하려면 매개 변수와 함께 세 개의 cmdlet을 조합하여 사용해야 `-ExclusionProcess` 합니다. cmdlet은 [모두 Defender 모듈에 있습니다.](/powershell/module/defender/)

cmdlet의 형식은 다음입니다.

```PowerShell
<cmdlet> -ExclusionProcess "<item>"
```

다음을 다음으로 \<cmdlet\> 허용합니다.

<br>

****

|구성 작업|PowerShell cmdlet|
|---|---|
|목록 만들기 또는 덮어 덮어 사용|`Set-MpPreference`|
|목록에 추가|`Add-MpPreference`|
|목록에서 항목 제거|`Remove-MpPreference`|
|

> [!IMPORTANT]
> 또는 를 사용하여 목록을 만든 경우 cmdlet을 다시 사용하여 기존 목록을 덮어 `Set-MpPreference` `Add-MpPreference` `Set-MpPreference` 덮어 니다.

예를 들어 다음 코드는 Microsoft Defender AV 검사에서 지정된 프로세스에서 연 파일을 제외합니다.

```PowerShell
Add-MpPreference -ExclusionProcess "c:\internal\test.exe"
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 Microsoft Defender 바이러스 백신 PowerShell cmdlet 및 [cmdlet을](/powershell/module/defender)사용하여 바이러스 Microsoft Defender 바이러스 백신 관리를 참조하세요.

### <a name="use-windows-management-instruction-wmi-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>WMI(Windows 관리 명령)를 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

다음 속성에 대해 MSFT_MpPreference 클래스의 [  **Set,** **Add** 및 **Remove**](/previous-versions/windows/desktop/legacy/dn455323(v=vs.85)) 메서드를 사용할 수 있습니다.

```WMI
ExclusionProcess
```

**Set,** **Add** 및 **Remove는** PowerShell에서 , 및 의 사용과 `Set-MpPreference` `Add-MpPreference` `Remove-MpPreference` 유사합니다.

자세한 정보 및 허용되는 매개 변수는 [WMIv2 api Windows Defender 참조하세요.](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

### <a name="use-the-windows-security-app-to-exclude-files-that-have-been-opened-by-specified-processes-from-scans"></a>앱 Windows 보안 사용하여 지정된 프로세스에서 연 파일을 검사에서 제외

지침은 앱의 Windows 보안 [제외 추가를](microsoft-defender-security-center-antivirus.md) 참조하세요.

## <a name="use-wildcards-in-the-process-exclusion-list"></a>프로세스 제외 목록에서 와일드카드 사용

프로세스 제외 목록에서 와일드카드를 사용하는 것은 다른 제외 목록에서 사용하는 경우와 다릅니다.

특히 물음표() 와일드카드를 사용할 수 없습니다. 그리고 전체 경로의 끝에만 물음표( ) 와일드카드를 사용할 `?` `*` 수 있습니다. 프로세스 제외 목록에서 항목을 정의할 때 환경 변수(예: )를 와일드카드로 사용할 `%ALLUSERSPROFILE%` 수 있습니다.

다음 표에서는 프로세스 제외 목록에서 와일드카드를 사용하는 방법에 대해 설명하고 있습니다.

<br>

****

|와일드카드|예제 사용|일치 예제|
|---|---|---|
|`*` (asterisk) <p> 문자 수에 따라 바꾸기|`C:\MyData\*`|모든 파일에서 연 파일 `C:\MyData\file.exe`|
|환경 변수 <p> 제외를 평가할 때 정의된 변수가 경로로 채워지기|`%ALLUSERSPROFILE%\CustomLogFiles\file.exe`|모든 파일에서 연 파일 `C:\ProgramData\CustomLogFiles\file.exe`|
|

## <a name="review-the-list-of-exclusions"></a>제외 목록 검토

MpCmdRun, PowerShell, Microsoft Endpoint Configuration Manager [,](/configmgr/protect/deploy-use/endpoint-antimalware-policies#exclusion-settings) [Intune](/intune/device-restrictions-configure)또는 Windows 보안 앱으로 제외 목록의 항목을 [검색할 수 있습니다.](microsoft-defender-security-center-antivirus.md)

PowerShell을 사용하는 경우 다음 두 가지 방법으로 목록을 검색할 수 있습니다.

- 모든 기본 설정의 Microsoft Defender 바이러스 백신 검색합니다. 각 목록은 별도의 줄에 표시되지만 각 목록 내의 항목이 같은 줄로 결합됩니다.
- 모든 기본 설정의 상태를 변수에 기록하고 해당 변수를 사용하여 관심 있는 특정 목록만 호출합니다. 각 `Add-MpPreference` 사용은 새 줄에 기록됩니다.

### <a name="validate-the-exclusion-list-by-using-mpcmdrun"></a>MpCmdRun을 사용하여 제외 목록 유효성 검사

전용 명령줄 도구에서 제외를 확인하려면 mpcmdrun.exe[명령을 ](./command-line-arguments-microsoft-defender-antivirus.md?branch=v-anbic-wdav-new-mpcmdrun-options)사용합니다.

```DOS
MpCmdRun.exe -CheckExclusion -path <path>
```

> [!NOTE]
> MpCmdRun을 통해 제외를 확인하려면 MICROSOFT DEFENDER 바이러스 백신 CAMP 버전 4.18.1812.3(2018년 12월에 출시) 이상이 필요합니다.

### <a name="review-the-list-of-exclusions-alongside-all-other-microsoft-defender-antivirus-preferences-by-using-powershell"></a>PowerShell을 사용하여 다른 모든 Microsoft Defender 바이러스 백신 제외 목록 검토

다음 cmdlet을 사용 합니다.

```PowerShell
Get-MpPreference
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender) 구성하고 실행을 Microsoft Defender 바이러스 백신.

### <a name="retrieve-a-specific-exclusions-list-by-using-powershell"></a>PowerShell을 사용하여 특정 제외 목록 검색

다음 코드 코드 코드를 사용하여 각 줄을 별도의 명령으로 입력합니다. **WDAVprefs를** 변수의 이름을 지정하려는 레이블로 대체합니다.

```PowerShell
$WDAVprefs = Get-MpPreference
$WDAVprefs.ExclusionProcess
```

PowerShell과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet을](/powershell/module/defender) 구성하고 실행을 Microsoft Defender 바이러스 백신.

## <a name="related-articles"></a>관련 문서

- [검사에서 제외 구성 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md)
- [파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성](configure-server-exclusions-microsoft-defender-antivirus.md)
- [제외 정의 시 피해야 하는 일반적인 실수](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
