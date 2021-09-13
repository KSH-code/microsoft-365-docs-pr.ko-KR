---
title: Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성
ms.reviewer: pahuijbr
manager: dansimp
description: Windows 서버에는 서버 역할에 따라 자동 제외가 포함됩니다. 사용자 지정 제외를 추가할 수도 있습니다.
keywords: 제외, 서버, 자동 제외, 자동, 사용자 지정, 검사, Microsoft Defender 바이러스 백신
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
ms.date: 08/17/2021
ms.openlocfilehash: d50146c3689f7b19fc6b546478bc0b01ada1fc30
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213782"
---
# <a name="configure-microsoft-defender-antivirus-exclusions-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 Windows 제외 구성


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- Windows Defender 바이러스 백신

## <a name="summary"></a>요약

이 문서에서는 Microsoft Defender 바이러스 백신 이상에서 제외하는 Windows Server 2016 제공합니다.

이 Microsoft Defender 바이러스 백신 기본 제공 Windows Server 2016 운영 체제 파일 및 서버 역할 제외가 자동으로 수행됩니다. 그러나 사용자 지정 제외를 정의할 수 있습니다. 필요한 경우 자동 제외를 옵트아웃(opt out)할 수 있습니다.

이 문서에는 다음과 같은 섹션이 포함되어 있습니다.

<br>

****

