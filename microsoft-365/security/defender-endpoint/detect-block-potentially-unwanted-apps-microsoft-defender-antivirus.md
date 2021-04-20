---
title: Microsoft Defender 바이러스 백신을 통해 잠재적으로 원치 않는 응용 프로그램 차단
description: 잠재적으로 원치 않는 응용 프로그램(PUA) 바이러스 백신 기능을 사용하도록 설정하여 애드웨어와 같은 원치 않는 소프트웨어를 차단합니다.
keywords: pua, 사용, 원치 않는 소프트웨어, 원치 않는 앱, 애드웨어, 브라우저 도구 모음, 검색, 차단, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8350db473580fd4d1728c3473742da5b63196c52
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893580"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>잠재적으로 원치 않는 응용 프로그램 검색 및 차단

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

PUA(잠재적으로 원치 않는 응용 프로그램)는 컴퓨터의 실행 속도가 느려지거나 예기치 않은 광고가 표시되거나 최악의 경우 예기치 않게 또는 원치 않는 다른 소프트웨어를 설치할 수 있는 소프트웨어 범주입니다. PUA는 바이러스, 맬웨어 또는 기타 유형의 위협으로 간주되지 않지만 끝점 성능 또는 사용에 부정적인 영향을 주는 끝점에서 작업을 수행할 수 있습니다. *PUA란* 용어는 특정 종류의 원치 않은 동작으로 인해 끝점에 대한 Microsoft Defender에서 평가한 신뢰도가 낮은 응용 프로그램을 참조할 수도 있습니다.

다음은 몇 가지 예입니다.

- **웹 페이지로** 광고를 삽입하는 소프트웨어를 포함하여 광고 또는 프로모션을 표시하는 광고 소프트웨어.
- **동일한 엔터티가** 디지털 서명하지 않은 다른 소프트웨어를 설치하기 위해 제공하는 소프트웨어 번들링. 또한 PUA로 한정하는 다른 소프트웨어를 설치하기 위해 제공하는 소프트웨어입니다.
- **보안 제품에서** 다르게 행동하는 소프트웨어를 포함하여 보안 제품의 검색을 적극적으로 피하는 소프트웨어 사용.

> [!TIP]
> 보안 기능에서 특별히 주의를 기울이기 위해 응용 프로그램에 레이블을 지정하는 데 사용하는 기준에 대한 자세한 예와 자세한 내용은 Microsoft에서 맬웨어 및 사용자 지정 응용 프로그램을 식별하는 [방법을 참조합니다.](/windows/security/threat-protection/intelligence/criteria)

잠재적으로 원치 않는 응용 프로그램은 네트워크가 실제 맬웨어에 감염될 위험을 높이거나, 맬웨어 감염을 식별하기 어렵게 만들거나, IT 리소스를 정리하는 데 리소스를 낭비할 수 있습니다. PUA 보호는 Windows 10, Windows Server 2019 및 Windows Server 2016에서 지원됩니다. Windows 10(버전 2004 이상)에서 Microsoft Defender 바이러스 백신은 기본적으로 엔터프라이즈용 PUA(E5) 장치로 간주되는 앱을 차단합니다.

## <a name="microsoft-edge"></a>Microsoft Edge

