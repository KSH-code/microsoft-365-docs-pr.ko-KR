---
title: Microsoft Defender 바이러스 백신 제품과의 호환성
description: 다른 보안 Microsoft Defender 바이러스 백신 운영 체제와의 통합에 대해 자세히 알아보습니다.
keywords: windows defender, 끝점용 defender, 차세대, 바이러스 백신, 호환성, 수동 모드
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: mkaminska, pahuijbr
manager: dansimp
ms.technology: mde
ms.date: 10/26/2021
ms.collection: M365-security-compliance
ms.openlocfilehash: 9ffbeb2b8b1f8095b79ebfce1466ecc4ee559cac
ms.sourcegitcommit: e09ced3e3628bf2ccb84d205d9699483cbb4b3b0
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2021
ms.locfileid: "60882504"
---
# <a name="microsoft-defender-antivirus-compatibility-with-other-security-products"></a>Microsoft Defender 바이러스 백신 제품과의 호환성

**적용 대상:**

- Microsoft Defender 바이러스 백신
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

Microsoft Defender 바이러스 백신 다음 버전의 응용 프로그램을 실행하는 끝점에 Windows.

- Windows 10 이상
- Windows Server 2022
- Windows Server 2019
- Windows 서버, 버전 1803 이상
- Windows Server 2016

Microsoft가 아닌 다른 바이러스 백신/맬웨어 방지 솔루션이 사용될 경우 어떻게 하나요? 다른 바이러스 백신 Microsoft Defender 바이러스 백신 함께 실행할 수 있나요? 답변은 운영 체제와 바이러스 백신 보호와 함께 [끝점용 Microsoft Defender(Endpoint용 Defender)를](microsoft-defender-endpoint.md) 사용하는지 여부와 같은 몇 가지 요인에 따라 결정됩니다.

이 문서에서는 Endpoint용 Defender를 Microsoft Defender 바이러스 백신 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션과 함께 발생하는 문제에 대해 설명합니다.

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 Windows 10 및 11, Windows Server 2022, Windows Server 2019, Windows Server, 버전 1803 이상, Windows Server 2016 및 Windows Server 2012 R2를 실행하는 장치에서만 사용할 수 있습니다.
>
> 이 Windows 8.1 엔터프라이즈 수준의 끝점 바이러스 백신 [](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))보호는 System Center Endpoint Protection 를 통해 관리되는 Microsoft Endpoint Configuration Manager.
>
> Windows Defender 엔터프라이즈 수준 관리를 [](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)제공하지는 Windows 8.1 소비자 Windows Defender 장치도 제공됩니다.

## <a name="antivirus-protection-without-defender-for-endpoint"></a>Endpoint용 Defender가 없는 바이러스 백신 보호

이 섹션에서는 끝점용 Defender에 온보딩되지 않은 끝점에서 Microsoft Defender 바이러스 백신 및 비 Microsoft 바이러스 백신/맬웨어 방지 제품과 함께 발생하는 일에 대해 설명합니다. 다음 표에는 예상할 수 있는 일이 요약된 표가 있습니다.

<br/><br/>

