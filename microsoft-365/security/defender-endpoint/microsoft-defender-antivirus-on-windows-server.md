---
title: Windows Server의 Microsoft Defender 바이러스 백신
description: Microsoft Defender 바이러스 백신 Server 2019 및 Windows Server 2016 Server 2019 및 Windows 2022에서 Windows 구성하는 방법을 학습합니다.
keywords: windows defender, server, scep, system center endpoint protection, server 2016, current branch, server 2012
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.reviewer: pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 10/13/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 8f5ae71ecc602a7bc588ff62036be20b883087db
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335481"
---
# <a name="microsoft-defender-antivirus-on-windows-server"></a>Windows Server의 Microsoft Defender 바이러스 백신

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

Microsoft Defender 바이러스 백신 서버의 다음 버전/버전에서 사용할 Windows 있습니다.

- Windows Server 2022
- Windows Server 2019
- Windows 서버, 버전 1803 이상
- Windows Server 2016
- Windows Server 2012 R2(끝점용 Microsoft Defender 필요)

경우에 따라 Microsoft Defender 바이러스 백신 라고도 *Endpoint Protection.* 그러나 보호 엔진은 동일합니다. Microsoft Defender 바이러스 백신 구성 및 관리는 거의 동일하기는 [](microsoft-defender-antivirus-windows.md)하지만 Windows 10 Server에서 몇 가지 주요 Windows 있습니다.

- Windows 서버 역할에 [](configure-server-exclusions-microsoft-defender-antivirus.md) 따라 자동 제외가 적용됩니다.

- Windows 서버에서 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션을 실행하는 경우 Microsoft Defender 바이러스 백신 모드 또는 비활성화 모드로 자동 전환되지 않습니다. 그러나 수동 또는 Microsoft Defender 바이러스 백신 모드로 설정할 수 있습니다.

## <a name="setting-up-microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에서 Windows 설정

서버 플랫폼에서 Microsoft Defender 바이러스 백신 설정하고 실행하는 프로세스에는 다음과 같은 몇 가지 단계가 포함됩니다.