Chromium 기반의 새 [Microsoft Edge는](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)잠재적으로 원치 않는 응용 프로그램 다운로드 및 연결된 리소스 URL을 차단합니다. 이 기능은 [Microsoft Defender SmartScreen을 통해 제공됩니다.](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Chromium 기반 Microsoft Edge에서 PUA 보호 사용

Microsoft Edge(Chromium 기반 버전 80.0.361.50)의 잠재적으로 원치 않는 응용 프로그램 보호가 기본적으로 꺼져 있는 경우 브라우저 내에서 쉽게 끄면 됩니다.

1. Edge 브라우저에서 타원을 선택한 다음 설정을 **선택합니다.**

2. 개인 **정보, 검색 및 서비스를 선택합니다.**

3. 보안 **섹션에서** 잠재적으로 원치 않는 앱 **차단을 켜십시오.**

> [!TIP]
> Microsoft Edge(Chromium 기반)를 실행하는 경우 [Microsoft Defender SmartScreen](https://demo.smartscreen.msft.net/)데모 페이지 중 하나에서 테스트하여 PUA 보호의 URL 차단 기능을 안전하게 탐색할 수 있습니다.

### <a name="blocking-urls-with-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen을 통해 URL 차단

PUA 보호가 켜진 Chromium 기반 Edge에서 Microsoft Defender SmartScreen은 PUA 관련 URL로부터 보호합니다.

보안 관리자는 Microsoft [Edge와](/DeployEdge/configure-microsoft-edge) Microsoft Defender SmartScreen이 함께 작동하여 PUA 관련 URL로부터 사용자 그룹을 보호하는 방법을 구성할 수 있습니다. PUA를 [](/DeployEdge/microsoft-edge-policies#smartscreen-settings) 차단하기 위한 설정을 포함하여 Microsoft Defender SmartScreen에 대해 명시적으로 사용할 수 있는 여러 그룹 정책 [설정이 있습니다.](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled) 또한 관리자는 그룹 정책 설정을 사용하여 Microsoft Defender SmartScreen을 설정하거나 해제하여 [Microsoft Defender SmartScreen을](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen) 전체적으로 구성할 수 있습니다.

Microsoft Defender for Endpoint에는 Microsoft에서 관리하는 데이터 집합을 기반으로 하는 자체 차단 목록이 있습니다. 그러나 위협 인텔리전스를 기반으로 이 목록을 사용자 지정할 수 있습니다. 끝점 [포털용](manage-indicators.md) Microsoft Defender에서 표시기를 만들고 관리하는 경우 Microsoft Defender SmartScreen은 새 설정을 적용합니다.

## <a name="microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신

Microsoft Defender 바이러스 백신의 잠재적으로 원치 않는 PUA(응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA를 검색하고 차단할 수 있습니다.

> [!NOTE]
> 이 기능은 Windows 10, Windows Server 2019 및 Windows Server 2016에서 사용할 수 있습니다.

Microsoft Defender 바이러스 백신은 검색된 PUA 파일 및 다운로드, 이동, 실행 또는 설치 시도를 차단합니다. 그런 다음 차단된 PUA 파일이 검지로 이동됩니다. 끝점에서 PUA 파일이 검색되면 Microsoft Defender 바이러스 백신은 알림이[](configure-notifications-microsoft-defender-antivirus.md)사용하지 않도록 설정되지 않은 경우 다른 위협 감지와 동일한 형식으로 사용자에게 알림을 전송합니다. 알림은 콘텐츠를 `PUA:` 나타내기 위해 미리 표시됩니다.

알림은 Windows 보안 앱 내의 일반적인 [검지 목록에 표시됩니다.](microsoft-defender-security-center-antivirus.md)

### <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에서 PUA 보호 구성

[Microsoft Intune, Microsoft Endpoint](/mem/intune/protect/device-protect) [Configuration Manager,](/mem/configmgr/protect/deploy-use/endpoint-protection)그룹 [](/azure/active-directory-domain-services/manage-group-policy)정책 또는 [PowerShell cmdlet을](/powershell/module/defender/?preserve-view=true&view=win10-ps)통해 PUA 보호를 사용하도록 설정할 수 있습니다.

감사 모드에서 PUA 보호를 사용하여 잠재적으로 원치 않는 응용 프로그램을 차단하지 않고 검색할 수도 있습니다. 검색은 Windows 이벤트 로그에 캡처됩니다.

> [!TIP]
> Microsoft Defender for [Endpoint](https://demo.wd.microsoft.com/Page/UrlRep) 데모 웹 사이트(demo.wd.microsoft.com)를 방문하여 기능이 작동하고 있는지 확인하고 작동을 확인하세요.

감사 모드에서 PUA 보호는 회사에서 내부 소프트웨어 보안 준수 검사를 수행하고 있으며 가극적 긍정을 방지하고자 하는 경우 유용합니다.

#### <a name="use-intune-to-configure-pua-protection"></a>Intune을 사용하여 PUA 보호 구성

자세한 [내용은 Microsoft Intune의](/intune/device-restrictions-configure) 장치 제한 설정 구성 및 [Intune에서 Windows 10에](/intune/device-restrictions-windows-10#microsoft-defender-antivirus) 대한 Microsoft Defender 바이러스 백신 장치 제한 설정을 참조하세요.

#### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager를 사용하여 PUA 보호 구성

PUA 보호는 기본적으로 Microsoft Endpoint Manager(현재 분기)에서 사용하도록 설정됩니다.

Microsoft Endpoint Manager(현재 분기)를 구성하는 방법에 대한 자세한 내용은 맬웨어 방지 정책을 만들고 배포하는 [방법:](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings) 예약된 검사 설정을 참조하세요.

구성 System Center 2012 대한 자세한 내용은 [Configuration Manager에서 Endpoint Protection에](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)대해 잠재적으로 원치 않는 응용 프로그램 보호 정책을 배포하는 방법을 참조합니다.

> [!NOTE]
> Microsoft Defender 바이러스 백신에서 차단된 PUA 이벤트는 Microsoft Endpoint Configuration Manager가 아닌 Windows 이벤트 뷰어에 보고됩니다.

#### <a name="use-group-policy-to-configure-pua-protection"></a>그룹 정책을 사용하여 PUA 보호 구성

1. [Windows 10 2020년 10월 업데이트용 관리 템플릿(.admx)을 다운로드하여 설치(20H2)](https://www.microsoft.com/download/details.aspx?id=102157)

2. 그룹 정책 관리 컴퓨터에서 그룹 정책 관리 [콘솔 을 니다.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))

3. 구성할 그룹 정책 개체를 선택한 다음 편집 을 **선택합니다.**

4. 그룹 **정책 관리 편집기에서** 컴퓨터 **구성으로 이동하여** 관리 **템플릿을 선택합니다.**

5. Windows 구성 요소 Microsoft Defender 바이러스 **백신까지**  >  **트리를 확장합니다.**

6. 원치 않는 응용 프로그램에 대한 검색 구성을 두 **번 클릭합니다.**

7. PUA **보호를** 사용하도록 설정하려면 사용 을 선택합니다.

8. **옵션에서** **차단을** 선택하여 잠재적으로 원치  않는 응용 프로그램을 차단하거나 감사 모드를 선택하여 해당 환경에서 설정이 작동하는 방법을 테스트합니다. **확인** 을 선택합니다.

9. 일반적으로와 같은 그룹 정책 개체를 배포합니다.

#### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell cmdlet을 사용하여 PUA 보호 구성

##### <a name="to-enable-pua-protection"></a>PUA 보호를 사용하도록 설정하려면

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

기능을 사용하지 않도록 설정한 경우 이 cmdlet의 값을 설정하여 `Enabled` 기능을 켜야 합니다.

##### <a name="to-set-pua-protection-to-audit-mode"></a>PUA 보호를 감사 모드로 설정

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

설정은 `AuditMode` PUAS를 차단하지 않고 검색합니다.

##### <a name="to-disable-pua-protection"></a>PUA 보호를 사용하지 않도록 설정

PUA 보호는 계속 켜져 있는 것이 좋습니다. 그러나 다음 cmdlet을 사용하여 이 기능을 해제할 수 있습니다.

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

이 cmdlet의 값을 설정하여 기능이 활성화된 `Disabled` 경우 기능을 해제합니다.

Microsoft Defender 바이러스 백신과 함께 PowerShell을 사용하는 방법에 대한 자세한 내용은 [PowerShell cmdlet을](use-powershell-cmdlets-microsoft-defender-antivirus.md) 사용하여 Microsoft Defender 바이러스 백신 및 [Defender cmdlet](/powershell/module/defender/index) 구성 및 실행을 참조하세요.

## <a name="view-pua-events"></a>PUA 이벤트 보기

PUA 이벤트는 Windows 이벤트 뷰어에서 보고되지만 Microsoft Endpoint Manager 또는 Intune에서는 보고되지 않습니다. 이 cmdlet을 사용하여 Microsoft Defender 바이러스 백신이 처리한 `Get-MpThreat` 위협을 볼 수도 있습니다. 예를 들면 다음과 같습니다.

```console
CategoryID       : 27
DidThreatExecute : False
IsActive         : False
Resources        : {webfile:_q:\Builds\Dalton_Download_Manager_3223905758.exe|http://d18yzm5yb8map8.cloudfront.net/
                    fo4yue@kxqdw/Dalton_Download_Manager.exe|pid:14196,ProcessStart:132378130057195714}
RollupStatus     : 33
SchemaVersion    : 1.0.0.0
SeverityID       : 1
ThreatID         : 213927
ThreatName       : PUA:Win32/InstallCore
TypeID           : 0
PSComputerName   :
```

PUA 검색에 대한 메일을 받기 위해 전자 메일 알림을 끄면 됩니다.

Microsoft Defender 바이러스 백신 이벤트 보기에 대한 자세한 내용은 이벤트 [ID](troubleshoot-microsoft-defender-antivirus.md) 문제 해결을 참조하세요. PUA 이벤트는 이벤트 ID **1160 아래에 기록됩니다.**

끝점용 Microsoft Defender를 사용하는 경우 고급 헌팅 쿼리를 사용하여 PUA 이벤트를 볼 수 있습니다. 다음은 쿼리의 예입니다.

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| evaluate bag_unpack(x)
| where ThreatName startswith_cs 'PUA:'
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName, WasExecutingWhileDetected, WasRemediated
```

## <a name="excluding-files"></a>파일 제외

파일이 PUA 보호에 의해 오차적으로 차단되거나 작업을 완료하기 위해 PUA의 기능이 필요한 경우도 있습니다. 이러한 경우 제외 목록에 파일을 추가할 수 있습니다.

자세한 내용은 파일 확장명 및 폴더 위치에 따라 제외 구성 및 유효성 검사를 [참조하세요.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)

## <a name="see-also"></a>참고 항목

- [차세대 보호](microsoft-defender-antivirus-in-windows-10.md)
- [동작, 추론 및 실시간 보호 구성](configure-protection-features-microsoft-defender-antivirus.md)