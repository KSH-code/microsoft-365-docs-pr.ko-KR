---
title: 공격 노출 영역 축소 규칙
description: 규칙에 따라 공격 표면 감소 규칙에 대한 세부 정보를 나열합니다.
keywords: 공격 표면 감소 규칙, ASR, asr 규칙, hips, 호스트 침입 방지 시스템, 보호 규칙, 악용 방지 규칙, 악용 방지 규칙, 감염 방지 규칙, 끝점용 Microsoft Defender, ASR 규칙 구성, ASR 규칙 설명
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar, jcedola
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 1ef91e980f5cb49432a223b50a94fb0bf2354746
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/16/2021
ms.locfileid: "59399830"
---
# <a name="attack-surface-reduction-rules"></a>공격 노출 영역 축소 규칙

이 문서에서는 공격 감소 규칙에 대한 정보를 제공합니다.

- [지원되는 운영 체제 버전](#supported-operating-systems)
- [지원되는 구성 관리 시스템](#supported-configuration-management-systems)
- [규칙에 대한 설명](#per-rule-descriptions)
  - 규칙 설명
  - GUID
  - 구성 관리 시스템 규칙 이름

## <a name="supported-operating-systems"></a>지원되는 운영 체제 

다음 표에는 공격 표면 감소 규칙이 사전순으로 나열됩니다. 확인 표시는 해당 열에 나열된 운영 체제에서 규칙이 지원되는 경우를 나타냅니다.

> [!Note]
>
> - 달리 명시하지 않는 한 최소 Windows 10 빌드는 버전 &nbsp; 1709(RS3, 빌드 16299) 이상, 최소 Windows Server 빌드 버전은 &nbsp; 1809 이상입니다.
>
> - \* 모든 규칙은 다른 명시가 없는 한 파일 및 폴더 제외를 지원합니다.

|규칙 이름|&nbsp;Windows 10|&nbsp;Windows Server 2019|&nbsp;Windows 서버|&nbsp;Windows Server 2016|&nbsp;Windows Server 2012 R2|
|---|:---:|:---:|:---:|:---:|:---:|
|[악용된 취약한 서명된 드라이버의 남용 차단](#block-abuse-of-exploited-vulnerable-signed-drivers) | Y | Y | Y 버전 1803(반기 채널) 이상 |  |  |
|[Adobe Reader에서 하위 프로세스를 만들지 차단](#block-adobe-reader-from-creating-child-processes) | Y 버전 1809 이상 | Y | Y  <br><br> |  |  |
|[모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-all-office-applications-from-creating-child-processes) | Y | Y | Y <br><br> |  |  |
|[로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | Y 버전 1803 이상 | Y <br><br> | Y <br><br> |  |  |
|[전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단](#block-executable-content-from-email-client-and-webmail) | Y | Y <br><br> | Y <br><br> |  |  |
|[실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | Y 버전 1803 이상 | Y <br><br> | Y <br><br> |  |  |
|[잠재적으로 난치될 수 있는 스크립트의 실행 차단](#block-execution-of-potentially-obfuscated-scripts) | Y | Y <br><br> | Y <br><br> |  |  |
|[JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | Y | Y <br><br> | Y <br><br> |  |  |
|[응용 Office 콘텐츠 만들기 차단](#block-office-applications-from-creating-executable-content) | Y | Y <br><br> | Y <br><br> |  |  |
|[응용 Office 코드 삽입 차단](#block-office-applications-from-injecting-code-into-other-processes)  | Y | Y <br><br> | Y <br><br> |  |  |
|[통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-office-communication-application-from-creating-child-processes) | Y | Y <br><br> | Y <br><br> |  |  |
|[WMI 이벤트 구독을 통한 지속성 차단](#block-persistence-through-wmi-event-subscription) <br><br> \*_파일 및 폴더 제외는 지원되지 않습니다._ | Y 버전 1903(빌드 18362) 이상| Y | Y <br><br> 버전 1903(빌드 18362) 이상 |  |  |
|[PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단](#block-process-creations-originating-from-psexec-and-wmi-commands) | Y 버전 1803 이상 | Y <br><br> | Y <br><br>  |  |  |
|[USB에서 실행된 무단 및 사인되지 않은 프로세스 차단](#block-untrusted-and-unsigned-processes-that-run-from-usb) | Y | Y <br><br> | Y <br><br> |  |  |
|[매크로에서 Win32 API Office 차단](#block-win32-api-calls-from-office-macros) | Y | Y <br><br> | Y <br><br> |  |  |
|[랜섬웨어에 대한 고급 보호 사용](#use-advanced-protection-against-ransomware) | Y 버전 1803 이상 | Y <br><br> | Y <br><br> |  |  |
| **규칙 이름** |  **&nbsp;Windows 10** | **&nbsp;Windows Server 2019** | **&nbsp;Windows 서버** | **&nbsp;Windows Server 2016** | **&nbsp;Windows Server 2012 R2** |

## <a name="supported-configuration-management-systems"></a>지원되는 구성 관리 시스템

이 표에서 참조되는 구성 관리 시스템 버전에 대한 링크는 아래 표에 나와 있습니다.

|규칙 이름 | Intune | Microsoft Endpoint Manager |Microsoft Endpoint Configuration Manager |그룹 정책 <sup> [[1]](#fn1)<sup></sup> | PowerShell <sup> [[1](#fn1)]<sup></sup>  |
|---|:---:|:---:|:---:|:---:|:---:|
|[악용된 취약한 서명된 드라이버의 남용 차단](#block-abuse-of-exploited-vulnerable-signed-drivers) | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |  ![지원](images/checkmark.png) <br><br> MEM OMA-URI |   | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |  ![지원](images/checkmark.png) <br><br> |
|[Adobe Reader에서 하위 프로세스를 만들지 차단](#block-adobe-reader-from-creating-child-processes) | ![지원되지 않습니다.](images/checkmark.png) |   | ![지원](images/checkmark.png) | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-all-office-applications-from-creating-child-processes) | ![지원되지 않습니다.](images/checkmark.png) |   | ![지원](images/checkmark.png) <br><br> CB 1710 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[로컬 보안 기관 하위 Windows(lsass.exe)에서 자격 증명 도용 차단](#block-credential-stealing-from-the-windows-local-security-authority-subsystem) | ![지원되지 않습니다.](images/checkmark.png)  |   |  ![지원](images/checkmark.png) <br><br> CB 1802 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단](#block-executable-content-from-email-client-and-webmail) | ![지원되지 않습니다.](images/checkmark.png) |  | ![지원](images/checkmark.png) <br><br> CB 1710 | ![지원](images/checkmark.png) | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단](#block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion) | ![지원되지 않습니다.](images/checkmark.png) |   | ![지원](images/checkmark.png) <br><br> CB 1802 |  ![지원되지 않습니다.](images/checkmark.png) <br><br> |  ![지원되지 않습니다.](images/checkmark.png) <br><br> |
|[잠재적으로 난치될 수 있는 스크립트의 실행 차단](#block-execution-of-potentially-obfuscated-scripts) | ![지원되지 않습니다.](images/checkmark.png) |   |  ![지원](images/checkmark.png)  <br><br> CB 1710 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단](#block-javascript-or-vbscript-from-launching-downloaded-executable-content) | ![지원되지 않습니다.](images/checkmark.png) |   |  ![지원](images/checkmark.png) <br><br> CB 1710 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[응용 Office 콘텐츠 만들기 차단](#block-office-applications-from-creating-executable-content) | ![지원되지 않습니다.](images/checkmark.png) <br><br> |  | ![지원](images/checkmark.png) <br><br> CB 1710 <br><br> | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[응용 Office 코드 삽입 차단](#block-office-applications-from-injecting-code-into-other-processes) | ![지원되지 않습니다.](images/checkmark.png) |  |  ![지원](images/checkmark.png) <br><br> CB 1710 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단](#block-office-communication-application-from-creating-child-processes) | ![지원되지 않습니다.](images/checkmark.png) |  | ![지원](images/checkmark.png) <br><br>  CB 1710 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[WMI 이벤트 구독을 통한 지속성 차단](#block-persistence-through-wmi-event-subscription) |  |  |  |![지원되지 않습니다.](images/checkmark.png) <br><br>   | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단](#block-process-creations-originating-from-psexec-and-wmi-commands) | ![지원](images/checkmark.png) |   |   |  ![지원되지 않습니다.](images/checkmark.png) <br><br> | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[USB에서 실행된 무단 및 사인되지 않은 프로세스 차단](#block-untrusted-and-unsigned-processes-that-run-from-usb) | ![지원되지 않습니다.](images/checkmark.png) |   | ![지원](images/checkmark.png) <br><br> CB 1802 <br><br> | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |
|[매크로에서 Win32 API Office 차단](#block-win32-api-calls-from-office-macros) | ![지원되지 않습니다.](images/checkmark.png) |   | ![지원](images/checkmark.png) <br><br> CB 1710 <br><br> | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |  ![지원되지 않습니다.](images/checkmark.png) <br><br> |
|[랜섬웨어에 대한 고급 보호 사용](#use-advanced-protection-against-ransomware) | ![지원되지 않습니다.](images/checkmark.png) |   |  ![지원](images/checkmark.png) <br><br>  CB 1802 | ![지원되지 않습니다.](images/checkmark.png) <br><br>  | ![지원되지 않습니다.](images/checkmark.png) <br><br>  |

  (<a id="fn1">1)</a>규칙의 GUID를 사용하여 규칙에 따라 공격 표면 감소 규칙을 구성할 수 있습니다.

- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)
- [Configuration Manager CB 1802](/configmgr/core/servers/manage/updates)
- [Microsoft Endpoint Manager CB 1710](/configmgr/core/servers/manage/updates)
- [System Center Configuration Manager(SCCM) CB 1710](/configmgr/core/servers/manage/updates) <br>_이제 SCCM이 Microsoft Endpoint Configuration Manager._

## <a name="per-rule-descriptions"></a>규칙 설명당

### <a name="block-abuse-of-exploited-vulnerable-signed-drivers"></a>악용된 취약한 서명된 드라이버의 남용 차단

이 규칙은 응용 프로그램이 디스크에 취약한 서명된 드라이버를 작성하지 못하게 합니다. 와일드에서 취약한 서명된 드라이버는 커널에 액세스하기에 충분한 권한이 있는 로컬 응용 프로그램에 \-  \- 의해 악용될 수 있습니다. 취약한 서명된 드라이버를 사용하면 공격자가 보안 솔루션을 사용하지 않도록 설정하거나 우회할 수 있습니다. 결과적으로 시스템 손상이 일어날 수 있습니다.

**악용된** 취약한 드라이버 남용 차단 규칙은 시스템에 이미 있는 드라이버가 로드되는 것을 차단하지 않습니다.

> [!NOTE]
>
> MEM OMA-URI를 사용하여 이 규칙을 구성할 수 있습니다. 사용자 지정 규칙을 구성하는 내용은 [MEM OMA-URI를](enable-attack-surface-reduction.md#mem) 참조합니다.
>
> PowerShell을 사용하여 이 규칙을 [구성할 수 있습니다.](enable-attack-surface-reduction.md#powershell)
>
> 드라이버를 검사하기 위해 이 웹 사이트를 사용하여 분석을 위해 [드라이버를 제출합니다.](https://www.microsoft.com/wdsi/driversubmission)

Intune 이름: `Block abuse of exploited vulnerable signed drivers`

GUID:  `56a863a9-875e-4185-98a7-b882c64b5ce5`

<!-- Hide this intro with no subsequent list items
Advanced hunting action type:
-->

### <a name="block-adobe-reader-from-creating-child-processes"></a>Adobe Reader에서 하위 프로세스를 만들지 차단

이 규칙은 Adobe Reader가 프로세스를 만들지 못하게 차단하여 공격을 방지합니다.

소셜 엔지니어링 또는 악용을 통해 맬웨어는 페이로드를 다운로드 및 시작하고 Adobe Reader를 중단할 수 있습니다. Adobe Reader에서 자식 프로세스가 생성되지 않도록 차단하면 벡터로 사용하려는 맬웨어가 확산되지 않습니다.

Intune 이름: `Process creation from Adobe Reader (beta)`

Configuration Manager 이름: 아직 사용할 수 없습니다.

GUID: `7674ba52-37eb-4a4f-a9a1-f0f9a1619a2c`

고급 헌팅 작업 유형:

- AsrAdobeReaderChildProcessAudited
- AsrAdobeReaderChildProcessBlocked

### <a name="block-all-office-applications-from-creating-child-processes"></a>모든 Office 응용 프로그램에서 자식 프로세스를 만들지 차단

이 규칙은 Office 프로세스 만들기를 차단합니다. Office 앱에는 Word, Excel, PowerPoint, OneNote 및 Access가 포함됩니다.

악의적인 자식 프로세스를 만드는 것은 일반적인 맬웨어 전략입니다. 벡터로 Office 악용하는 맬웨어는 VBA 매크로를 실행하고 코드를 악용하여 더 많은 페이로드를 다운로드하고 실행하려고 합니다. 그러나 일부 합법적인 업무(LINE-OF-BUSINESS) 응용 프로그램에서는 자식 프로세스를 무해한 용도로 생성할 수도 있습니다. 명령 프롬프트를 만들거나 PowerShell을 사용하여 레지스트리 설정을 구성하는 등의 경우

Intune 이름: `Office apps launching child processes`

Configuration Manager 이름: `Block Office application from creating child processes`

GUID: `d4f940ab-401b-4efc-aadc-ad5f3c50688a`

고급 헌팅 작업 유형:

- AsrOfficeChildProcessAudited
- AsrOfficeChildProcessBlocked

### <a name="block-credential-stealing-from-the-windows-local-security-authority-subsystem"></a>로컬 보안 기관 하위 Windows 자격 증명 도용 차단

이 규칙은 LSASS(Local Security Authority Subsystem Service)를 잠가 자격 증명 도용을 방지하는 데 도움이 됩니다.

LSASS는 Windows 인증합니다. Microsoft Defender Credential Guard는 Windows 10 LSASS에서 자격 증명을 추출하려고 시도하지 않습니다. 그러나 일부 조직에서는 사용자 지정 스마트 카드 드라이버 또는 LSA(Local Security Authority)로 로드되는 다른 프로그램과의 호환성 문제로 인하여 모든 컴퓨터에서 Credential Guard를 사용하도록 설정할 수 없습니다. 이러한 경우 공격자는 Mimikatz와 같은 해킹 도구를 사용하여 LSASS에서 지우기 암호 및 NTLM 해시를 스크랩할 수 있습니다.

> [!NOTE]
> 일부 앱에서는 코드가 실행 중인 모든 프로세스를 열기하고 모든 사용 권한으로 열려고 시도합니다. 이 규칙은 앱의 프로세스 열기 작업을 거부하고 보안 이벤트 로그에 세부 정보를 기록합니다. 이 규칙은 노이즈를 많이 생성할 수 있습니다. LSASS를 열기만 하지만 기능에는 실질적인 영향을 미치는 앱이 있는 경우 제외 목록에 앱을 추가할 필요가 없습니다. 이 이벤트 로그 항목 자체는 악의적인 위협을 나타낼 필요는 없습니다.

Intune 이름: `Flag credential stealing from the Windows local security authority subsystem`

Configuration Manager 이름: `Block credential stealing from the Windows local security authority subsystem`

GUID: `9e6c4e1f-7d60-472f-ba1a-a39ef669e4b2`

고급 헌팅 작업 유형:

- AsrLsassCredentialTheftAudited
- AsrLsassCredentialTheftBlocked

### <a name="block-executable-content-from-email-client-and-webmail"></a>전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠 차단

이 규칙은 Microsoft Outlook 응용 프로그램 또는 Outlook.com 및 기타 인기 있는 웹 메일 공급자에서 연 전자 메일에서 다음 파일 형식이 시작되지 Outlook 차단합니다.

- 실행 파일(예: .exe, .dll 또는 .scr)
- 스크립트 파일(예: PowerShell .ps, Visual Basic .vbs 또는 JavaScript .js 파일)

Intune 이름: `Execution of executable content (exe, dll, ps, js, vbs, etc.) dropped from email (webmail/mail client) (no exceptions)`

Microsoft Endpoint Manager 이름:`Block executable content from email client and webmail`

GUID: `be9ba2d9-53ea-4cdc-84e5-9b1eeee46550`

고급 헌팅 작업 유형:

- AsrExecutableEmailContentAudited
- AsrExecutableEmailContentBlocked

> [!NOTE]
> 전자 **메일 클라이언트 및 웹** 메일에서 실행 가능한 콘텐츠 차단 규칙에는 사용하는 응용 프로그램에 따라 다음과 같은 대체 설명이 있습니다.
>
> - Intune(구성 프로필): 전자 메일(webmail/mail client)에서 삭제된 실행 가능한 콘텐츠(예: dll, ps, js, vbs 등)의 실행입니다(예외 없음).
> - Endpoint Manager: 전자 메일 및 웹 메일 클라이언트에서 실행 가능한 콘텐츠 다운로드를 차단합니다.
> - 그룹 정책: 전자 메일 클라이언트 및 웹 메일에서 실행 가능한 콘텐츠를 차단합니다.

### <a name="block-executable-files-from-running-unless-they-meet-a-prevalence-age-or-trusted-list-criterion"></a>실행 파일이 보전, 보존 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단

이 규칙은 다음 조건이 충족되지 않는 한 .exe, .dll 또는 .scr과 같은 실행 파일이 시작되지 못하게 차단합니다.

- Prevalence: The executable files are found on more than 1,000 endpoints
- 사용 시간: 실행 파일이 24시간 이상 전에 릴리스되었습니다.
- 위치: 실행 파일이 신뢰할 수 있는 목록 또는 제외 목록에 포함됩니다.

파일이 악의적인 경우 처음에 명확하지 않을 수 있는 것으로 보아서, 트러블되지 않았거나 알 수 없는 실행 파일을 실행하는 것은 위험할 수 있습니다.

> [!IMPORTANT]
> 이 규칙을 [사용하려면](/windows/security/threat-protection/microsoft-defender-antivirus/enable-cloud-protection-microsoft-defender-antivirus) 클라우드 제공 보호를 사용하도록 설정해야 합니다.
>
> GUID로 **보전,** 보존 기간 또는 신뢰할 수 있는 목록 기준을 충족하지 않는 한 실행 파일이 실행되지 못하게 차단 규칙은 Microsoft가 소유하며 관리자가 `01443614-cd74-433a-b99e-2ecdc07bfc25` 지정하지 않습니다. 이 규칙은 클라우드 제공 보호를 사용하여 신뢰할 수 있는 목록을 정기적으로 업데이트합니다.
>
> 개별 파일 또는 폴더(폴더 경로 또는 정식 리소스 이름을 사용하여)를 지정할 수 있지만 적용할 규칙이나 제외를 지정할 수 없습니다.

Intune 이름: `Executables that don't meet a prevalence, age, or trusted list criteria`

Configuration Manager 이름: `Block executable files from running unless they meet a prevalence, age, or trusted list criteria`

GUID: `01443614-cd74-433a-b99e-2ecdc07bfc25`

고급 헌팅 작업 유형:

- AsrUntrustedExecutableAudited
- AsrUntrustedExecutableBlocked

### <a name="block-execution-of-potentially-obfuscated-scripts"></a>잠재적으로 난치될 수 있는 스크립트의 실행 차단

이 규칙은 난처한 스크립트 내에서 의심스러운 속성을 검색합니다.

스크립트 난동은 맬웨어 작성자와 합법적인 응용 프로그램이 지적 재산을 숨기거나 스크립트 로드 시간을 줄이는 데 사용하는 일반적인 기술입니다. 또한 맬웨어 작성자는 난독을 사용하여 악의적인 코드를 읽기 어렵게 하여 사람 및 보안 소프트웨어에 의해 가려질 수 없습니다.

Intune 이름: `Obfuscated js/vbs/ps/macro code`

Configuration Manager 이름: `Block execution of potentially obfuscated scripts`

GUID: `5beb7efe-fd9a-4556-801d-275e5ffc04cc`

고급 헌팅 작업 유형:

- AsrObfuscatedScriptAudited
- AsrObfuscatedScriptBlocked

### <a name="block-javascript-or-vbscript-from-launching-downloaded-executable-content"></a>JavaScript 또는 VBScript에서 다운로드한 실행 콘텐츠 시작 차단

이 규칙은 스크립트가 잠재적으로 악의적인 다운로드 콘텐츠를 시작하지 못하게 합니다. JavaScript 또는 VBScript로 작성된 맬웨어는 종종 다운로드자 역할을 하여 인터넷에서 다른 맬웨어를 페치하고 실행합니다.

일반적인 것은 아니며, 업무용 응용 프로그램에서는 스크립트를 사용하여 설치 관리자를 다운로드하고 실행하기도 합니다.

Intune 이름: `js/vbs executing payload downloaded from Internet (no exceptions)`

Configuration Manager 이름: `Block JavaScript or VBScript from launching downloaded executable content`

GUID: `d3e037e1-3eb8-44c8-a917-57927947596d`

고급 헌팅 작업 유형:

- AsrScriptExecutableDownloadAudited
- AsrScriptExecutableDownloadBlocked

### <a name="block-office-applications-from-creating-executable-content"></a>응용 Office 콘텐츠 만들기 차단

이 규칙은 word, Excel 및 PowerPoint 등의 Office 앱이 악성 코드가 디스크에 기록되지 않도록 차단하여 잠재적으로 악의적인 실행 콘텐츠를 만들지 못하게 합니다.

벡터로 Office 악용하는 맬웨어는 악의적인 구성 요소를 Office 디스크에 저장하려고 할 수 있습니다. 이러한 악성 구성 요소는 컴퓨터 재부팅에서 유지되고 시스템에서 지속됩니다. 따라서 이 규칙은 일반적인 지속성 기술에 대해 방어합니다.

Intune 이름: `Office apps/macros creating executable content`

SCCM 이름: `Block Office applications from creating executable content`

GUID: `3b576869-a4ec-4529-8536-b80a7769e899`

고급 헌팅 작업 유형:

- AsrExecutableOfficeContentAudited
- AsrExecutableOfficeContentBlocked

### <a name="block-office-applications-from-injecting-code-into-other-processes"></a>응용 Office 코드 삽입 차단

이 규칙은 앱을 다른 프로세스로 Office 코드 삽입 시도를 차단합니다.

공격자는 앱의 Office 사용하여 코드 삽입을 통해 악성 코드를 다른 프로세스로 마이그레이션하려고 시도할 수 있으므로 코드가 깔끔한 프로세스로 악의적으로 처리될 수 있습니다.

코드 삽입을 사용하는 데 알려진 합법적인 비즈니스 목적이 없습니다.

이 규칙은 Word, Excel 및 PowerPoint.

Intune 이름: `Office apps injecting code into other processes (no exceptions)`

Configuration Manager 이름: `Block Office applications from injecting code into other processes`

GUID: `75668c1f-73b5-4cf0-bb93-3ecf5cb7cc84`

고급 헌팅 작업 유형:

- AsrOfficeProcessInjectionAudited
- AsrOfficeProcessInjectionBlocked

### <a name="block-office-communication-application-from-creating-child-processes"></a>통신 Office 응용 프로그램에서 자식 프로세스를 만들지 차단

이 규칙은 Outlook 자식 프로세스를 만들지 못하게 하지만 합법적인 Outlook 합니다.

이 규칙은 사회 엔지니어링 공격으로부터 보호하고 코드 악용을 통해 보안상 취약성을 악용하지 Outlook. 또한 사용자의 자격 [Outlook](https://blogs.technet.microsoft.com/office365security/defending-against-rules-and-forms-injection/) 공격자가 사용할 수 있는 규칙 및 양식 악용으로부터 보호합니다.

> [!NOTE]
> 이 규칙은 규칙에 따라 DLP 정책 팁과 도구 Outlook. 이 규칙은 Outlook Outlook.com에만 적용됩니다.

Intune 이름: `Process creation from Office communication products (beta)`

Configuration Manager 이름: 사용할 수 없습니다.

GUID: `26190899-1602-49e8-8b27-eb1d0a1ce869`

고급 헌팅 작업 유형:

- AsrOfficeCommAppChildProcessAudited
- AsrOfficeCommAppChildProcessBlocked

### <a name="block-persistence-through-wmi-event-subscription"></a>WMI 이벤트 구독을 통한 지속성 차단

이 규칙은 맬웨어가 WMI를 부인하여 디바이스에서 지속성에 이를 수 없습니다.

> [!IMPORTANT]
> 파일 및 폴더 제외는 이 공격 표면 축소 규칙에 적용되지 않습니다.

파일 없는 위협은 다양한 방법을 사용하여 숨김을 유지하여 파일 시스템에서 볼 수 없는 것을 방지하고 주기적인 실행 제어를 얻습니다. 일부 위협은 WMI 리포지토리 및 이벤트 모델을 남용하여 숨길 수 있습니다.

Intune 이름: 사용할 수 없습니다.

Configuration Manager 이름: 사용할 수 없습니다.

GUID: `e6db77e5-3df2-4cf1-b95a-636979351e5b`

고급 헌팅 작업 유형:

- AsrPersistenceThroughWmiAudited
- AsrPersistenceThroughWmiBlocked

### <a name="block-process-creations-originating-from-psexec-and-wmi-commands"></a>PSExec 및 WMI 명령에서 시작된 프로세스 생성 차단

이 규칙은 [PsExec](/sysinternals/downloads/psexec) 및 [WMI를](/windows/win32/wmisdk/about-wmi) 통해 만든 프로세스의 실행을 차단합니다. PsExec과 WMI 모두 코드를 원격으로 실행할 수 있으므로 맬웨어가 명령 및 제어 목적으로 이 기능을 남용하거나 조직의 네트워크 전체에 감염을 전파할 위험이 있습니다.

> [!WARNING]
> [Intune](/intune) 또는 다른 MDM 솔루션으로 장치를 관리하는 경우 이 규칙만 사용 이 규칙은 Configuration Manager 클라이언트가 올바르게 Microsoft Endpoint Configuration Manager WMI 명령을 차단하기 때문에 이 규칙은 관리자를 [통해](/configmgr) 관리와 비호환합니다.

Intune 이름: `Process creation from PSExec and WMI commands`

Configuration Manager 이름: 해당되지 않습니다.

GUID: `d1e49aac-8f56-4280-b9ba-993a6d77406c`

고급 헌팅 작업 유형:

- AsrPsexecWmiChildProcessAudited
- AsrPsexecWmiChildProcessBlocked

### <a name="block-untrusted-and-unsigned-processes-that-run-from-usb"></a>USB에서 실행된 무단 및 사인되지 않은 프로세스 차단

이 규칙을 사용하여 관리자는 SD 카드를 포함하여 USB 이동식 드라이브에서 사인되지 않은 실행 파일 또는 트러블된 실행 파일을 실행하지 못하게 할 수 있습니다. 차단된 파일 형식에는 실행 파일(예: .exe, .dll 또는 .scr)이 포함됩니다.

Intune 이름: `Untrusted and unsigned processes that run from USB`

Configuration Manager 이름: `Block untrusted and unsigned processes that run from USB`

GUID: `b2b3f03d-6a65-4f7b-a9c7-1c7ef74a9ba4`

고급 헌팅 작업 유형:

- AsrUntrustedUsbProcessAudited
- AsrUntrustedUsbProcessBlocked

### <a name="block-win32-api-calls-from-office-macros"></a>매크로에서 Win32 API Office 차단

이 규칙은 VBA 매크로가 Win32 API를 호출하지 못하게 합니다.

Office VBA는 Win32 API 호출을 가능하게 합니다. 맬웨어는 [Win32 API를](https://www.microsoft.com/security/blog/2018/09/12/office-vba-amsi-parting-the-veil-on-malicious-macros/) 호출하여 디스크에 직접 아무것도 쓰지 않고 악성 셸 코드를 시작하는 등 이 기능을 남용할 수 있습니다. 대부분의 조직에서는 다른 방법으로 매크로를 사용하는 경우에도 매일 작동할 때 Win32 API를 호출하는 기능을 사용하지 않습니다.

지원되는 운영 체제:

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709)
- [Windows 서버, 버전 1809](/windows-server/get-started/whats-new-in-windows-server-1809)
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)
- [Configuration Manager CB 1710](/configmgr/core/servers/manage/updates)

Intune 이름: `Win32 imports from Office macro code`

Configuration Manager 이름: `Block Win32 API calls from Office macros`

GUID: `92e97fa1-2edf-4476-bdd6-9dd0b4dddc7b`

고급 헌팅 작업 유형:

- AsrOfficeMacroWin32ApiCallsAudited
- AsrOfficeMacroWin32ApiCallsBlocked

### <a name="use-advanced-protection-against-ransomware"></a>랜섬웨어에 대한 고급 보호 사용

이 규칙은 랜섬웨어에 대한 추가 보호 계층을 제공합니다. 클라이언트와 클라우드추론을 모두 사용하여 파일이 랜섬웨어와 같은지 여부를 판단합니다. 이 규칙은 다음 특성 중 하나 이상이 있는 파일을 차단하지 않습니다.

- 파일이 Microsoft 클라우드에서 이미 손상되지 않은 것으로 발견된 경우
- 파일이 유효한 서명된 파일입니다.
- 이 파일은 랜섬웨어로 간주되지 않을 정도로 보전됩니다.

규칙은 랜섬웨어를 방지하기 위해 신중하게 진행되는 경향이 있습니다.

> [!NOTE]
> 이 규칙을 [사용하려면](enable-cloud-protection-microsoft-defender-antivirus.md) 클라우드 제공 보호를 사용하도록 설정해야 합니다.

Intune 이름: `Advanced ransomware protection`

Configuration Manager 이름: `Use advanced protection against ransomware`

GUID: `c1db55ab-c21a-4637-bb3f-a12568109d35`

고급 헌팅 작업 유형:

- AsrRansomwareAudited
- AsrRansomwareBlocked