|Windows 버전|기본 바이러스 백신/맬웨어 방지 솔루션|Microsoft Defender 바이러스 백신 상태|
|---|---|---|
|Windows 10 <p> Windows 11|Microsoft Defender 바이러스 백신|활성 모드|
|Windows 10 <p> Windows 11|Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션|비활성화 모드(자동으로 발생)|
|Windows Server 2022 <p> Windows Server 2019<p> Windows 서버, 버전 1803 이상 <p> Windows Server 2016 |Microsoft Defender 바이러스 백신|활성 모드|
|Windows Server 2022<p>Windows Server 2019<p>Windows 서버, 버전 1803 이상 <p> Windows Server 2016 <p>  |Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션|사용 안 하게(수동으로 설정) <sup>[[1](#fn1)]</sup>|

(<a id="fn1">1)</a>Windows Server에서 Microsoft가 아닌 바이러스 백신 제품을 실행하는 경우 그룹 정책을 사용하여 Microsoft Defender 바이러스 백신 해제하거나 [DisableAntiSpyware](/windows-hardware/customize/desktop/unattend/security-malware-windows-defender-disableantispyware) 레지스트리 키를 사용하여 Microsoft Defender 바이러스 백신 사용하지 않도록 설정할 수 있습니다. 레지스트리 키를 사용 하 고 로 이동 하 고 `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender` 이라는 DWORD 항목을 설정하거나 만들 수 `DisableAntiSpyware` 있습니다. 해당 값을 로 설정하고(레지스트리 키의 값을 true로 설정) 기준에 대해 `1` **16진수** 를 선택합니다. 

> [!TIP]
> Microsoft Defender 바이러스 백신 [서버](microsoft-defender-antivirus-on-windows-server.md) 설치에 대한 주요 차이점 및 Windows 관리 옵션은 Windows 참조하세요. 이 Windows Server 2016 에 를 표시하지 *않고* Windows Defender 바이러스 백신 수 *Microsoft Defender 바이러스 백신.*

## <a name="microsoft-defender-antivirus-and-non-microsoft-antivirusantimalware-solutions"></a>Microsoft Defender 바이러스 백신 및 비 Microsoft 바이러스 백신/맬웨어 방지 솔루션

다음 표에는 Microsoft가 아닌 Microsoft Defender 바이러스 백신 맬웨어 방지 솔루션이 함께 사용되거나 끝점용 Microsoft Defender가 없는 경우 발생하는 문제가 요약되어 있습니다. 

| Windows 버전   | 바이러스 백신/맬웨어 방지 솔루션  | 온보더드- <br/> Endpoint용 Defender | Microsoft Defender 바이러스 백신 상태     |
|------|------|-------|-------|
| Windows 10 <p> Windows 11| Microsoft Defender 바이러스 백신 | 예  | 활성 모드 | 
| Windows 10 <p> Windows 11 | Microsoft Defender 바이러스 백신 | 아니요   | 활성 모드 |
| Windows 10 <p> Windows 11  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예  | 수동 모드(자동) |
| Windows 10 <p> Windows 11  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니요   | 비활성화 모드(자동)    |
| Windows Server 2019 <p>Windows 서버, 버전 1803 이상  | Microsoft Defender 바이러스 백신  | 예 |         활성 모드  |
| Windows Server 2019 <p> Windows 서버, 버전 1803 이상   | Microsoft Defender 바이러스 백신 | 아니요  | 활성 모드 |
| Windows Server 2019 <p> Windows 서버, 버전 1803 이상  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예  | Microsoft Defender 바이러스 백신 수동 모드로 설정해야 합니다(수동) <sup> [[2]](#fn2)<sup>  | 
| Windows Server 2019 <p> Windows 서버, 버전 1803 이상  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니요  | Microsoft Defender 바이러스 백신 비활성화해야 합니다(수동으로) <sup> [[3](#fn3)]<sup></sup>  |
| Windows Server 2016 <br><br> Windows Server 2012 R2   | Microsoft Defender 바이러스 백신 | 예 | 활성 모드 |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft Defender 바이러스 백신 | 아니오 | 활성 모드 |
| Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예 | Microsoft Defender 바이러스 백신 수동 모드로 설정해야 합니다(수동) <sup> [[2]](#fn2)<sup> |
|Windows Server 2016 <br><br> Windows Server 2012 R2  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니오 | Microsoft Defender 바이러스 백신 비활성화해야 합니다(수동으로) <sup> [[3](#fn3)]<sup> |

<a id="fn2">(2)</a>Windows Server 2019, Windows Server, 버전 1803 이상, Windows Server 2016 또는 Windows Server 2012 R2에서는 Microsoft가 아닌 바이러스 백신을 설치할 때 Microsoft Defender 바이러스 백신 수동 모드가 자동으로 전환되지 않습니다. product. 이러한 경우 [Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md) 바이러스 백신 제품을 여러 개 설치하여 문제를 방지할 수 있는 수동 모드로 설정하십시오. PowerShell, Microsoft Defender 바이러스 백신 또는 레지스트리 키를 사용하여 수동 모드로 설정할 수 있습니다. 

  다음 레지스트리 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다.
- 경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 이름: `ForceDefenderPassiveMode`
- 유형: `REG_DWORD`
- 값: `1`

 > [!NOTE]
 > 수동 모드가 R2 및 Windows Server 2016 Windows Server 2012 실행되는 끝점에서 작동하려면 해당 끝점을 온보드 서버 [](configure-server-endpoints.md#windows-server-2012-r2-and-windows-server-2016)Windows 사용하세요. 

(<a id="fn3">3</a>) Windows Server 2016 또는 Windows Server 2012 R2에서 Microsoft가 아닌 바이러스 백신 제품을 사용하고 있으며 해당 끝점이 끝점용 Microsoft Defender에 온보딩되지 않은 경우 여러 바이러스 백신으로 인한 문제를 방지하려면 Microsoft Defender 바이러스 백신 수동으로 사용하지 않도록 [설정/제거합니다.](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2012-r2-or-windows-server-2016) 서버에 설치된 제품입니다.

> [!TIP]
> Microsoft Defender 바이러스 백신 [서버](microsoft-defender-antivirus-on-windows-server.md) 설치에 대한 주요 차이점 및 Windows 관리 옵션은 Windows 참조하세요. 이 Windows Server 2016 에 를 표시하지 *않고* Windows Defender 바이러스 백신 수 *Microsoft Defender 바이러스 백신.*

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 Windows 10 및 11, Windows Server 2022, Windows Server 2019, Windows Server, 버전 1803 이상, Windows Server 2016 및 Windows Server 2012 R2를 실행하는 장치에서만 사용할 수 있습니다.
>
> 이 Windows 8.1 엔터프라이즈 수준의 끝점 바이러스 백신 [](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))보호는 System Center Endpoint Protection 를 통해 관리되는 Microsoft Endpoint Configuration Manager.
>
> Windows Defender 엔터프라이즈 수준 관리를 [](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)제공하지는 Windows 8.1 소비자 Windows Defender 장치도 제공됩니다.

Endpoint용 Defender에는 끝점에 설치된 바이러스 백신 보호를 추가로 확장하는 기능이 포함되어 있습니다. 다른 바이러스 백신 솔루션과 함께 Microsoft Defender 바이러스 백신 수 있습니다.

예를 들어 차단 모드의 [끝점](edr-in-block-mode.md) 감지 및 응답(EDR)은 기본 바이러스 백신 제품이 아니어도 Microsoft Defender 바이러스 백신 아티팩트로부터 추가된 보호 기능을 제공합니다. 이러한 기능을 사용하려면 Microsoft Defender 바이러스 백신 모드 또는 활성 모드로 설치 및 실행해야 합니다.

### <a name="requirements-for-microsoft-defender-antivirus-to-run-in-passive-mode"></a>수동 Microsoft Defender 바이러스 백신 실행하기 위한 요구 사항

수동 Microsoft Defender 바이러스 백신 실행하려면 끝점이 다음 요구 사항을 충족해야 합니다.

- 운영 체제: Windows 10 이상입니다. Windows Server 2022, Windows Server 2019 또는 Windows Server, 버전 1803 이상
- Microsoft Defender 바이러스 백신 설치해야 합니다.
- 다른 비 Microsoft 바이러스 백신/맬웨어 방지 제품을 설치하고 기본 바이러스 백신 솔루션으로 사용해야 합니다.
- 끝점은 Endpoint용 Defender에 온보딩되어야 합니다.

## <a name="how-microsoft-defender-antivirus-affects-defender-for-endpoint-functionality"></a>끝점 Microsoft Defender 바이러스 백신 Defender 기능에 미치는 영향

Endpoint용 Defender는 수동 Microsoft Defender 바이러스 백신 수 있는지 여부에 영향을 미치게 됩니다. Microsoft Defender 바이러스 백신 끝점용 Defender의 특정 기능에도 영향을 줄 수 있습니다. 예를 들어 실시간 보호는 활성 또는 Microsoft Defender 바이러스 백신 수동 모드일 때 작동하지만, Microsoft Defender 바이러스 백신 또는 제거되지 않을 때 작동합니다.

이 섹션의 표에는 활성 모드, 수동 모드 또는 비활성화/제거 여부에 따라 Microsoft Defender 바이러스 백신 기능 및 기능이 요약되어 있습니다.

> [!IMPORTANT]
> 다음 표는 정보 전용으로 디자인됩니다. 수동 모드에서 Microsoft Defender 바이러스 백신 사용하는 경우 또는 사후 위반이 감지된 악의적인 아티팩트를 감지하고 수정하는 차단 모드에서 EDR 사용 [](edr-in-block-mode.md)하는 경우 실시간 보호, 클라우드 제공 보호 또는 제한된 주기적 검사와 같은 기능을 해제하지 않습니다.

<br/><br/>

 | 보호 | Microsoft Defender 바이러스 백신 <br/>(*활성 모드*) | Microsoft Defender 바이러스 백신 <br/>(*수동 모드*) | Microsoft Defender 바이러스 백신 <br/>(*사용 안 되거나 제거*) | [차단 모드의 EDR](edr-in-block-mode.md) | 
 |---|---|---|---|---| 
 | [실시간 보호](configure-real-time-protection-microsoft-defender-antivirus.md) | 예 | 아니요 <sup>[[4](#fn4)]</sup> | 아니요 | 아니요 | 
 | [클라우드 제공 보호](enable-cloud-protection-microsoft-defender-antivirus.md) | 예 | 아니요  | 아니요 | 아니요 | 
 | [네트워크 보호](network-protection.md)  | 예 | 아니요 | 아니요 | 아니요 | 
 | [공격 표면 감소 규칙](attack-surface-reduction.md)  | 예 | 아니요 | 아니요  | 아니요 | 
 | [제한된 주기적 검사 가용성](limited-periodic-scanning-microsoft-defender-antivirus.md) | 아니요 | 아니요 | 예 | 아니요 | 
 | [파일 검색 및 검색 정보](review-scan-results-microsoft-defender-antivirus.md) | 예 | 예 | 아니요 | 예 | 
 | [위협 수정](configure-remediation-microsoft-defender-antivirus.md) | 예 | 참고 <sup>참조 [[5](#fn5)]</sup> | 아니오 | 예 | 
 | [보안 인텔리전스 업데이트](manage-updates-baselines-microsoft-defender-antivirus.md) | 예 | 예 | 아니요 | 예 | 

(<a id="fn4">4)</a>일반적으로 Microsoft Defender 바이러스 백신 수동 모드인 경우 실시간 보호는 수동 모드로 설정되어 있는 경우에도 차단 또는 적용을 제공하지 않습니다.

(<a id="fn5">5)</a>Microsoft Defender 바이러스 백신 수동 모드인 경우 위협 수정 기능은 예약된 검사 또는 수동 검사 중에만 활성화됩니다.

> [!NOTE]
> [Microsoft 365 수동](/microsoft-365/compliance/endpoint-dlp-learn-about) 모드에 있는 경우 끝점 데이터 손실 방지 Microsoft Defender 바이러스 백신 정상적으로 작동합니다.

## <a name="important-notes"></a>중요 참고 사항

- Microsoft Defender 바이러스 백신, Endpoint용 Defender 또는 앱 앱에 사용되는 관련 서비스를 사용하지 않도록 설정하거나 중지하거나 수정하지 Windows 보안 않습니다. 이 권장에는 *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* 또는 *MsMpEng* 서비스 및 프로세스가 포함됩니다. 이러한 서비스를 수동으로 수정하면 장치에 심각한 문제가 발생할 수 있으며 네트워크가 취약해질 수 있습니다. 이러한 서비스를 사용하지 않고 중지하거나 수정하면 Microsoft가 아닌 다른 바이러스 백신 솔루션을 사용할 때와 해당 정보가 앱 앱에 표시되는 방식에 문제가 Windows 보안 [있습니다.](microsoft-defender-security-center-antivirus.md)

- 끝점용 Defender에서 EDR 바이러스 백신 솔루션이 아니어도 Microsoft Defender 바이러스 백신 모드로 전환합니다. EDR 모드에서 디바이스에서 발견된 악성 항목을 감지하고 수정합니다(위반 후). 자세한 내용은 EDR [모드로 전환을 참조합니다.](edr-in-block-mode.md)

## <a name="how-to-confirm-the-state-of-microsoft-defender-antivirus"></a>상태 확인 방법Microsoft Defender 바이러스 백신

다음 표에 설명된 여러 방법 중 하나를 사용하여 Microsoft Defender 바이러스 백신 상태를 확인할 수 있습니다.

<br/><br/>

 | 메서드 | 절차 | 
 |---|---| 
 | Windows 보안 앱 |  1. Windows 디바이스에서 Windows 보안 를 니다.<br/>2. 바이러스 **백신 & 보호를 선택합니다.**<br/>3. Who **보호에서** 공급자 **관리를 선택합니다.**<br/>4. **보안** 공급자 페이지의 바이러스 백신 **아래에서** 를 Microsoft Defender 바이러스 백신 **표시됩니다.** | 
 | 작업 관리자 |  1. Windows 디바이스에서 작업 관리자 앱을 니다.<br/>2. 세부 정보 **탭을** 선택합니다.<br/>3. **목록에서** MsMpEng.exe찾아야 합니다. | 
 | Windows PowerShell <br/><br/> (실행 중인 Microsoft Defender 바이러스 백신 확인) |  1. Windows 장치에서 Windows PowerShell. <br/>2. 다음 PowerShell cmdlet을 `Get-Process` 실행합니다. .<br/>3. 결과를 검토합니다. 활성화된 **MsMpEng.exe** 경우 Microsoft Defender 바이러스 백신 표시됩니다. | 
 | Windows PowerShell <br/><br/> (바이러스 백신 보호가 실행 중이지 확인) |  [Get-MpComputerStatus PowerShell cmdlet을 사용할 수 있습니다.](/powershell/module/defender/get-mpcomputerstatus) <br/><br/>1. Windows 장치에서 Windows PowerShell.<br/>2. 다음 PowerShell cmdlet을 `Get-MpComputerStatus | select AMRunningMode` 실행합니다. .<br/>3. 결과를 검토합니다. 끝점에서 사용할 **수** **있는** Microsoft Defender 바이러스 백신 일반 또는 수동이 표시됩니다.  | 
 | 명령 프롬프트 |  1. Windows 디바이스에서 명령 프롬프트를 니다.<br/>2. `sc query windefend` 를 입력한 다음 Enter를 누를 수 있습니다.<br/>3. 결과를 검토하여 수동 Microsoft Defender 바이러스 백신 실행 중인지 검토합니다.  | 

## <a name="more-details-about-microsoft-defender-antivirus-states"></a>상태와 관련한 Microsoft Defender 바이러스 백신 세부 정보

이 섹션의 표에서는 사용자와 함께 표시될 수 있는 다양한 Microsoft Defender 바이러스 백신.

<br/><br/>

 |  상태  |  발생 작업  | 
 |---|---| 
 |  활성 모드  |  활성 모드에서는 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용됩니다. 설정, 그룹 정책, Microsoft Intune 또는 기타 관리 제품을 사용하여 구성한 정책이 적용됩니다. 파일을 검색하고 위협을 해결하며 구성 도구(예: 구성 관리자 또는 끝점 자체의 Microsoft Defender 바이러스 백신 앱)에 검색 정보가 보고됩니다.  | 
 |  수동 모드  |  수동 모드에서는 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용되지 않을  뿐만 아니라 위협이 제거되지 Microsoft Defender 바이러스 백신. 그러나 차단 모드에서 끝점 감지 및 [대응(EDR)을](edr-in-block-mode.md)통해 위협을 해결할 수 있습니다. <br/><br/> 파일을 검사하고 끝점용 Defender 서비스와 공유되는 위협 감지에 대한 보고서가 제공됩니다. 보안 센터에서 수동 [](microsoft-defender-security-center.md) 모드에 있는 경우에도 Microsoft Defender 바이러스 백신 경고가 표시될 Microsoft Defender 바이러스 백신 있습니다. <br/><br/> 수동 Microsoft Defender 바이러스 백신 경우 에 대한 업데이트를 관리할 [Microsoft Defender 바이러스 백신.](manage-updates-baselines-microsoft-defender-antivirus.md) 그러나 장치에 맬웨어로부터 실시간 보호를 Microsoft Defender 바이러스 백신 Microsoft가 아닌 바이러스 백신 제품이 있는 경우 활성 모드로 전환할 수 없습니다. <br/><br/> 보안 계층 방어 및 검색 기능을 최적화하기 위해 수동 모드에서 실행 중인 경우에도 바이러스 백신 및 Microsoft Defender 바이러스 백신 업데이트를 다운로드해야 합니다. 자세한 [내용은 Microsoft Defender 바이러스 백신 관리 및 기준 적용을 참조하세요.](manage-updates-baselines-microsoft-defender-antivirus.md) <br/><br/> **참고:** 수동 모드는 수동 모드에서 지원되지 Windows Server 2016.  | 
 |  사용 안 함 <br/><br/> 또는 <br/><br/> 제거  |  사용하지 않도록 설정하거나 제거하면 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용되지 않습니다. 파일을 검사하지 않은 경우 위협이 해결되지 않습니다. <br/><br/> 일반적으로 Microsoft Defender 바이러스 백신 사용 안 하게 또는 Microsoft Defender 바이러스 백신 권장되지 않습니다. 가능하면 microsoft가 아닌 Microsoft Defender 바이러스 백신/바이러스 백신 솔루션을 사용하는 경우 수동 모드로 유지하세요. <br/><br/> 자동 Microsoft Defender 바이러스 백신 사용하지 않도록 설정된 경우 Microsoft가 아닌 바이러스 백신/맬웨어 방지 제품이 만료되거나 바이러스, 맬웨어 또는 기타 위협으로부터 실시간 보호를 제공하는 것을 중지하는 경우 자동으로 다시 활성화할 수 있습니다. 자동 다시 사용하도록 설정하면 Microsoft Defender 바이러스 백신 끝점에서 바이러스 백신 보호가 유지 관리됩니다. <br/><br/> 또한 Microsoft가 [](limited-periodic-scanning-microsoft-defender-antivirus.md)아닌 바이러스 백신 앱을 사용하는 경우 Microsoft Defender 바이러스 백신 엔진에서 작동하는 제한된 주기적 검사 를 사용하여 위협을 주기적으로 확인할 수 있습니다.  | 


## <a name="see-also"></a>참고 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [차단 모드의 EDR](edr-in-block-mode.md)
- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](/microsoft-365/compliance/endpoint-dlp-learn-about)
