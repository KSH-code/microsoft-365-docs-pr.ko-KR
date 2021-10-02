---
title: Microsoft Defender 바이러스 백신을 통해 사용자 동의없이 설치된 응용 프로그램 차단
description: PUA(사용자 동의없이 설치된 응용 프로그램) 바이러스 백신 기능을 사용하도록 설정하여 애드웨어와 같은 원하지 않는 소프트웨어를 차단합니다.
keywords: pua, 사용, 원하지 않는 소프트웨어, 원하지 않는 앱, 애드웨어, 브라우저 도구 모음, 감지, 차단, Microsoft Defender 바이러스 백신
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: detect
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
audience: ITPro
ms.reviewer: mimilone, julih
manager: dansimp
ms.technology: mde
ms.topic: article
ms.date: 06/02/2021
ms.collection: m365-security-compliance
ms.openlocfilehash: 230e70000e4561c7b88bcedb7bab143b03b95b49
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042893"
---
# <a name="detect-and-block-potentially-unwanted-applications"></a>사용자 동의없이 설치된 응용 프로그램 검색 및 차단

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)
- [Microsoft Edge](/microsoft-edge/deploy/microsoft-edge)

PUA(사용자 동의없이 설치된 응용 프로그램)는 컴퓨터가 느리게 실행되거나 예기치 않은 광고가 표시되거나 최악의 상황으로 예상치 못하거나 원치 않을 수 있는 기타 소프트웨어를 설치하게 할 수 있는 소프트웨어 범주입니다. PUA는 바이러스, 맬웨어 또는 다른 유형의 위협으로 간주되지 않지만 끝점에서 끝점 성능이나 사용에 부정적인 영향을 주는 작업을 수행할 수 있습니다. *PUA* 라는 용어는 특정 종류의 바람직하지 않은 동작으로 인해 엔드포인트용 Microsoft Defender에서 평가한 평판이 나쁜 응용 프로그램을 가리키지도 합니다.

다음은 몇 가지 예입니다.

- 광고나 프로모션을 표시하는 **광고 소프트웨어**, 광고를 웹페이지에 삽입하는 소프트웨어 포함.
- 동일한 엔터티에서 디지털 서명된 것이 아닌 다른 소프트웨어를 설치하도록 제안하는 **번들화 소프트웨어**. 또한 PUA로 적격한 다른 소프트웨어를 설치하도록 제안하는 소프트웨어를 말하기도 함.
- 보안 제품이 있을 때 다르게 동작하는 소프트웨어를 포함해 보안 제품의 탐지를 적극적으로 피하려고 하는 **회피 소프트웨어**.

> [!TIP]
> 보안 기능에서 특별히 주의를 기울이기 위해 응용 프로그램에 레이블을 지정하는 데 사용하는 기준에 대한 논의 사항과 추가 예제는 [Microsoft에서 맬웨어 및 사용자 동의없이 설치된 응용 프로그램을 식별하는 방법](/windows/security/threat-protection/intelligence/criteria)을 참조하세요.

사용자 동의없이 설치된 응용 프로그램이 있으면 네트워크가 실제 맬웨어에 감염될 위험이 높아지고 맬웨어 감염을 식별하기 어렵게 되거나 감염을 없애는 데 IT 리소스가 낭비될 수 있습니다. PUA 보호 기능은 Windows 10, Windows Server 2019, Windows Server 2022 및 Windows Server 2016에서 지원됩니다. Windows 10(버전 2004 이상)에서 Microsoft Defender 바이러스 백신은 기본적으로 Enterprise(E5) 디바이스용 PUA로 간주되는 앱을 차단합니다.

## <a name="microsoft-edge"></a>Microsoft Edge

