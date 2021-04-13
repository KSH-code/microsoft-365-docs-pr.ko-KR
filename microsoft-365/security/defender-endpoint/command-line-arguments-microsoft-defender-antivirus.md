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
# <a name="configure-and-manage-microsoft-defender-antivirus-with-the-mpcmdrunexe-command-line-tool"></a>명령줄 도구를 사용하여 Microsoft Defender 바이러스 mpcmdrun.exe 구성 및 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/) 

전용 명령줄 도구인 를 사용하여 다양한 Microsoft Defender 바이러스 백신 기능을 수행할 **수mpcmdrun.exe.** 이 유틸리티는 Microsoft Defender 바이러스 백신 사용을 자동화하려는 경우 유용합니다. 유틸리티는 에서 찾을 수 `%ProgramFiles%\Windows Defender\MpCmdRun.exe` 있습니다. 명령 프롬프트에서 실행해야 합니다.

> [!NOTE]
> 명령 프롬프트의 관리자 수준 버전을 열 필요가 있을 수 있습니다. 시작 메뉴에서 **명령** 프롬프트를 검색할 때 관리자 권한으로 실행 **을 선택합니다.**
> 업데이트된 Microsoft Defender 플랫폼 버전을 실행 중인 경우 다음 위치에서 `**MpCmdRun**` `C:\ProgramData\Microsoft\Windows Defender\Platform\<version>` 실행합니다. .

유틸리티에는 다음 명령이 있습니다.

```console
MpCmdRun.exe [command] [-options]
```
예를 들면 다음과 같습니다.

```console
MpCmdRun.exe -Scan -ScanType 2
``` 

| 명령  | 설명   |
|:----|:----|
| `-?`**또는**`-h`   | 이 도구에 사용할 수 있는 모든 옵션 표시 |
| `-Scan [-ScanType [0\|1\|2\|3]] [-File <path> [-DisableRemediation] [-BootSectorScan] [-CpuThrottling]] [-Timeout <days>] [-Cancel]` | 악성 소프트웨어를 검사합니다. **ScanType의** 값은 **구성에 따라 기본값 0,** **-1** 빠른 검사, **-2** 전체 검사, **-3** 파일 및 디렉터리 사용자 지정 검사입니다.  CpuThrottling은 정책에서 구성된 CPU 스로틀을 적용합니다. |
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
| `-ValidateMapsConnection` | 네트워크가 Microsoft Defender 바이러스 백신 클라우드 서비스와 통신할 수 있는지 확인합니다. 이 명령은 Windows 10 버전 1703 이상에서만 작동됩니다.|


## <a name="common-errors-in-running-commands-via-mpcmdrunexe"></a>명령을 실행하는 데 발생하는 일반적인 오류는 mpcmdrun.exe 

|오류 메시지 | 가능한 이유
|:----|:----|
| `ValidateMapsConnection failed (800106BA) or 0x800106BA` | Microsoft Defender 바이러스 백신 서비스를 사용할 수 없습니다. 서비스를 사용하도록 설정하고 다시 시도합니다. <br>   **참고:**  Windows 10 1909 이상 및 Windows Server 2019 이상에서는 "Windows Defender 바이러스 백신" 서비스라고 불리는 서비스를 사용했습니다.|
| `0x80070667` | `-ValidateMapsConnection`Windows 10 버전 1607 또는 Windows Server 2016 이상인 컴퓨터에서 명령을 실행하고 있습니다. Windows 10 버전 1703 이상 또는 Windows Server 2019 이상인 컴퓨터로부터 명령을 실행합니다.|
| `'MpCmdRun' is not recognized as an internal or external command, operable program or batch file.` | 도구는 다음 중 하나에서 실행해야 합니다. (플랫폼 업데이트는 월별을 제외하고 다를 `%ProgramFiles%\Windows Defender` `C:\ProgramData\Microsoft\Windows Defender\Platform\4.18.2012.4-0` 수 `2012.4-0` 있습니다).|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070005 httpcode=450)` | 권한이 부족합니다. 명령 프롬프트(cmd.exe)를 관리자 권한으로 사용|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80070006 httpcode=451)` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80004005 httpcode=450)` | 이름 확인 문제와 같은 네트워크 관련 문제 발생 가능|
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=0x80508015` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=800722F0D` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |
| `ValidateMapsConnection failed to establish a connection to MAPS (hr=80072EE7 httpcode=451)` | 방화벽이 연결을 차단하거나 SSL 검사를 수행하고 있습니다. |

## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 기능 구성](configure-microsoft-defender-antivirus-features.md)
- [비즈니스에서 Microsoft Defender 바이러스 백신 관리](configuration-management-reference-microsoft-defender-antivirus.md)
- [관리 및 구성 도구에 대한 참조 항목](configuration-management-reference-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)