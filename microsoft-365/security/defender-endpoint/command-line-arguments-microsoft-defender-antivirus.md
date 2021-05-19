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
ms.date: 05/17/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: eb7fa7fdf5b88bd9361176003817116bcbb1a087
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538906"
---
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>명령줄 Microsoft Defender 바이러스 백신 사용하여 mpcmdrun.exe 구성 및 관리

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

의 전용 명령줄 Microsoft Defender 바이러스 백신 사용하여 다양한 여러 기능을 수행할 **수mpcmdrun.exe.** 이 유틸리티는 자동 관리 기능을 사용하려는 Microsoft Defender 바이러스 백신 유용합니다. 유틸리티는 에서 찾을 수 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 있습니다. 명령 프롬프트에서 실행해야 합니다.

> [!NOTE]
> 명령 프롬프트의 관리자 수준 버전을 열 필요가 있을 수 있습니다. 시작 메뉴에서 **명령** 프롬프트를 검색할 때 관리자 권한으로 실행 **을 선택합니다.**
> 업데이트된 Microsoft Defender 플랫폼 버전을 실행 중인 경우 다음 위치에서 `**MpCmdRun**` `C:\ProgramData\Microsoft\Windows Defender\Platform\<antimalware platform version>` 실행합니다. .
> 맬웨어 방지 플랫폼에 대한 자세한 내용은 Microsoft Defender 바이러스 백신 [및 기준을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md)

MpCmdRun 유틸리티는 다음 구문을 사용 합니다.

```console
MpCmdRun.exe [command] [-options]
```

다음은 예입니다.

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| 명령  | 설명   |
|:----|:----|
| `-?` **또는** `-h`   | 이 도구에 사용할 수 있는 모든 옵션 표시 |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 악성 소프트웨어를 검사합니다. **ScanType의 값은:**<p>**0** 구성에 따라 기본값<p>**-1** 빠른 검사<p>**-2** 전체 검사<p>**-3** 파일 및 디렉터리 사용자 지정 검사.<p>CpuThrottling은 정책에서 구성된 CPU 스로틀을 적용합니다. |
| `-Trace [-Grouping #] [-Level #]` | 진단 추적 시작 |
| `-GetFiles [-SupportLogLocation <path>]` | 지원 정보를 수집합니다. '진단[데이터 수집'](collect-diagnostic-data.md)참조  |
| `-GetFilesDiagTrack`  | 과 `-GetFiles` 동일하지만 임시 DiagTrack 폴더로 출력 |
| `-RemoveDefinitions [-All]` | 설치된 보안 인텔리전스를 이전 백업 복사본 또는 원래 기본 집합으로 복원 |
| `-RemoveDefinitions [-DynamicSignatures]` | 동적으로 다운로드한 보안 인텔리전스만 제거합니다. |
| `-RemoveDefinitions [-Engine]` | 이전 설치된 엔진 복원 |
| `-SignatureUpdate [-UNC \| -MMPC]` | 새 보안 인텔리전스 업데이트 확인 |
| `-Restore  [-ListAll \| [[-Name <name>] [-All] \| [-FilePath <filePath>]] [-Path <path>]]` | 분리된 항목 복원 또는 목록 |
| `-AddDynamicSignature [-Path]` | 동적 보안 인텔리전스 로드 |
| `-ListAllDynamicSignatures` | 로드된 동적 보안 인텔리전스 나열 |
| `-RemoveDynamicSignature [-SignatureSetID]` | 동적 보안 인텔리전스 제거 |
| `-CheckExclusion -path <path>` | 경로 제외 여부 확인 |
| `-ValidateMapsConnection` | 네트워크가 클라우드 서비스 및 통신할 Microsoft Defender 바이러스 백신 확인합니다. 이 명령은 버전 Windows 10 버전 1703 이상에서만 사용할 수 있습니다.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>명령을 실행하는 데 발생하는 일반적인 오류는 mpcmdrun.exe 

|오류 메시지 | 가능한 이유
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Microsoft Defender 바이러스 백신 서비스를 사용할 수 없습니다. 서비스를 사용하도록 설정하고 다시 시도합니다. <br>   **참고:**  Windows 10 1909 이상 및 Windows Server 2019 이상에서는 서비스를 Windows Defender 바이러스 백신 *서비스라고* 합니다.|
| `0x80070667` | 버전 1607 또는 Windows 10 또는 Windows Server 2016 `-ValidateMapsConnection` 컴퓨터에서 명령을 실행하고 있습니다. 1703 이상 Windows 10 또는 Server 2019 이상 버전인 Windows 명령을 실행합니다.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | 도구는 다음 중 하나에서 실행해야 합니다. (플랫폼 업데이트는 월별을 제외하고 다를 `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` 수 `2012.4-0` 있습니다).|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 권한이 부족합니다. 명령 프롬프트(cmd.exe)를 관리자 권한으로 사용|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 이름 확인 문제와 같은 네트워크 관련 문제 발생 가능|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |

## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 기능 구성](configure-microsoft-defender-antivirus-features.md)
- [비즈니스 Microsoft Defender 바이러스 백신 관리](configuration-management-reference-microsoft-defender-antivirus.md)
- [관리 및 구성 도구에 대한 참조 항목](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)