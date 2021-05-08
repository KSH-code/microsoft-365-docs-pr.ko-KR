---
title: Microsoft Defender 바이러스 백신 제품과의 호환성
description: 다른 보안 Microsoft Defender 바이러스 백신 운영 체제와의 통합에 대해 자세히 알아보습니다.
keywords: windows defender, 끝점용 defender, 차세대, 바이러스 백신, 호환성, 수동 모드
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr
ms.topic: article
manager: dansimp
ms.technology: mde
ms.date: 05/06/2021
ms.openlocfilehash: e3ec35e777469fec3cda762f7e670490c0963f8d
ms.sourcegitcommit: 5a1cb7d95070eef47d401a4693cc137a90550a5e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/06/2021
ms.locfileid: "52259694"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 바이러스 백신 호환성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="summary"></a>요약

Microsoft Defender 바이러스 백신 실행되는 끝점 및 장치에 자동으로 사용하도록 설정되어 Windows 10. 그러나 다른(Microsoft가 아닌) 바이러스 백신/맬웨어 방지 솔루션이 사용될 경우 어떻게 될까요? 이 방법은 바이러스 백신 보호와 함께 [끝점용 Microsoft Defender를](microsoft-defender-endpoint.md) 사용하는지 여부에 따라 결정됩니다. 이 문서에서는 끝점이 끝점용 Microsoft Defender에 온보딩된 경우 바이러스 백신/맬웨어 방지 솔루션에서 발생하는 문제에 대해 설명합니다.

## <a name="why-defender-for-endpoint-matters"></a>끝점용 Defender가 중요한 이유

Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션을 사용하는 경우에도 끝점을 Defender for Endpoint에 온보딩하는 것이 있습니다. 대부분의 경우 디바이스를 Defender for Endpoint에 온보딩할 때 추가된 보호를 위해 microsoft가 Microsoft Defender 바이러스 백신 바이러스 백신 솔루션과 함께 사용할 수 있습니다. 예를 들어 기본 바이러스 백신 [솔루션에서 EDR](edr-in-block-mode.md)악의적인 아티팩트를 차단하고 수정하는 차단 모드에서 이 기능을 사용할 수 있습니다. 

작동 방식은 다음과 같습니다.

- 조직의 클라이언트 장치가 Microsoft가 아닌 바이러스 백신/웨어웨어 방지 솔루션으로 보호되는 경우 해당 장치가 Endpoint용 Defender에 온보딩될 때 Microsoft Defender 바이러스 백신 수동 모드로 전환됩니다. 이 경우 위협 감지가 발생하지만 실시간 보호 및 위협은 위협에 의해 해결되지 Microsoft Defender 바이러스 백신. **참고:** 이 특정 시나리오는 Windows 실행되는 끝점에는 적용되지 않습니다.

- 조직의 클라이언트 장치가 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션으로 보호되고 해당 장치가 끝점용 Microsoft Defender에 온보딩되지 않은 경우 Microsoft Defender 바이러스 백신 모드로 자동 전환됩니다. 이 경우 위협이 검색되거나 수정되지 Microsoft Defender 바이러스 백신. **참고:** 이 특정 시나리오는 Windows 실행되는 끝점에는 적용되지 않습니다.

- 조직의 끝점이 Windows Server를 실행하고 있으며 해당 끝점이 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션으로 보호되는 경우 해당 끝점이 Endpoint용 Defender에 온보딩될 때 Microsoft Defender 바이러스 백신 수동 모드 또는 비활성화 모드로 자동 전환되지 않습니다. 이 특정 시나리오에서는 서버 끝점을 Windows 구성해야 합니다. 

   - Windows Server, 버전 1803 이상 및 Windows Server 2019에서 수동 모드에서 Microsoft Defender 바이러스 백신 수 있습니다. 
   - 이 Windows Server 2016 Microsoft Defender 바이러스 백신 사용하지 않도록 설정해야 합니다(수동 모드는 Windows Server 2016).

- Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션으로 조직의 끝점을 보호하는 경우 해당 장치가 차단 모드로 [](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 설정된 EDR 끝점용 Defender에 온보딩되면 Endpoint용 Defender는 악성 아티팩트를 차단하고 수정합니다. **참고:** 이 특정 시나리오는 이 시나리오에 적용되지 Windows Server 2016. EDR 모드로 설정하려면 Microsoft Defender 바이러스 백신 수동 모드에서 사용하도록 설정해야 합니다.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>바이러스 백신 및 끝점용 Microsoft Defender

다음 표에는 Microsoft가 아닌 Microsoft Defender 바이러스 백신 맬웨어 방지 솔루션이 함께 사용되거나 끝점용 Microsoft Defender가 없는 경우 발생하는 문제가 요약되어 있습니다. 

| Windows 버전   | 바이러스 백신/맬웨어 방지 솔루션  | 온보더드- <br/> Endpoint용 Defender | Microsoft Defender 바이러스 백신 상태     |
|------|------|-------|-------|
| Windows 10  | Windows Defender 바이러스 백신 | 예  | 활성 모드 | 
| Windows 10  | Windows Defender 바이러스 백신 | 아니요   | 활성 모드 |
| Windows 10  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예  | 수동 모드(자동) |
| Windows 10  | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니요   | 비활성화 모드(자동)    |
| Windows 서버, 버전 1803 이상 <p> Windows Server 2019 | Windows Defender 바이러스 백신  | 예 |         활성 모드  |
| Windows 서버, 버전 1803 이상 <p> Windows Server 2019 | Windows Defender 바이러스 백신 | 아니요  | 활성 모드 |
| Windows 서버, 버전 1803 이상 <p> Windows Server 2019 | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예  | Microsoft Defender 바이러스 백신 수동 모드로 설정해야 합니다(수동) <sup> [[1]](#fn1)<sup>  | 
| Windows 서버, 버전 1803 이상 <p> Windows Server 2019 | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니요  | Microsoft Defender 바이러스 백신 비활성화해야 합니다(수동으로) <sup> [[2]](#fn2)<sup></sup>  |
| Windows Server 2016 | Windows Defender 바이러스 백신 | 예 | 활성 모드 |
| Windows Server 2016 | Windows Defender 바이러스 백신 | 아니요 | 활성 모드 |
| Windows Server 2016 | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 예 | Microsoft Defender 바이러스 백신 비활성화해야 합니다(수동으로) <sup> [[2]](#fn2)<sup> |
| Windows Server 2016 | Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션 | 아니요 | Microsoft Defender 바이러스 백신 비활성화해야 합니다(수동으로) <sup> [[2]](#fn2)<sup> |

(<a id="fn1">1)</a>Windows Server, 버전 1803 이상 또는 Windows Server 2019에서는 microsoft가 아닌 바이러스 백신 제품을 설치할 때 Microsoft Defender 바이러스 백신 수동 모드가 자동으로 전환되지 않습니다. 이러한 경우 [Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) 바이러스 백신 제품을 여러 개 설치하여 문제를 방지할 수 있는 수동 모드로 설정하십시오. PowerShell, Microsoft Defender 바이러스 백신 또는 레지스트리 키를 사용하여 수동 모드로 설정할 수 있습니다.

Windows Server, 버전 1803 이상 또는 Windows Server 2019를 사용하는 경우 다음 레지스트리 키를 설정하여 Microsoft Defender 바이러스 백신 수동 모드로 설정할 수 있습니다.
- 경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 이름: `ForceDefenderPassiveMode`
- 유형: `REG_DWORD`
- 값: `1`

> [!NOTE]
> 수동 모드는 수동 모드에서 지원되지 Windows Server 2016. 레지스트리 키는 레지스트리 `ForcePassiveMode` 키에 Windows Server 2016. 

(<a id="fn2">2</a>) Windows Server 2016 Microsoft가 아닌 바이러스 백신 제품을 사용하는 경우 수동 모드 또는 활성 모드에서 Microsoft Defender 바이러스 백신 실행할 수 없습니다. 이러한 경우 서버에 여러 [바이러스 백신 제품을 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) 문제를 방지하기 위해 수동으로 제거하거나 제거합니다.

Microsoft Defender 바이러스 백신 [서버](microsoft-defender-antivirus-on-windows-server.md) 설치에 대한 주요 차이점 및 Windows 관리 옵션은 Windows 참조하세요.

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신 서버, Windows 10, Windows Server 2016, Windows Server, 버전 1803 이상 및 Windows Server 2019를 실행하는 장치에서만 사용할 수 있습니다.
>
> Windows 8.1 및 Windows Server 2012 엔터프라이즈 수준의 끝점 바이러스 백신 보호는 System Center Endpoint Protection [](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))를 통해 관리되는 Microsoft Endpoint Configuration Manager.
>
> Windows Defender 엔터프라이즈 수준 관리(또는 Windows 8.1 Server Core 설치의 인터페이스)를 제공하지는 Windows 8.1 Windows Server 2012 소비자 장치에도 제공됩니다 Windows Server 2012. [](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)

## <a name="functionality-and-features-available-in-each-state"></a>각 상태의 기능 및 사용 가능한 기능

이 섹션의 표에는 각 상태의 사용 가능한 기능이 요약되어 있습니다. 이 표는 정보 전용으로 디자인됩니다. 활성 모드인지 &, 수동 모드인지, 비활성화/제거되어 있는지에 따라 Microsoft Defender 바이러스 백신 기능을 설명하기 위한 것입니다. 

> [!IMPORTANT]
> 수동 모드에서 또는 차단 모드에서 Microsoft Defender 바이러스 백신 실시간 보호, 클라우드 제공 보호 또는 제한된 주기적 검사와 같은 기능을 끄지 EDR 않습니다. 

|보호 |활성 모드 |수동 모드 |차단 모드의 EDR |사용 안 되거나 제거 |
|:---|:---|:---|:---|:---|
| [실시간 보호 및](configure-real-time-protection-microsoft-defender-antivirus.md) [클라우드 제공 보호](enable-cloud-protection-microsoft-defender-antivirus.md) | 예 | 아니요 <sup> [[3](#fn3)]<sup> | 아니요 | 아니요 |
| [제한된 주기적 검사 가용성](limited-periodic-scanning-microsoft-defender-antivirus.md) | 아니요 | 아니요 | 아니요 | 예 |
| [파일 검색 및 검색 정보](customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 예 | 예 | 예 | 아니요 |
|  [위협 수정](configure-remediation-microsoft-defender-antivirus.md) | 예 | 참고 <sup> 참조 [[4](#fn4)]<sup> | 예 | 아니요 |
| [보안 인텔리전스 업데이트](manage-updates-baselines-microsoft-defender-antivirus.md) | 예 | 예 | 예 | 아니요 |

(<a id="fn3">3)</a>일반적으로 Microsoft Defender 바이러스 백신 수동 모드인 경우 실시간 보호는 활성화되어 있으며 수동 모드에서도 차단 또는 적용을 제공하지 않습니다. 

(<a id="fn4">4)</a>Microsoft Defender 바이러스 백신 수동 모드인 경우 위협 수정 기능은 예약된 검사 또는 수동 검사 중에만 활성화됩니다.

> [!NOTE]
> [Microsoft 365 또는](/microsoft-365/compliance/endpoint-dlp-learn-about) 수동 모드에 있는 경우 끝점 데이터 손실 방지 Microsoft Defender 바이러스 백신 정상적으로 작동합니다.

## <a name="keep-the-following-points-in-mind"></a>다음에 유의해야 합니다.

- 활성 모드에서는 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용됩니다. Configuration Manager, 그룹 정책, Intune 또는 기타 관리 제품으로 만든 모든 구성이 적용됩니다. 파일을 검색하고 위협을 수정하고 구성 도구(예: Configuration Manager 또는 컴퓨터 자체의 Microsoft Defender 바이러스 백신 앱)에 검색 정보가 보고됩니다.

- 수동 모드에서는 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용되지 않을 뿐만 아니라 위협이 제거되지 Microsoft Defender 바이러스 백신. 파일을 검사하고 끝점용 Microsoft Defender 서비스와 공유되는 위협 감지에 대한 보고서가 제공됩니다. 보안 센터에서 수동 [](microsoft-defender-security-center.md) 모드에 있는 경우에도 Microsoft Defender 바이러스 백신 경고가 표시될 Microsoft Defender 바이러스 백신 있습니다.

- 차단 [EDR](edr-in-block-mode.md) 켜져 있으며 Microsoft Defender 바이러스 백신 바이러스 백신 솔루션이 아닌 경우 악의적인 항목을 검색하고 수정합니다. EDR 모드로 설정하려면 Microsoft Defender 바이러스 백신 수동 모드에서 사용하도록 설정해야 합니다.

- 사용하지 않도록 설정하면 Microsoft Defender 바이러스 백신 바이러스 백신 앱으로 사용되지 않습니다. 파일을 검사하지 않은 경우 위협이 해결되지 않습니다. 일반적으로 Microsoft Defender 바이러스 백신 사용 안 하게/Microsoft Defender 바이러스 백신 권장되지 않습니다. 가능하면 microsoft가 아닌 Microsoft Defender 바이러스 백신/바이러스 백신 솔루션을 사용하는 경우 수동 모드로 유지하세요.

- 끝점용 Microsoft Defender에 등록되어 있으며 타사 맬웨어 방지 제품을 사용하는 경우 수동 모드가 사용하도록 설정됩니다. 이 서비스는 침입 시도 및 공격을 Microsoft Defender 바이러스 백신 장치 및 네트워크를 제대로 모니터링하기 위해 Microsoft Defender 바이러스 백신 서비스에서 일반적인 정보 공유가 필요합니다. 자세한 내용은 [Microsoft Defender 바이러스 백신 Microsoft Defender for Endpoint와의 호환성을 참조합니다.](defender-compatibility.md) 

- 수동 Microsoft Defender 바이러스 백신 경우 에 대한 업데이트를 관리할 [Microsoft Defender 바이러스 백신.](manage-updates-baselines-microsoft-defender-antivirus.md) 그러나 장치에 맬웨어로부터 실시간 보호를 Microsoft Defender 바이러스 백신 Microsoft가 아닌 최신 바이러스 백신 제품이 있는 경우 활성 모드로 전환할 수 없습니다. 보안 계층 방어 및 검색 기능을 최적화하기 위해 [](manage-updates-baselines-microsoft-defender-antivirus.md) 수동 모드에서 실행 중인 경우에도 Microsoft Defender 바이러스 백신 보호(보안 인텔리전스 업데이트, 엔진 및 플랫폼)Microsoft Defender 바이러스 백신 업데이트해야 합니다.

- 자동 Microsoft Defender 바이러스 백신 사용하지 않도록 설정하면 Microsoft가 아닌 바이러스 백신 제품에서 제공하는 보호가 만료되거나 바이러스, 맬웨어 또는 기타 위협으로부터 실시간 보호를 제공하는 것을 중지하면 자동으로 다시 활성화될 수 있습니다. 자동 다시 사용하도록 설정하면 장치에서 바이러스 백신 보호가 유지 관리됩니다. 또한 기본 바이러스 [](limited-periodic-scanning-microsoft-defender-antivirus.md)백신 앱 외에 Microsoft Defender 바이러스 백신 검사 엔진을 사용하여 위협을 주기적으로 검사하는 제한된 주기적 검사를 사용하도록 설정할 수 있습니다.

> [!WARNING]
> Microsoft Defender 바이러스 백신, 끝점용 Microsoft Defender 또는 앱 앱에 사용되는 관련 서비스를 사용하지 않도록 설정하거나 중지하거나 수정하지 Windows 보안 않습니다. 이 권장에는 *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* 또는 *MsMpEng* 서비스 및 프로세스가 포함됩니다. 이러한 서비스를 수동으로 수정하면 장치에 심각한 문제가 발생할 수 있으며 네트워크가 취약해질 수 있습니다. 이러한 서비스를 사용하지 않고 중지하거나 수정하면 Microsoft가 아닌 다른 바이러스 백신 솔루션을 사용할 때와 해당 정보가 앱 앱에 표시되는 방식에 문제가 Windows 보안 [있습니다.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>참고 항목

- [Microsoft Defender 바이러스 백신 Windows 10](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [차단 모드의 EDR](edr-in-block-mode.md)
- [구성 Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)
- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](/microsoft-365/compliance/endpoint-dlp-learn-about)
