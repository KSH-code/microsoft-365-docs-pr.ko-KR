---
title: 진단 로그
description: 문제 해결 중에 장치에서 수집될 수 있는 로그 및 로그가 저장되는 방법
keywords: Microsoft Managed Desktop, Microsoft 365, 서비스, 문서
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ef7d19fef989610c10323c2a9820a5314d5e1641
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59215312"
---
# <a name="diagnostic-logs"></a>진단 로그

사용자가 보고한 것이든 서비스에서 식별되어 있는지에 Microsoft Managed Desktop 관리되는 장치의 문제를 해결할 때 사용자의 개입 없이 장치에서 특정 진단 로그를 수집해야 할 수 있습니다. 사용자 생성 콘텐츠나 정보는 사용자 Director에서 수집하지 않습니다. 장치 상태와 관련한 진단 및 로그 데이터만 수집합니다.

수집된 로그는 28일 동안 저장한 다음 삭제합니다. 데이터 처리 표준에 따라 장치에서 [수집된 모든 로그를 처리합니다.](privacy-personal-data.md)

## <a name="data-collected"></a>수집된 데이터

이 목록에는 진단 로그를 수집할 수 있는 모든 폴더, Microsoft Managed Desktop, 실행 파일 또는 레지스트리 위치가 포함됩니다. 수집된 실제 데이터는 이 목록의 하위 집합이 되고 식별된 문제의 종속됩니다.

### <a name="registry-keys"></a>레지스트리 키

- HKLM \\ SYSTEM \\ CurrentControlSet \\ Services
- HKLM \\ 소프트웨어 \\ Microsoft \\ Surface
- HKLM \\ 소프트웨어 정책 Microsoft Windows \\ \\ \\ \\ WindowsUpdate
- HKLM \\ SYSTEM \\ CurrentControlSet \\ 컨트롤 \\ MUI \\ UILanguages
- HKLM \\ 소프트웨어 정책 Microsoft \\ \\ \\ WindowsStore
- HKLM \\ 소프트웨어 Microsoft Windows \\ \\ \\ CurrentVersion \\ WindowsStore \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ AppModel
- HKLM \\ SYSTEM \\ CurrentControlSet \\ 컨트롤 \\ 펌웨어소싱
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsSelfhost
- HKLM \\ SOFTWARE \\ Microsoft \\ WindowsUpdate
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Appx
- HKLM \\ SOFTWARE Microsoft Windows NT \\ \\ \\ CurrentVersion \\ Superfetch
- HKLM \\ 시스템 \\ 설정
- HKLM \\ Software \\ Microsoft \\ IntuneManagementExtension
- HKLM \\ SOFTWARE \\ Microsoft \\ SystemCertificates \\ AuthRoot
- HKLM \\ SOFTWARE Microsoft Windows Advanced Threat \\ \\ Protection
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Authentication \\ LogonUI
- HKLM \\ SOFTWARE Microsoft Windows \\ \\ \\ CurrentVersion \\ Internet 설정
- HKLM \\ 소프트웨어 Microsoft Windows \\ \\ \\ CurrentVersion \\ 제거
- HKLM \\ \\ 소프트웨어 정책
- HKLM \\ 소프트웨어 정책 Microsoft \\ \\ \\ Cryptography \\ Configuration \\ SSL
- HKLM 소프트웨어 정책 Microsoft Windows \\ \\ Advanced Threat \\ \\ Protection
- HKLM \\ SOFTWARE \\ WOW6432Node Microsoft Windows \\ \\ \\ CurrentVersion \\ 제거
- HKLM \\ SYSTEM \\ CurrentControlSet \\ Control \\ SecurityProviders \\ SCHANNEL

### <a name="commands"></a>명령