1. [인터페이스를 사용하도록 설정합니다.](#enable-the-user-interface-on-windows-server)
2. [를 Microsoft Defender 바이러스 백신.](#install-microsoft-defender-antivirus-on-windows-server)
3. [이 Microsoft Defender 바이러스 백신 중인지 확인](#verify-microsoft-defender-antivirus-is-running)
4. [맬웨어 방지 보안 인텔리전스를 업데이트합니다.](#update-antimalware-security-intelligence)
5. (필요한 경우) [샘플 제출](#submit-samples).
6. (필요한 경우) [자동 제외를 구성합니다.](#configure-automatic-exclusions)
7. (필요한 경우만 해당) Windows [수동 모드로 설정](#passive-mode-and-windows-server)

## <a name="enable-the-user-interface-on-windows-server"></a>서버의 사용자 인터페이스 Windows 사용

기본적으로 Microsoft Defender 바이러스 백신 서버에서 설치 및 Windows 있습니다. GUI(사용자 인터페이스)가 기본적으로 설치되지만 GUI가 필요하지 않은 경우도 있습니다. PowerShell, 그룹 정책 또는 기타 방법을 사용하여 그룹 정책을 관리할 Microsoft Defender 바이러스 백신.

GUI가 서버에 설치되어 있지 않은 경우 역할 및 기능 추가  마법사 또는 PowerShell cmdlet을 설치합니다.



> [!NOTE]
> 이 옵션은 R2에서 사용할 Windows Server 2012 없습니다. 자세한 내용은 [끝점용 Microsoft Defender를 설치하는 옵션을 참조하세요.](configure-server-endpoints.md#options-to-install-microsoft-defender-for-endpoint)

### <a name="turn-on-the-gui-using-the-add-roles-and-features-wizard"></a>역할 및 기능 추가 마법사를 사용하여 GUI 켜기

1. 역할 및 기능 추가 마법사를 사용하여 [역할,](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 서비스 및 기능 설치 및 역할 및 기능 추가 마법사 사용을 **참조합니다.**

2. 마법사의 기능  단계에 도착하면 Windows Defender **에서** 마법사의 **GUI를 Windows Defender.**

   이 Windows Server 2016 역할 및 기능 추가 **마법사는** 다음과 같습니다.

   ![사용자 설정 옵션에 대한 GUI를 보여 Windows Defender 추가합니다.](images/server-add-gui.png)

   Windows Server 2019 및 Windows Server 2022에서  역할 추가 및 기능 마법사도 비슷합니다.

### <a name="turn-on-the-gui-using-powershell"></a>PowerShell을 사용하여 GUI 켜기

다음 PowerShell cmdlet은 인터페이스를 사용하도록 설정합니다.

```PowerShell
Install-WindowsFeature -Name Windows-Defender-GUI
```

## <a name="install-microsoft-defender-antivirus-on-windows-server"></a>Microsoft Defender 바이러스 백신 서버에 Windows 설치

Microsoft Defender 바이러스 백신 서버에 Windows 설치하거나 다시 설치해야 하는 경우 역할 및 기능 추가 마법사  또는 PowerShell을 사용하여 이 작업을 할 수 있습니다.

### <a name="use-the-add-roles-and-features-wizard-to-install-microsoft-defender-antivirus"></a>역할 및 기능 추가 마법사를 사용하여 역할 및 기능 Microsoft Defender 바이러스 백신

1. 이 문서 [를 참조하고](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#install-roles-role-services-and-features-by-using-the-add-roles-and-features-wizard)역할 및 기능 추가 **마법사를 사용하세요.**

2. 마법사의 **기능** 단계에 도착하면 Microsoft Defender 바이러스 백신 선택합니다. 또한 선택 **옵션에 대한 WINDOWS DEFENDER** 선택합니다.

### <a name="use-powershell-to-install-microsoft-defender-antivirus"></a>PowerShell을 사용하여 설치 Microsoft Defender 바이러스 백신

PowerShell을 사용하여 Microsoft Defender 바이러스 백신 cmdlet을 실행합니다.

```PowerShell
Install-WindowsFeature -Name Windows-Defender
```

맬웨어 방지 엔진에 대한 이벤트 Microsoft Defender 바이러스 백신 [Microsoft Defender AV](troubleshoot-microsoft-defender-antivirus.md)이벤트에서 찾을 수 있습니다.

## <a name="verify-microsoft-defender-antivirus-is-running"></a>실행 Microsoft Defender 바이러스 백신 확인

설치 Microsoft Defender 바이러스 백신 다음 단계는 실행 중인지 확인하는 것입니다. Windows Server 끝점에서 다음 PowerShell cmdlet을 실행합니다.

```PowerShell
Get-Service -Name windefend
```

방화벽 보호가 켜져 있는지 확인하기 위해 다음 PowerShell cmdlet을 실행합니다.

```PowerShell
Get-Service -Name mpssvc
```

PowerShell 대신 명령 프롬프트를 사용하여 명령 프롬프트가 Microsoft Defender 바이러스 백신 있습니다. 이를 위해 명령 프롬프트에서 다음 명령을 실행합니다.

```console
sc query Windefend
```

명령은 `sc query` Microsoft Defender 바이러스 백신 반환합니다. 실행 Microsoft Defender 바이러스 백신 값이 `STATE` `RUNNING` 표시됩니다.

## <a name="update-antimalware-security-intelligence"></a>맬웨어 방지 보안 인텔리전스 업데이트

업데이트된 맬웨어 방지 보안 인텔리전스를 사용하려면 맬웨어 방지 Windows 실행해야 합니다. WSUS(Windows Server Update Services)와 같은 업데이트 관리 서비스를 사용하는 경우 Microsoft Defender 바이러스 백신 보안 인텔리전스에 대한 업데이트가 관리하는 컴퓨터에 대해 승인되어 있는지 확인합니다.

기본적으로 Windows 업데이트는 Windows Server 2019 또는 Windows Server 2022 또는 Windows Server 2016. 다음 방법 중 하나를 사용하여 이 구성을 변경할 수 있습니다.

<br/><br/>

| 방법 | 설명 |
|---|---|
| **Windows 업데이트** | **업데이트를 자동으로 설치하면** 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 설치됩니다. <br/><br/> **업데이트를 다운로드하지만** 설치할지 여부를 선택할 수 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하고 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다. |
| **그룹 정책** | 관리 **템플릿\Windows 구성 요소\Windows** 업데이트\자동 업데이트 구성 경로의 그룹 정책에서 사용할 수 있는 설정을 사용하여 Windows 업데이트를 설정하고 관리할 수 있습니다. |
| **AUOptions** 레지스트리 키 | 다음 두 값을 사용하면 Windows 업데이트에서 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있습니다. <br/><br/> **4**  -  **자동으로 업데이트를 설치합니다.** 이 값을 설정하면 보안 인텔리전스 업데이트를 포함하여 모든 Windows Defender 자동으로 설치됩니다. <br/><br/> **3**  -  **업데이트를 다운로드하지만 설치할지 여부를 선택할 수 있습니다.** 이 값을 Windows Defender 보안 인텔리전스 업데이트를 자동으로 다운로드하여 설치할 수 있지만 다른 업데이트는 자동으로 설치되지 않습니다. |

맬웨어로부터 보호를 유지하려면 다음 서비스를 사용하도록 설정하는 것이 좋습니다.

- Windows 오류 보고 서비스
- Windows 업데이트 서비스

다음 표에는 서비스 및 종속 Microsoft Defender 바이러스 백신 대한 서비스가 나열되어 있습니다.

<br/><br/>


| 서비스 이름 | 파일 위치 | 설명 |
|---|---|---|
| Windows Defender 서비스(WinDefend) | `C:\Program Files\Windows Defender\MsMpEng.exe` | 이 서비스는 Microsoft Defender 바이러스 백신 실행해야 하는 기본 서비스입니다.|
| Windows 오류 보고 서비스(Wersvc) | `C:\WINDOWS\System32\svchost.exe -k WerSvcGroup` | 이 서비스는 오류 보고서를 Microsoft로 다시 전송합니다. |
| Windows Defender 방화벽(MpsSvc) | `C:\WINDOWS\system32\svchost.exe -k LocalServiceNoNetwork` | 방화벽 서비스를 사용하도록 Windows Defender 것이 좋습니다. |
| Windows 업데이트(Wuauserv) | `C:\WINDOWS\system32\svchost.exe -k netsvcs`| Windows 보안 인텔리전스 업데이트 및 맬웨어 방지 엔진 업데이트를 다운로드하려면 업데이트가 필요합니다. |

## <a name="submit-samples"></a>샘플 제출

샘플 제출을 통해 Microsoft는 잠재적으로 악성 소프트웨어의 샘플을 수집할 수 있습니다. Microsoft 연구원들은 이러한 샘플을 사용하여 의심스러운 활동을 분석하고 업데이트된 맬웨어 방지 보안 인텔리전스를 생성합니다. 파일 및 파일 파일과 같은 .exe 실행 파일을 .dll 있습니다. 문서 및 PDF 파일과 같은 개인 데이터가 Microsoft Word 수집하지 않습니다.

### <a name="submit-a-file"></a>파일 제출

1. 제출 [가이드를 검토합니다.](/windows/security/threat-protection/intelligence/submission-guide)
2. 샘플 [제출 포털 을 방문하여](https://www.microsoft.com/wdsi/filesubmission)파일을 제출합니다.

### <a name="enable-automatic-sample-submission"></a>자동 샘플 제출 사용

자동 샘플 제출을 사용하도록 설정하려면 Windows PowerShell 콘솔을 시작하고 다음 설정 중 하나에 따라 **SubmitSamplesConsent** 값 데이터를 설정하십시오.

<br/><br/>

|설정|설명|
|---|---|
| **0**  -  **항상 프롬프트** | Microsoft Defender 바이러스 백신 서비스에서 필요한 모든 파일의 제출을 확인하라는 메시지를 제공합니다. 이 설정은 Microsoft Defender 바이러스 백신 기본 설정이지만 Windows Server 2016 또는 2019 또는 Windows Server 2022에 GUI가 없는 설치에는 권장되지 않습니다. |
| **1**   -  **안전한 샘플 자동 보내기** | Microsoft Defender 바이러스 백신 서비스는 "안전"으로 표시된 모든 파일을 전송하고 나머지 파일을 묻는 메시지를 제공합니다. |
| **2**  -  **보내지 않는 경우** | Microsoft Defender 바이러스 백신 서비스는 메시지를 표시하지 않습니다. 또한 어떤 파일도 보내지 않습니다. |
| **3**  -  **모든 샘플 자동 보내기** | Microsoft Defender 바이러스 백신 서비스는 확인 메시지를 표시하지 않고 모든 파일을 전송합니다. |

> [!NOTE]
> 이 옵션은 R2에서 사용할 Windows Server 2012 없습니다. 


## <a name="configure-automatic-exclusions"></a>자동 제외 구성

보안 및 성능을 보장하기 위해 Microsoft Defender 바이러스 백신 또는 2019 또는 Windows Server 2016 Server 2022에서 Microsoft Defender 바이러스 백신 사용할 때 설치하는 역할 및 기능에 따라 특정 제외가 Windows 추가됩니다.

Microsoft Defender 바이러스 백신 서버에서 제외 Windows [참조합니다.](configure-server-exclusions-microsoft-defender-antivirus.md)

## <a name="passive-mode-and-windows-server"></a>수동 모드 및 Windows 서버

Windows Server에서 Microsoft가 아닌 바이러스 백신 제품을 기본 바이러스 백신 솔루션으로 사용하는 경우 Microsoft Defender 바이러스 백신 모드 또는 비활성화 모드로 설정해야 합니다.

자세한 내용은 [Install Microsoft Defender 바이러스 백신 on Windows 참조하십시오.](microsoft-defender-antivirus-on-windows-server.md#install-microsoft-defender-antivirus-on-windows-server)


### <a name="set-microsoft-defender-antivirus-to-passive-mode-using-a-registry-key"></a>레지스트리 Microsoft Defender 바이러스 백신 수동 모드로 설정

다음 레지스트리 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다.
- 경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 이름: `ForceDefenderPassiveMode`
- 유형: `REG_DWORD`
- 값: `1`

### <a name="disable-microsoft-defender-antivirus-using-the-remove-roles-and-features-wizard"></a>역할 Microsoft Defender 바이러스 백신 제거 마법사를 사용하여 사용자 설정을 사용하지 않도록 설정

1. 역할, 역할 서비스 또는 기능 설치 또는 제거 및 역할 및 기능 **제거 마법사 사용을 참조합니다.** [](/windows-server/administration/server-manager/install-or-uninstall-roles-role-services-or-features#remove-roles-role-services-and-features-by-using-the-remove-roles-and-features-wizard)

2. 마법사의 **기능** 단계에 도착하면 기능 Windows Defender **선택을 취소합니다.**

    Windows Defender 기능  섹션에서 Windows Defender 선택을  취소하면 에 대한 인터페이스 옵션 GUI를 제거하라는 **메시지가 Windows Defender.**

    Microsoft Defender 바이러스 백신 인터페이스 없이도 정상적으로 실행되지만 핵심 사용자 인터페이스 기능을 사용하지 않도록 설정한 경우 사용자 인터페이스를 사용할 **Windows Defender** 없습니다.

### <a name="turn-off-the-microsoft-defender-antivirus-user-interface-using-powershell"></a>PowerShell을 Microsoft Defender 바이러스 백신 사용자 인터페이스 끄기

GUI를 Microsoft Defender 바이러스 백신 다음 PowerShell cmdlet을 사용 합니다.

```PowerShell
Uninstall-WindowsFeature -Name Windows-Defender-GUI
```

### <a name="are-you-using-windows-server-2012-r2-or-windows-server-2016"></a>R2 또는 Windows Server 2012 사용 Windows Server 2016?

이제 R2 및 Microsoft Defender 바이러스 백신 수동 모드에서 Windows Server 2012 실행할 수 Windows Server 2016. 자세한 내용은 [끝점용 Microsoft Defender를 설치하는 옵션을 참조하세요.](configure-server-endpoints.md#options-to-install-microsoft-defender-for-endpoint)

<br/><br/>

| 절차 | 설명 |
|---|---|
| 그룹 Microsoft Defender 바이러스 백신 사용하지 않도록 설정 | 로컬 그룹 정책 편집기에서 Windows Defender **로** 이동한 다음 끄기를 **Windows Defender 바이러스 백신.** |
| 레지스트리 Microsoft Defender 바이러스 백신 사용하지 않도록 설정 | [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 레지스트리 키를 사용 하 고 로 이동 하 고 라는 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` DWORD 항목을 설정 또는 만들 수 `DisableAntiSpyware` 있습니다. 해당 값을 로 설정하여 레지스트리 키의 값을 `1` *true로 설정합니다.* |
| PowerShell을 Microsoft Defender 바이러스 백신 사용하지 않도록 설정 | 다음 PowerShell cmdlet을 사용 합니다. `Set-MpPreference -DisableRealtimeMonitoring $true` |
| PowerShell을 Microsoft Defender 바이러스 백신 제거 | 다음 PowerShell cmdlet을 사용 합니다. `Uninstall-WindowsFeature -Name Windows-Defender` |


## <a name="see-also"></a>참고 항목

- [Windows의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-windows.md)
- [Microsoft Defender 바이러스 백신 호환성](microsoft-defender-antivirus-compatibility.md)
