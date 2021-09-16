---
title: 타사 HIPS에서 ASR 규칙으로 마이그레이션
description: 타사 HIPS(호스트 침입 방지 시스템) 솔루션에서 ASR 규칙으로의 마이그레이션에 접근하는 방법에 대해 설명
keywords: 공격 표면 감소 규칙, asr, asr 규칙, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지, 악용, 감염 방지, 끝점용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.topic: article
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.openlocfilehash: 0c2ffdde4ff259f2a2ef098a6d715cbcd785dfe4
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59401689"
---
# <a name="migrating-from-a-third-party-hips-to-asr-rules"></a>타사 HIPS에서 ASR 규칙으로 마이그레이션

이 문서에서는 공통 규칙을 끝점용 Microsoft Defender에 매핑하는 데 도움이 됩니다.

## <a name="scenarios-when-migrating-from-a-third-party-hips-product-to-asr-rules"></a>타사 HIPS 제품에서 ASR 규칙으로 마이그레이션할 때의 시나리오

### <a name="block-creation-of-specific-files"></a>특정 파일 만들기 차단

- **적용대상**- 모든 프로세스
- **작업**- 파일 만들기
- **Files/Folders, Registry Keys/Values, Processes, Services**- *.zepto, *.odin, *.locky, *.jaff, *.lukitus, *.wnry, *.krab의 예
- **공격 표면 감소 규칙**- ASR 규칙은 IOC(손상 표시기)가 아닌 공격 기술을 차단합니다. 특정 파일 확장명을 차단하는 것은 장치가 손상되는 것을 방지하지 않는 것이기 때문에 항상 유용하지는 않습니다. 공격자가 페이로드에 대한 새 유형의 확장을 만들 때까지 공격을 부분적으로만 저지합니다.
- **기타 권장 기능**- 클라우드 보호 및 동작 분석과 함께 Microsoft Defender AV를 사용하도록 설정하는 것이 좋습니다. "랜섬웨어에 대한 고급 보호 사용" ASR 규칙과 같은 다른 방지를 사용하는 것이 좋습니다. 이를 통해 랜섬웨어 공격으로부터 더 높은 수준의 보호를 제공합니다. 또한 이러한 레지스트리 키 중 상당수는 특정 경고를 트리거하는 ASEP 기술과 같은 끝점용 Microsoft Defender에서 모니터링합니다. 사용되는 레지스트리 키에는 최소한 로컬 관리자 또는 신뢰할 수 있는 설치 관리자 권한이 필요합니다. 최소한의 관리 계정이나 권한으로 잠긴 환경을 사용하는 것이 좋습니다. 더 광범위한 보안 권장 사항의 일부인 "필수가 아닌 역할에 대해 SeDebug 사용 안 하게"를 비롯한 기타 시스템 구성을 사용하도록 설정할 수 있습니다.

### <a name="block-creation-of-specific-registry-keys"></a>특정 레지스트리 키 만들기 차단

- **적용대상**- 모든 프로세스
- **프로세스**- N/A
- **작업**- 레지스트리 수정
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스의 예** -  *\Software*,HKCU\Environment\UserInitMprLogonScript,HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Accessibility\ATs *\StartExe, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\Image File Execution Options*\Debugger, HKEY_CURRENT_USER\Software\Microsoft\HtmlHelp Author\location, HKLM\SOFTWARE\Microsoft\Windows NT\CurrentVersion\SilentProcessExit*\MonitorProcess
- **공격 표면 감소 규칙**- ASR 규칙은 IOC(손상 표시기)가 아닌 공격 기술을 차단합니다. 특정 파일 확장명을 차단하는 것은 장치가 손상되는 것을 방지하지 않는 것이기 때문에 항상 유용하지는 않습니다. 공격자가 페이로드에 대한 새 유형의 확장을 만들 때까지 공격을 부분적으로만 저지합니다.
- **기타 권장 기능**- 클라우드 보호 및 동작 분석과 함께 Microsoft Defender AV를 사용하도록 설정하는 것이 좋습니다. "랜섬웨어에 대한 고급 보호 사용" ASR 규칙과 같은 추가 방지를 사용하는 것이 좋습니다. 이를 통해 랜섬웨어 공격으로부터 더 높은 수준의 보호를 제공합니다. 또한 이러한 레지스트리 키 중 일부가 특정 경고를 트리거하는 ASEP 기술과 같은 끝점용 Microsoft Defender에서 모니터링합니다. 또한 사용되는 레지스트리 키에는 최소한 로컬 관리자 또는 신뢰할 수 있는 설치 관리자 권한이 필요합니다. 최소한의 관리 계정이나 권한으로 잠긴 환경을 사용하는 것이 좋습니다. 더 광범위한 보안 권장 사항의 일부인 "필수가 아닌 역할에 대해 SeDebug 사용 안 하게"를 비롯한 기타 시스템 구성을 사용하도록 설정할 수 있습니다.