- %programfiles% \\ windows defender \\mpcmdrun.exe -GetFiles
- %windir% \\ system32 \\certutil.exe -store
- %windir% \\ system32 \\certutil.exe -store -user my
- %windir% \\ system32 \\Dsregcmd.exe /status
- %windir% \\ system32 \\ipconfig.exe /all
- %windir% \\ system32 \\ipconfig.exe /displaydns
- %windir% \\ system32 \\mdmdiagnosticstool.exe
- %windir% \\ system32 \\msinfo32.exe /report %temp% \\ MDMDiagnostics \\ msinfo32.log
- %windir% \\ system32netsh.exe \\ advfirewall show allprofiles
- %windir% \\ system32 \\netsh.exe advfirewall show global
- %windir% \\ system32 \\netsh.exe lan show profiles
- %windir% \\ system32 \\netsh.exe winhttp show proxy
- %windir% \\ system32 \\netsh.exe wlan show profiles
- %windir% \\ system32 \\netsh.exe wlanreport 표시
- %windir% \\ system32 \\ping.exe -n 50 localhost
- %windir% \\ system32 \\powercfg.exe /batteryreport /output %temp% \\ MDMDiagnostics \\battery-report.html
- %windir% \\ system32 \\powercfg.exe /energy /output %temp% \\ MDMDiagnostics \\energy-report.html
- bitsadmin /list /allusers /verbose
- fltMC.exe
- bcdedit /enum all /v
- manage-bde -protectors -get
- Windows PowerShell 명령:
    - Get-appxpackage -allusers
    - Get-appxpackage -packagetype 번들
    - Get-Service wuauserv
    - Get-NetFirewallRule
    - Get-WmiObject -Class win32 \_ 제품
    - Get-ComputerInfo
    - Get-Service
    - Get-Process
    - Get-WmiObject Win32 \_ PnPSignedDriver

### <a name="event-logs"></a>이벤트 로그

- 응용 프로그램
- Microsoft-Windows-AppLocker/EXE 및 DLL
- Microsoft-Windows-AppLocker/MSI 및 스크립트
- Microsoft-Windows-AppLocker/Packaged app-Deployment
- Microsoft-Windows-AppLocker/패키지된 앱 실행
- Microsoft-Windows-Bitlocker/Bitlocker 관리
- Microsoft-Windows-SENSE/Operational
- Microsoft-Windows-SenseIR/Operational
- 설정
- 시스템

### <a name="files"></a>파일

- %ProgramData% \\ Microsoft \\ DiagnosticLogCSP \\ Collectors \\ \* .etl
- %ProgramData% \\ Microsoft \\ IntuneManagementExtension \\ Logs \\ \* .\*
- %ProgramData% \\ Microsoft Windows Defender 지원 \\ \\ \\MpSupportFiles.cab
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReportwlan-report-latest.htm\\ l
- %ProgramData% \\ Microsoft \\ Windows \\ WlanReport -SourceFileName wlan-report-latest.html
- %windir% \\ ccm \\ logs \* .log
- %windir% \\ ccmsetup \\ logs \* .log
- %windir% \\ logs \\ CBS \\ cbs.log
- %windir% \\ logs \\ measuredboot \* .\*
- %windir% \\ Logs \\ WindowsUpdate \* .etl
- %windir% \\ inf \\ \* .log
- %windir% \\ 서비스 \\ 세션 \\ActionList.xml
- %windir% \\ 서비스 \\ 세션 \\Sessions.xml
- %windir% \\ SoftwareDistribution \\ DataStore \\ Logs \\ edb.log
- %windir% \\ SoftwareDistribution \\ DataStore \\ DataStore.edb
- %windir% \\ logs \\ dism \\ dism.log
- %SystemRoot% \\ System32 \\ Winevt \\ Logs\\
- %appdata% \\ Microsoft Teams 미디어 스택 \\ \\ \\ \* .blog
- %appdata% \\ Microsoft \\ Teams \\ skylib \\ \* .blog
- %appdata% \\ Microsoft Teams 미디어 스택 \\ \\ \\ \* .etl
- %appdata% \\ Microsoft \\ Teams \\logs.txt
- %windir% \\ Windows \\ System32 \\ winevt \\ \* .\*