[새로운 Microsoft Edge](https://support.microsoft.com/microsoft-edge/get-to-know-microsoft-edge-3f4bb0ff-58de-2188-55c0-f560b7e20bea)는 Chromium 기반으로 사용자 동의없이 설치된 응용 프로그램 다운로드 및 관련 리소스 URL을 차단합니다. 이 기능은 [Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview)을 통해 제공됩니다.

### <a name="enable-pua-protection-in-chromium-based-microsoft-edge"></a>Chromium 기반 Microsoft Edge에서 PUA 보호 사용

Microsoft Edge(Chromium 기반 버전 80.0.361.50)에서 사용자 동의없이 설치된 응용 프로그램 보호는 기본적으로 꺼져 있지만 브라우저 내에서 손쉽게 켤 수 있습니다.

1. Microsoft Edge 브라우저에서 줄임표를 선택한 후 **설정** 을 선택합니다.

2. **개인 정보, 검색 및 서비스** 를 선택합니다.

3. **보안** 섹션에서 **사용자 동의없이 설치된 앱 차단** 을 켭니다.

> [!TIP]
> Microsoft Edge(Chromium 기반)를 실행하는 경우 [Microsoft Defender SmartScreen 데모 페이지](https://demo.smartscreen.msft.net/) 중 하나에서 테스트하여 PUA 보호의 URL 차단 기능을 안전하게 탐색할 수 있습니다.

### <a name="block-urls-with-microsoft-defender-smartscreen"></a>Microsoft Defender SmartScreen로 URL 차단

PUA 보호가 켜진 Chromium 기반 Edge에서 Microsoft Defender SmartScreen은 PUA 관련 URL로부터 사용자를 보호합니다.

보안 관리자는 Microsoft Edge 및 Microsoft Defender SmartScreen이 함께 작동하여 PUA 관련 URL로부터 사용자 그룹을 보호하는 방법을 [구성](/DeployEdge/configure-microsoft-edge)할 수 있습니다. Microsoft Defender SmartScreen에는 [PUA를 차단하기 위한 설정](/DeployEdge/microsoft-edge-policies#smartscreenpuaenabled)을 포함하여 몇 가지 명시적으로 사용할 수 있는 [그룹 정책 설정](/DeployEdge/microsoft-edge-policies#smartscreen-settings)이 있습니다. 또한 관리자는 그룹 정책 설정을 통해 [Microsoft Defender SmartScreen을 하나의 전체로 구성](/microsoft-edge/deploy/available-policies?source=docs#configure-windows-defender-smartscreen)하여 Microsoft Defencer SmartScreen을 켜거나 끌 수 있습니다.

엔드포인트용 Microsoft Defender에는 Microsoft에서 관리하는 데이터 집합을 기반으로 한 자체 차단 목록이 있지만, 자체 위협 인텔리전스 기반의 이 목록을 사용자 지정할 수 있습니다. 엔드포인트용 Microsoft Defender 포털에서 [지표를 만들고 관리](manage-indicators.md)하는 경우 Microsoft Defender SmartScreen은 새 설정을 사용합니다.

## <a name="microsoft-defender-antivirus-and-pua-protection"></a>Microsoft Defender 바이러스 백신 및 PUA 보호

Microsoft Defender 바이러스 백신의 PUA(사용자 동의없이 설치된 응용 프로그램) 보호 기능은 네트워크의 끝점에서 PUA를 검색하고 차단할 수 있습니다.

> [!NOTE]
> 이 기능은 Windows 10, Windows Server 2019, Windows Server 2022 및 Windows Server 2016에서 사용할 수 있습니다.

Microsoft Defender 바이러스 백신은 감지된 PUA 파일 및 이를 다운로드, 이동, 실행 또는 설치하려는 시도를 차단합니다. 그런 다음 차단된 PUA 파일은 이동하여 격리됩니다. 끝점에서 PUA 파일이 감지되면 Microsoft Defender 바이러스 백신에서는 다른 위협 감지와 같은 형식으로 사용자에게 알림을 전송합니다([알림이 사용하지 않도록 설정된 경우가 아니면](configure-notifications-microsoft-defender-antivirus.md)). 알림은 내용은 표시하기 위해 `PUA:`(으)로 시작됩니다.

알림은 [Windows 보안 앱 내 일반적인 격리 목록](microsoft-defender-security-center-antivirus.md)에 표시됩니다.

## <a name="configure-pua-protection-in-microsoft-defender-antivirus"></a>Microsoft Defender 바이러스 백신에서 PUA 보호 구성

[Microsoft Intune](/mem/intune/protect/device-protect), [Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection), [그룹 정책](/azure/active-directory-domain-services/manage-group-policy), 또는 [PowerShell cmdlet](/powershell/module/defender/?preserve-view=true&view=win10-ps)을 통해 PUA 보호를 사용하도록 설정할 수 있습니다.

사용자 동의없이 설치된 응용 프로그램을 차단하지 않고 감지하기 위해 PUA 보호를 감사 모드로 사용할 수도 있습니다. 감지는 Windows 이벤트 로그에 기록됩니다.

> [!TIP]
> [demo.wd.microsoft.com](https://demo.wd.microsoft.com/Page/UrlRep)에서 엔드포인트용 Microsoft Defender 데모 웹 사이트를 방문하여 기능이 작동하는지 확인하고 실제로 작동해 보세요.

회사에서 내부 소프트웨어 보안 규정 준수 검사를 수행하고 있으며 오탐지를 피하고자 하는 경우에 PUA 보호를 감사 모드로 사용하는 것이 유용합니다.

### <a name="use-intune-to-configure-pua-protection"></a>Intune을 사용하여 PUA 보호 구성

자세한 내용은 [Microsoft Intune에서 디바이스 제한 설정 구성](/intune/device-restrictions-configure) 및 [Intune에서 Windows 10의 Microsoft Defender 바이러스 백신 디바이스 제한 설정](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)을 참조하세요.

### <a name="use-configuration-manager-to-configure-pua-protection"></a>Configuration Manager를 사용하여 PUA 보호 구성

PUA 보호는 기본적으로 Microsoft Endpoint Manager(현재 분기)에서 사용하도록 설정됩니다.

Microsoft Endpoint Manager(현재 분기) 구성에 대한 자세한 내용은 [맬웨어 방지 정책을 만들고 배포하는 방법: 예약 검사 설정](/configmgr/protect/deploy-use/endpoint-antimalware-policies#real-time-protection-settings)을 참조하세요.

System Center 2012 Configuration Manager의 경우 [Configuration Manager에서 Endpoint Protection을 위한 사용자 동의없이 설치된 응용 프로그램 보호 정책을 배포하는 방법](/previous-versions/system-center/system-center-2012-R2/hh508770(v=technet.10)#BKMK_PUA)을 참조하세요.

> [!NOTE]
> Microsoft Defender 바이러스 백신에서 차단하는 PUA 이벤트는 Microsoft Endpoint Configuration Manager가 아닌 Windows 이벤트 뷰어에서 보고됩니다.

### <a name="use-group-policy-to-configure-pua-protection"></a>그룹 정책을 사용하여 PUA 보호 구성

1. [Windows 10 2020년 10월 업데이트(20H2)의 관리 템플릿(.admx)](https://www.microsoft.com/download/details.aspx?id=102157) 다운로드 및 설치

2. 그룹 정책 관리 컴퓨터에서 [그룹 정책 관리 콘솔](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))을 엽니다.

3. 구성할 그룹 정책 개체를 선택한 다음 **편집** 을 선택합니다.

4. **그룹 정책 관리 편집기** 에서 **컴퓨터 구성** 으로 이동하여 **관리 템플릿** 을 선택합니다.

5. **Windows 구성 요소** \> **Microsoft Defender 바이러스 백신으로** 트리를 확장합니다.

6. **사용자 동의없이 설치된 응용 프로그램에 대한 감지 구성** 을 두 번 클릭합니다.

7. PUA 보호를 사용하도록 설정하려면 **사용** 을 선택합니다.

8. **옵션** 에서 **차단** 을 선택하여 잠재적으로 원치 않는 애플리케이션을 차단하거나 **감사 모드** 를 선택하여 환경에서 설정이 작동하는 방식을 테스트합니다. **확인** 을 선택합니다.

9. 평소와 같이 그룹 정책 개체를 배포합니다.

### <a name="use-powershell-cmdlets-to-configure-pua-protection"></a>PowerShell cmdlet을 사용하여 PUA 보호 구성

#### <a name="to-enable-pua-protection"></a>PUA 보호를 사용하도록 설정하려면

```PowerShell
Set-MpPreference -PUAProtection Enabled
```

사용하지 않도록 설정되어 있는 경우 이 cmdlet 값을 `Enabled`(으)로 설정하면 기능이 켜집니다.

#### <a name="to-set-pua-protection-to-audit-mode"></a>PUA 보호를 감사 모드로 설정하려면

```PowerShell
Set-MpPreference -PUAProtection AuditMode
```

`AuditMode`을(를) 설정하면 PUA를 차단하지 않고 감지합니다.

#### <a name="to-disable-pua-protection"></a>PUA 보호를 사용하지 않도록 설정하려면

PUA 보호가 계속 켜져 있도록 하는 것이 권장되지만 다음 cmdlet을 사용하여 끌 수도 있습니다.

```PowerShell
Set-MpPreference -PUAProtection Disabled
```

사용하도록 설정되어 있는 경우 이 cmdlet 값을 `Disabled`(으)로 설정하면 기능이 꺼집니다.

자세한 내용은 [PowerShell cmdlet을 사용하여 Microsoft Defender 바이러스 백신 구성 및 실행](use-powershell-cmdlets-microsoft-defender-antivirus.md)과 [Defender cmdlet](/powershell/module/defender/index)을 참조하세요.

## <a name="view-pua-events-using-powershell"></a>PowerShell을 사용하여 PUA 이벤트 보기

PUA 이벤트는 Microsoft Endpoint Manager 또는 Intune이 아니라 Windows 이벤트 뷰어에서 보고됩니다. 또한 `Get-MpThreat` cmdlet을 사용하여 Microsoft Defender 바이러스 백신에서 처리한 위협을 볼 수도 있습니다. 다음은 예입니다.

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

## <a name="get-email-notifications-about-pua-detections"></a>PUA 감지에 대한 전자 메일 알림 수신

PUA 감지에 대한 메일을 수신하려면 전자 메일 알림을 켜면 됩니다.

Microsoft Defender 바이러스 백신 이벤트 보기에 대한 자세한 내용은 [이벤트 ID 문제 해결](troubleshoot-microsoft-defender-antivirus.md)을 참조하세요. PUA 이벤트는 이벤트 ID **1160** 아래에 기록됩니다.

## <a name="view-pua-events-using-advanced-hunting"></a>고급 헌팅을 사용하여 PUA 이벤트 보기

[Microsoft Defender for Endpoint](microsoft-defender-endpoint.md)를 사용하는 경우 고급 헌팅 쿼리를 사용하여 PUA 이벤트를 볼 수 있습니다. 다음은 쿼리의 예입니다.

```console
DeviceEvents
| where ActionType == "AntivirusDetection"
| extend x = parse_json(AdditionalFields)
| project Timestamp, DeviceName, FolderPath, FileName, SHA256, ThreatName = tostring(x.ThreatName), WasExecutingWhileDetected = tostring(x.WasExecutingWhileDetected), WasRemediated = tostring(x.WasRemediated)
| where ThreatName startswith_cs 'PUA:'
```

고급 헌팅에 대한 자세한 내용을 확인하려면 [고급 헌팅으로 위협을 사전 예방적으로 헌팅하는 방법](advanced-hunting-overview.md)을 참조하세요.

## <a name="exclude-files-from-pua-protection"></a>PUA 보호에서 파일 제외

경우에 따라 PUA 보호로 파일이 잘못 차단되거나 작업을 완료하기 위해서 PUA 기능이 필요할 때가 있습니다. 이 경우 파일을 제외 목록에 추가할 수 있습니다.

자세한 내용은 [파일 확장명 및 폴더 위치를 기준으로 제외를 구성하고 유효성 검사](configure-extension-file-exclusions-microsoft-defender-antivirus.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

- [차세대 보호](microsoft-defender-antivirus-in-windows-10.md)
- [동작, 추론 및 실시간 보호 구성](configure-protection-features-microsoft-defender-antivirus.md)