### <a name="block-untrusted-programs-from-running-from-removable-drives"></a>이동식 드라이브에서 트러스터가 실행되지 않는 프로그램 차단

- **적용 프로그램**- USB의 트러프되지 않은 프로그램
- **프로세스**- *
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스의 예:*
- **공격** 표면 감소 규칙 - ASR 규칙에는 "USB에서 실행되는 트러블되지 않은 프로세스 및 부호 없는 프로세스 차단", GUID "b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4"의 기본 제공 규칙이 있습니다.
- **기타 권장** 기능 - 끝점용 Microsoft Defender를 사용하여 USB 장치 및 기타 이동식 미디어에 대한 추가 컨트롤을 살펴보기: 끝점용 [Microsoft Defender를](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)사용하여 USB 장치 및 기타 이동식 미디어를 제어하는 방법.

### <a name="block-mshta-from-launching-certain-child-processes"></a>Mshta에서 특정 하위 프로세스를 시작하지 차단

- **적용대상**- Mshta
- **프로세스**- mshta.exe
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- powershell.exe, cmd.exe, regsvr32.exe
- **공격 표면 감소 규칙**- ASR 규칙은 하위 프로세스가 "하위 프로세스"를 "mshta.exe. 이 컨트롤은 Exploit Protection 또는 응용 프로그램 제어의 Windows Defender 있습니다.
- **기타 권장 기능**- 응용 Windows Defender 응용 프로그램 제어를 사용하도록 설정하여 응용 mshta.exe 실행되지 않도록 합니다. 조직에서 업무용 앱에 "mshta.exe" 요구하는 경우 조직에서 하위 Windows Defender 시작하지 못하도록 특정 Windows Defender Exploit Protection 규칙을 mshta.exe 구성합니다.

### <a name="block-outlook-from-launching-child-processes"></a>하위 Outlook 시작하지 차단

- **적용하는 Outlook**
- **프로세스**- outlook.exe
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- powershell.exe
- **공격** 표면 감소 규칙 - ASR 규칙에는 Office 통신 앱(Outlook, Skype 및 Teams)이 하위 프로세스를 시작하지 못하게 하는 기본 제공 규칙이 있습니다. "Office 통신 응용 프로그램이 자식 프로세스를 만들지 못하게 차단", GUID "26190899-1602-49e8-8b27-eb1d0a1ce869".
- **기타 권장 기능**- PowerShell의 공격 표면을 최소화하기 위해 PowerShell 제한 언어 모드를 사용하도록 설정하는 것이 좋습니다.

### <a name="block-office-apps-from-launching-child-processes"></a>앱의 Office 프로세스 시작 차단

- **적용일**- Office
- **프로세스**- winword.exe, powerpnt.exe, excel.exe
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- powershell.exe, cmd.exe, wscript.exe, mshta.exe, EQNEDT32.EXE, regsrv32.exe
- **공격** 표면 감소 규칙 - ASR 규칙에는 Office 앱이 하위 프로세스를 시작하지 못하게 하는 기본 제공 규칙이 있습니다. "모든 Office 응용 프로그램이 하위 프로세스를 만들지 못하게 차단", GUID "d4f940ab-401b-4efc-aadc-ad5f3c50688a".
- **기타 권장 기능**- N/A

### <a name="block-office-apps-from-creating-executable-content"></a>앱에서 Office 콘텐츠를 만들지 차단

- **적용일**- Office
- **프로세스**- winword.exe, powerpnt.exe, excel.exe
- **작업**- 파일 만들기
- **파일/폴더, 레지스트리 키/값, 프로세스의 예,** 서비스 - C:\Users ***\AppData.exe, C:\ProgramData**.exe, C:\ProgramData**.com, C:\Users* AppData\Local\Temp **.com, C:\Users*\Downloads**.exe, C:\Users ***\AppData .scf, C:\ProgramData**.scf, C:\Users\Public*.exe, C:\Users*\Desktop***.exe
- **공격 표면 감소 규칙**- N/A.

### <a name="block-wscript-from-reading-certain-types-of-files"></a>Wscript에서 특정 형식의 파일을 읽지 않습니다.

- **적용대상**- Wscript
- **프로세스**- wscript.exe
- **작업**- 파일 읽기
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- C:\Users *\AppData**.js, C:\Users*\Downloads**.js
- **공격 표면 감소 규칙**- 안정성 및 성능 문제로 인해 ASR 규칙에는 특정 프로세스가 특정 스크립트 파일 형식을 읽는 것을 방지할 수 있는 기능이 없습니다. 이러한 시나리오에서 시작될 수 있는 공격 벡터를 방지하는 규칙이 있습니다. 규칙 이름은 "JavaScript 또는 VBScript에서 다운로드된 실행 콘텐츠 시작을 차단"(GUID "d3e037e1-3eb8-44c8-a917-57927947596)입니다.d") 및 "잠재적으로 난치될 수 있는 스크립트의 실행 차단"(GUID " 5beb7efe-fd9a-4556-801d-275e5ffc04cc").
- 다른 권장 기능 **-** 이러한 시나리오 내에서 특정 공격 벡터를 완화하는 특정 ASR 규칙이 있는 경우 AV가 AMSI(맬웨어 방지 검사 인터페이스)를 통해 실시간으로 스크립트(PowerShell, Windows Script Host, JavaScript, VBScript 등)를 실시간으로 검사할 수 있습니다. 자세한 내용은 [AMSI(맬웨어](/windows/win32/amsi/antimalware-scan-interface-portal)방지 검사 인터페이스)에서 사용할 수 있습니다.