|섹션|설명|
|---|---|
|[Windows Server 2016 이상에서 자동 제외](#automatic-exclusions-on-windows-server-2016-or-later)|자동 제외의 두 가지 주요 유형에 대해 설명하고 자동 제외에 대한 자세한 목록을 포함합니다.|
|[자동 제외 옵트아웃](#opting-out-of-automatic-exclusions)|자동 제외를 옵트아웃하는 방법을 설명하는 중요한 고려 사항 및 절차가 포함되어 있습니다.|
|[사용자 지정 제외 정의](#defining-custom-exclusions)|사용자 지정 제외를 정의하는 방법 정보에 대한 링크를 제공합니다.|
|

> [!IMPORTANT]
> 다음 점에 유의하십시오.
>
> - 사용자 지정 제외는 자동 제외보다 우선합니다.
> - 자동 제외는 RTP(실시간 보호) 검사에만 적용됩니다. 전체 검사, 빠른 검사 또는 수동 검사 중에는 자동 제외가 사용되지 않습니다.
> - 사용자 지정 및 중복 제외는 자동 제외와 충돌하지 않습니다.
> - Microsoft Defender 바이러스 백신 DISM(배포 이미지 서비스 및 관리) 도구를 사용하여 컴퓨터에 설치된 역할을 확인합니다.

## <a name="automatic-exclusions-on-windows-server-2016-or-later"></a>Windows Server 2016 이상에서 자동 제외

> [!NOTE]
> 자동 제외는 RTP(실시간 보호) 검사에만 적용됩니다. 전체 검사, 빠른 검사 또는 수동 검사 중에는 자동 제외가 사용되지 않습니다.

Windows Server 2016 이상에서는 다음 제외를 정의할 필요가 없습니다.

- 운영 체제 파일
- 서버 역할 및 서버 역할을 통해 추가되는 모든 파일

이 Microsoft Defender 바이러스 백신 기본 제공되어 있기 때문에 기본 제공 또는 Windows Server 2016 운영 체제 파일에 대한 제외가 필요하지 않습니다. 또한 Windows Server 2016 이상을 실행하고 역할을 설치하면 Microsoft Defender 바이러스 백신 설치하는 동안 추가되는 모든 파일과 서버 역할에 대한 자동 제외가 포함됩니다.

운영 체제 제외 및 서버 역할 제외는 Windows 보안 앱에 표시된 표준 제외 [목록에 나타나지 않습니다.](microsoft-defender-security-center-antivirus.md)

서버 역할 및 운영 체제 파일에 대한 자동 제외는 R2 또는 Windows Server 2012 Windows Server 2012 않습니다.

### <a name="the-list-of-automatic-exclusions"></a>자동 제외 목록

다음 섹션에는 자동 제외 파일 경로 및 파일 형식과 함께 제공된 제외가 포함되어 있습니다.

#### <a name="default-exclusions-for-all-roles"></a>모든 역할에 대한 기본 제외

이 섹션에는 Windows Server 2016 Server 2019의 모든 역할에 대한 Windows 나열되어 있습니다.

> [!NOTE]
> 기본 위치는 이 문서에 나와 있는 위치와 다를 수 있습니다.

##### <a name="windows-tempedb-files"></a>Windows "temp.edb" 파일

- `%windir%\SoftwareDistribution\Datastore\*\tmp.edb`
- `%ProgramData%\Microsoft\Search\Data\Applications\Windows\*\*.log`

##### <a name="windows-update-files-or-automatic-update-files"></a>Windows 파일 업데이트 또는 자동 업데이트 파일

- `%windir%\SoftwareDistribution\Datastore\*\Datastore.edb`
- `%windir%\SoftwareDistribution\Datastore\*\edb.chk`
- `%windir%\SoftwareDistribution\Datastore\*\edb\*.log`
- `%windir%\SoftwareDistribution\Datastore\*\Edb\*.jrs`
- `%windir%\SoftwareDistribution\Datastore\*\Res\*.log`

##### <a name="windows-security-files"></a>Windows 보안 파일

- `%windir%\Security\database\*.chk`
- `%windir%\Security\database\*.edb`
- `%windir%\Security\database\*.jrs`
- `%windir%\Security\database\*.log`
- `%windir%\Security\database\*.sdb`

##### <a name="group-policy-files"></a>그룹 정책 파일

- `%allusersprofile%\NTUser.pol`
- `%SystemRoot%\System32\GroupPolicy\Machine\registry.pol`
- `%SystemRoot%\System32\GroupPolicy\User\registry.pol`

##### <a name="wins-files"></a>WINS 파일

- `%systemroot%\System32\Wins\*\*.chk`
- `%systemroot%\System32\Wins\*\*.log`
- `%systemroot%\System32\Wins\*\*.mdb`
- `%systemroot%\System32\LogFiles\`
- `%systemroot%\SysWow64\LogFiles\`

##### <a name="file-replication-service-frs-exclusions"></a>FRS(파일 복제 서비스) 제외

- FRS(파일 복제 서비스) 작업 폴더의 파일 FRS 작업 폴더가 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Working Directory`

  - `%windir%\Ntfrs\jet\sys\*\edb.chk`
  - `%windir%\Ntfrs\jet\*\Ntfrs.jdb`
  - `%windir%\Ntfrs\jet\log\*\*.log`

- FRS 데이터베이스 로그 파일입니다. FRS 데이터베이스 로그 파일 폴더가 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\Ntfrs\Parameters\DB Log File Directory`

  - `%windir%\Ntfrs\*\Edb\*.log`

- FRS 준비 폴더입니다. 준비 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NtFrs\Parameters\Replica Sets\GUID\Replica Set Stage`

  - `%systemroot%\Sysvol\*\Ntfrs_cmp*\`

- FRS 사전 설치 폴더입니다. 이 폴더는 폴더에 의해 지정됩니다. `Replica_root\DO_NOT_REMOVE_NtFrs_PreInstall_Directory`

  - `%systemroot%\SYSVOL\domain\DO_NOT_REMOVE_NtFrs_PreInstall_Directory\*\Ntfrs*\`

- DFSR(분산 파일 시스템 복제) 데이터베이스 및 작업 폴더 이러한 폴더는 레지스트리 키로 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DFSR\Parameters\Replication Groups\GUID\Replica Set Configuration File`

  > [!NOTE]
  > 사용자 지정 위치에 대한 자세한 내용은 자동 제외 [옵트아웃을 참조하세요.](#opting-out-of-automatic-exclusions)

  - `%systemdrive%\System Volume Information\DFSR\$db_normal$`
  - `%systemdrive%\System Volume Information\DFSR\FileIDTable_*`
  - `%systemdrive%\System Volume Information\DFSR\SimilarityTable_*`
  - `%systemdrive%\System Volume Information\DFSR\*.XML`
  - `%systemdrive%\System Volume Information\DFSR\$db_dirty$`
  - `%systemdrive%\System Volume Information\DFSR\$db_clean$`
  - `%systemdrive%\System Volume Information\DFSR\$db_lostl$`
  - `%systemdrive%\System Volume Information\DFSR\Dfsr.db`
  - `%systemdrive%\System Volume Information\DFSR\*.frx`
  - `%systemdrive%\System Volume Information\DFSR\*.log`
  - `%systemdrive%\System Volume Information\DFSR\Fsr*.jrs`
  - `%systemdrive%\System Volume Information\DFSR\Tmp.edb`

##### <a name="process-exclusions"></a>프로세스 제외

- `%systemroot%\System32\dfsr.exe`
- `%systemroot%\System32\dfsrs.exe`

##### <a name="hyper-v-exclusions"></a>Hyper-V 제외

다음 표에는 Hyper-V 설치할 때 자동으로 배달되는 파일 형식 제외, 폴더 제외 및 프로세스 제외가 나열되어 있습니다.

<br>

****

|제외 유형|구체적|
|---|---|
|파일 형식|`*.vhd` <br/> `*.vhdx` <br/> `*.avhd` <br/> `*.avhdx` <br/> `*.vsv` <br/> `*.iso` <br/> `*.rct` <br/> `*.vmcx` <br/> `*.vmrs`|
|폴더|`%ProgramData%\Microsoft\Windows\Hyper-V` <br/> `%ProgramFiles%\Hyper-V` <br/> `%SystemDrive%\ProgramData\Microsoft\Windows\Hyper-V\Snapshots` <br/> `%Public%\Documents\Hyper-V\Virtual Hard Disks`|
|프로세스|`%systemroot%\System32\Vmms.exe` <br/> `%systemroot%\System32\Vmwp.exe`|
|

##### <a name="sysvol-files"></a>SYSVOL 파일

- `%systemroot%\Sysvol\Domain\*.adm`
- `%systemroot%\Sysvol\Domain\*.admx`
- `%systemroot%\Sysvol\Domain\*.adml`
- `%systemroot%\Sysvol\Domain\Registry.pol`
- `%systemroot%\Sysvol\Domain\*.aas`
- `%systemroot%\Sysvol\Domain\*.inf`
- `%systemroot%\Sysvol\Domain\*Scripts.ini`
- `%systemroot%\Sysvol\Domain\*.ins`
- `%systemroot%\Sysvol\Domain\Oscfilter.ini`


#### <a name="active-directory-exclusions"></a>Active Directory 제외

이 섹션에는 AD DS(Active Directory 도메인 서비스)를 설치할 때 자동으로 배달되는 제외가 나열되어 있습니다.

##### <a name="ntds-database-files"></a>NTDS 데이터베이스 파일

데이터베이스 파일이 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Database File`

- `%windir%\Ntds\ntds.dit`
- `%windir%\Ntds\ntds.pat`

##### <a name="the-ad-ds-transaction-log-files"></a>AD DS 트랜잭션 로그 파일

트랜잭션 로그 파일이 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\Database Log Files Path`

- `%windir%\Ntds\EDB*.log`
- `%windir%\Ntds\Res*.log`
- `%windir%\Ntds\Edb*.jrs`
- `%windir%\Ntds\Ntds*.pat`
- `%windir%\Ntds\TEMP.edb`

##### <a name="the-ntds-working-folder"></a>NTDS 작업 폴더

이 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\NTDS\Parameters\DSA Working Directory`

- `%windir%\Ntds\Temp.edb`
- `%windir%\Ntds\Edb.chk`

##### <a name="process-exclusions-for-ad-ds-and-ad-ds-related-support-files"></a>AD DS 및 AD DS 관련 지원 파일에 대한 프로세스 제외

- `%systemroot%\System32\ntfrs.exe`
- `%systemroot%\System32\lsass.exe`

#### <a name="dhcp-server-exclusions"></a>DHCP 서버 제외

이 섹션에는 DHCP 서버 역할을 설치할 때 자동으로 배달되는 제외가 나열되어 있습니다. DHCP 서버 파일 위치는 레지스트리 키의 *DatabasePath,* *DhcpLogFilePath* 및 *BackupDatabasePath* 매개 변수에 의해 지정됩니다. `HKEY_LOCAL_MACHINE\System\CurrentControlSet\Services\DHCPServer\Parameters`

- `%systemroot%\System32\DHCP\*\*.mdb`
- `%systemroot%\System32\DHCP\*\*.pat`
- `%systemroot%\System32\DHCP\*\*.log`
- `%systemroot%\System32\DHCP\*\*.chk`
- `%systemroot%\System32\DHCP\*\*.edb`

#### <a name="dns-server-exclusions"></a>DNS 서버 제외

이 섹션에는 DNS 서버 역할을 설치할 때 자동으로 배달되는 파일 및 폴더 제외 및 프로세스 제외가 나열되어 있습니다.

##### <a name="file-and-folder-exclusions-for-the-dns-server-role"></a>DNS 서버 역할에 대한 파일 및 폴더 제외

- `%systemroot%\System32\Dns\*\*.log`
- `%systemroot%\System32\Dns\*\*.dns`
- `%systemroot%\System32\Dns\*\*.scc`
- `%systemroot%\System32\Dns\*\BOOT`

##### <a name="process-exclusions-for-the-dns-server-role"></a>DNS 서버 역할에 대한 프로세스 제외

- `%systemroot%\System32\dns.exe`

#### <a name="file-and-storage-services-exclusions"></a>파일 및 Storage 서비스 제외

이 섹션에는 파일 및 Storage 서비스 역할을 설치할 때 자동으로 배달되는 파일 및 폴더 제외가 나열되어 있습니다. 아래에 나열된 제외에는 클러스터링 역할에 대한 제외가 포함되어 있지 않습니다.

- `%SystemDrive%\ClusterStorage`
- `%clusterserviceaccount%\Local Settings\Temp`
- `%SystemDrive%\mscs`

#### <a name="print-server-exclusions"></a>인쇄 서버 제외

이 섹션에는 인쇄 서버 역할을 설치할 때 자동으로 배달되는 파일 형식 제외, 폴더 제외 및 프로세스 제외가 나열되어 있습니다.

##### <a name="file-type-exclusions"></a>파일 형식 제외

- `*.shd`
- `*.spl`

##### <a name="folder-exclusions"></a>폴더 제외

이 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Print\Printers\DefaultSpoolDirectory`

- `%system32%\spool\printers\*`

##### <a name="process-exclusions"></a>프로세스 제외

- `spoolsv.exe`

#### <a name="web-server-exclusions"></a>웹 서버 제외

이 섹션에는 웹 서버 역할을 설치할 때 자동으로 배달되는 폴더 제외 및 프로세스 제외가 나열되어 있습니다.

##### <a name="folder-exclusions"></a>폴더 제외

- `%SystemRoot%\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\IIS Temporary Compressed Files`
- `%SystemDrive%\inetpub\temp\ASP Compiled Templates`
- `%systemDrive%\inetpub\logs`
- `%systemDrive%\inetpub\wwwroot`

##### <a name="process-exclusions"></a>프로세스 제외

- `%SystemRoot%\system32\inetsrv\w3wp.exe`
- `%SystemRoot%\SysWOW64\inetsrv\w3wp.exe`
- `%SystemDrive%\PHP5433\php-cgi.exe`

##### <a name="turning-off-scanning-of-files-in-the-sysvolsysvol-folder-or-the-sysvol_dfsrsysvol-folder"></a>Sysvol\Sysvol 폴더 또는 SYSVOL_DFSR\Sysvol 폴더에서 파일 검색 끄기

또는 폴더의 현재 위치와 모든 하위 폴더는 복제 데이터베이스 집합 루트의 파일 시스템 재분석 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 대상입니다. 및 폴더는 기본적으로 다음 `Sysvol\Sysvol` `SYSVOL_DFSR\Sysvol` 위치를 사용합니다.

- `%systemroot%\Sysvol\Domain`
- `%systemroot%\Sysvol_DFSR\Domain`

현재 활성 상태인 경로는 NETLOGON 공유에서 참조하며 다음 하위 키의 `SYSVOL` SysVol 값 이름으로 결정될 수 있습니다. `HKEY_LOCAL_MACHINE\SYSTEM\ControlSet001\Services\Netlogon\Parameters`

이 폴더와 모든 하위 폴더에서 다음 파일을 제외합니다.

- `*.adm`
- `*.admx`
- `*.adml`
- `Registry.pol`
- `Registry.tmp`
- `*.aas`
- `*.inf`
- `Scripts.ini`
- `*.ins`
- `Oscfilter.ini`

#### <a name="windows-server-update-services-exclusions"></a>Windows Server Update Services 제외

이 섹션에서는 WSUS(Windows Server Update Services) 역할을 설치할 때 자동으로 배달되는 폴더 제외를 나열합니다. WSUS 폴더는 레지스트리 키에 지정됩니다. `HKEY_LOCAL_MACHINE\Software\Microsoft\Update Services\Server\Setup`

- `%systemroot%\WSUS\WSUSContent`
- `%systemroot%\WSUS\UpdateServicesDBFiles`
- `%systemroot%\SoftwareDistribution\Datastore`
- `%systemroot%\SoftwareDistribution\Download`

## <a name="opting-out-of-automatic-exclusions"></a>자동 제외 옵트아웃

Windows Server 2016 보안 인텔리전스 업데이트에서 제공된 미리 정의한 제외는 역할 또는 기능에 대한 기본 경로만 제외합니다. 사용자 지정 경로에 역할 또는 기능을 설치하거나 제외 집합을 수동으로 제어하려는 경우 보안 인텔리전스 업데이트에 제공된 자동 제외를 옵트아웃해야 합니다. 그러나 자동으로 제공되는 제외는 해당 제외가 Windows Server 2016 최적화됩니다. 제외 [권장 사항](configure-exclusions-microsoft-defender-antivirus.md#recommendations-for-defining-exclusions) 정의하기 전에 제외를 정의하는 방법을 참조하세요.

> [!WARNING]
> 자동 제외를 옵트아웃하면 성능이 밝아지거나 데이터가 손상될 수 있습니다. 자동으로 전달되는 제외는 서버 2019 및 Windows Server 2016 Windows 최적화됩니다.

미리 정의한 제외는 기본 경로만 제외하기 때문에 NTDS 및 SYSVOL 폴더를 원래 경로와 다른 다른 드라이브 또는 경로로 이동하는 경우 제외를 수동으로 추가해야 합니다. 폴더 이름 또는 파일 확장명에 따라 제외 목록 [구성을 참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md#configure-the-list-of-exclusions-based-on-folder-name-or-file-extension)

그룹 정책, PowerShell cmdlet 및 WMI를 사용하여 자동 제외 목록을 사용하지 않도록 설정할 수 있습니다.

### <a name="use-group-policy-to-disable-the-auto-exclusions-list-on-windows-server-2016-and-windows-server-2019"></a>그룹 정책을 사용하여 Windows Server 2016 Server 2019에서 Windows 사용하지 않도록 설정

1. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc725752(v=ws.11))을 엽니다. 구성할 그룹 정책 개체를 마우스 오른쪽 단추로 클릭한 다음 편집 **을 선택합니다.**

2. 그룹 정책 **관리 편집기에서** 컴퓨터 **구성으로 이동한** 다음 관리 템플릿 **을 선택합니다.**

3. 트리를 확장하여 **Windows 구성 요소 Microsoft Defender 바이러스 백신** \>  \> **확장합니다.**

4. 자동 **제외** 해제를 두 번 클릭하고 옵션을 사용으로 **설정합니다.** 그런 다음 **확인** 을 선택합니다.

### <a name="use-powershell-cmdlets-to-disable-the-auto-exclusions-list-on-windows-server"></a>PowerShell cmdlet을 사용하여 Windows 서버에서 자동 제외 목록을 사용하지 않도록 설정

다음 cmdlet을 사용 합니다.

```PowerShell
Set-MpPreference -DisableAutoExclusions $true
```

자세한 내용은 다음 리소스를 참조하세요.

- [PowerShell cmdlet을 사용하여](use-powershell-cmdlets-microsoft-defender-antivirus.md)를 구성하고 Microsoft Defender 바이러스 백신.
- [에서 PowerShell을 Microsoft Defender 바이러스 백신.](/powershell/module/defender/)

### <a name="use-windows-management-instruction-wmi-to-disable-the-auto-exclusions-list-on-windows-server"></a>WMI(Windows Management Instruction)를 사용하여 Windows 서버에서 자동 제외 목록을 사용하지 않도록 설정

다음 속성에 MSFT_MpPreference [클래스의](/previous-versions/windows/desktop/defender/msft-mppreference) **Set** 메서드를 사용합니다.

```WMI
DisableAutoExclusions
```

자세한 정보 및 허용되는 매개 변수는 다음을 참조하세요.

- [Windows Defender WMIv2 API](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)

## <a name="defining-custom-exclusions"></a>사용자 지정 제외 정의

필요한 경우 사용자 지정 제외를 추가하거나 제거할 수 있습니다. 이를 위해 다음 문서를 참조합니다.

- [파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>참고 항목

- [검사에 대한 제외 Microsoft Defender 바이러스 백신 유효성 검사](configure-exclusions-microsoft-defender-antivirus.md)
- [파일 이름, 확장명 및 폴더 위치를 기반으로 제외 구성 및 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)
- [프로세스에서 연 파일에 대한 제외 구성 및 유효성 검사](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)
- [제외 정의 시 피해야 하는 일반적인 실수](common-exclusion-mistakes-microsoft-defender-antivirus.md)
- [사용자 지정, 시작 및 재구성 결과 Microsoft Defender 바이러스 백신 검토](customize-run-review-remediate-scans-microsoft-defender-antivirus.md)
- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