### <a name="block-launch-of-child-processes"></a>하위 프로세스 시작 차단

- **적용대상**- Adobe Acrobat
- **프로세스**- AcroRd32.exe, Acrobat.exe
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- cmd.exe, powershell.exe, wscript.exe
- **공격 표면 감소 규칙**- ASR 규칙은 Adobe Reader가 하위 프로세스를 시작하지 못하도록 차단하도록 허용합니다. 규칙 이름은 "Adobe Reader에서 하위 프로세스를 만들 수 없습니다.", GUID "7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c"입니다.
- **기타 권장 기능**- N/A

### <a name="block-download-or-creation-of-executable-content"></a>실행 가능한 콘텐츠 다운로드 또는 만들기 차단

- **적용 사항**- CertUtil: 실행 파일을 다운로드 또는 만들기 차단
- **프로세스**- certutil.exe
- **작업**- 파일 만들기
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- *.exe
- **공격 표면 감소 규칙**- ASR 규칙은 보안 보호의 일부이기 때문에 이러한 시나리오를 Microsoft Defender 바이러스 백신 않습니다.
- **기타 권장 기능**- Microsoft Defender AV는 CertUtil이 실행 파일을 만들거나 다운로드하지 못하게 합니다.

### <a name="block-processes-from-stopping-critical-system-components"></a>프로세스에서 중요한 시스템 구성 요소를 중지하지 못하게 차단

- **적용대상**- 모든 프로세스
- **프로세스**- *
- **작업**- 프로세스 종료
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- MsSense.exe, MsMpEng.exe, NisSrv.exe, svchost.exe*, services.exe, csrss.exe, smss.exe, wininit.exe 등입니다.
- **공격 표면 감소 규칙**- ASR 규칙은 기본 제공 보안 보호 기능으로 보호되어 있기 때문에 이러한 Windows 10 지원하지 않습니다.
- ELAM(맬웨어 방지 조기 실행), PPL(보호 프로세스 조명), PPL 맬웨어 방지 조명 및 System Guard와 같은 권장 기능도 있습니다.

### <a name="block-specific-launch-process-attempt"></a>특정 시작 프로세스 시도 차단

- **적용 주체**- 특정 프로세스
- **프로세스**- "프로세스 이름 지정"
- **작업**- 프로세스 실행
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스**- tor.exe, bittorrent.exe, cmd.exe, powershell.exe 등
- **공격 표면 감소 규칙**- 전체적으로 ASR 규칙은 응용 프로그램 관리자로 작동하도록 설계되지 않습니다.
- **기타 권장 기능**- 사용자가 특정 프로세스 또는 프로그램을 시작하지 못하도록 방지하기 위해 응용 프로그램 제어를 Windows Defender 좋습니다. Microsoft Defender for Endpoint File and Cert indicators는 인시던트 대응 시나리오에서 사용할 수 있습니다(응용 프로그램 제어 메커니즘으로 표시하지 말아야 합니다).

### <a name="block-unauthorized-changes-to-microsoft-defender-antivirus-configurations"></a>구성에 대한 무단 Microsoft Defender 바이러스 백신 차단

- **적용대상**- 모든 프로세스
- **프로세스**- *
- **작업**- 레지스트리 수정
- **파일/폴더, 레지스트리 키/값, 프로세스, 서비스 -** HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\DisableAntiSpyware, HKLM\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\AllowRealTimeMonitoring과 같은 예입니다.
- **공격 표면 감소 규칙**- ASR 규칙은 끝점에 대한 Microsoft Defender 기본 제공 보호의 일부이기 때문에 이러한 시나리오를 다루지 않습니다.
- 기타 권장 **기능인** 변조 방지(옵트인(opt in, Intune에서 관리)는 DisableAntiVirus, DisableAntiSpyware, DisableRealtimeMonitoring, DisableOnAccessProtection, DisableBehaviorMonitoring 및 DisableIOAVProtection 레지스트리 키에 대한 무단 변경을 방지합니다.

참고 항목

- [공격 표면 감소 FAQ](attack-surface-reduction-faq.yml)
- [공격 표면 감소 규칙 사용](enable-attack-surface-reduction.md)
- [공격 표면 감소 규칙 평가](evaluate-attack-surface-reduction.md)
