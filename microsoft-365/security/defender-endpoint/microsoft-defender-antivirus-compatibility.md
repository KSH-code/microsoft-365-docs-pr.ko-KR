---
title: 다른 보안 제품과의 Microsoft Defender 바이러스 백신 호환성
description: 다른 보안 제품과 사용하는 운영 체제와 함께 Microsoft Defender 바이러스 백신에서 예상되는 동작
keywords: windows defender, 차세대, 바이러스 백신, 호환성, 수동 모드
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: tewchen, pahuijbr, shwjha
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 8e179135f12ad6f4ea765eaf975a40534446b51f
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893392"
---
# <a name="microsoft-defender-antivirus-compatibility"></a>Microsoft Defender 바이러스 백신 호환성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

## <a name="overview"></a>개요

Microsoft Defender 바이러스 백신은 자동으로 사용하도록 설정되며 Windows 10을 실행하는 끝점 및 장치에 설치됩니다. 그러나 다른 바이러스 백신/맬웨어 방지 솔루션이 사용될 경우 어떻게 하나요? 이 방법은 바이러스 백신 보호와 함께 [끝점용 Microsoft Defender를](microsoft-defender-endpoint.md) 사용하는지 여부에 따라 결정됩니다.
- 조직의 끝점과 장치가 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션으로 보호되고 끝점용 Microsoft Defender가 사용되지 않는 경우 Microsoft Defender 바이러스 백신이 자동으로 비활성화 모드로 전환됩니다.
- 조직에서 비 Microsoft 바이러스 백신/맬웨어 방지 솔루션과 함께 끝점용 Microsoft Defender를 사용하는 경우 Microsoft Defender 바이러스 백신이 자동으로 수동 모드로 전환됩니다. (실시간 보호 및 위협은 Microsoft Defender 바이러스 백신에 의해 해결되지 않습니다.)
- 조직에서 Microsoft가 아닌 바이러스 백신/맬웨어 방지 솔루션과 함께 끝점용 Microsoft Defender를 사용하고 있으며 차단 모드에서 [EDR을](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 사용하도록 설정한 경우 악의적인 아티팩트가 감지될 때마다 끝점용 Microsoft Defender가 아티팩트를 차단하고 수정하는 조치를 취합니다.

## <a name="antivirus-and-microsoft-defender-for-endpoint"></a>바이러스 백신 및 끝점용 Microsoft Defender

다음 표에는 타사 바이러스 백신 제품이 함께 사용되거나 Endpoint용 Microsoft Defender가 없는 경우 Microsoft Defender 바이러스 백신에서 발생하는 일이 요약됩니다. 


| Windows 버전   | 맬웨어 방지 보호  | 끝점 등록용 Microsoft Defender | Microsoft Defender 바이러스 백신 상태     |
|------|------|-------|-------|
| Windows 10  | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 예  | 수동 모드  |
| Windows 10  | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 아니요   | 자동으로 사용하지 않도록 설정 모드     |
| Windows 10  | Microsoft Defender 바이러스 백신 | 예  | 활성 모드 | 
| Windows 10  | Microsoft Defender 바이러스 백신 | 아니요   | 활성 모드 |
| Windows Server, 버전 1803 이상 또는 Windows Server 2019 | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 예  | 수동 모드로 설정해야 합니다(수동으로) <sup> [[1]](#fn1)<sup>  | 
| Windows Server, 버전 1803 이상 또는 Windows Server 2019 | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 아니요  | 비활성화해야 합니다(수동으로) <sup> [[2](#fn2)]<sup></sup>  |
| Windows Server, 버전 1803 이상 또는 Windows Server 2019 | Microsoft Defender 바이러스 백신  | 예 |         활성 모드  |
| Windows Server, 버전 1803 이상 또는 Windows Server 2019 | Microsoft Defender 바이러스 백신 | 아니요  | 활성 모드 |
| Windows Server 2016 | Microsoft Defender 바이러스 백신 | 예 | 활성 모드 |
| Windows Server 2016 | Microsoft Defender 바이러스 백신 | 아니요 | 활성 모드 |
| Windows Server 2016 | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 예 | 비활성화해야 합니다(수동으로) <sup> [[2](#fn2)]<sup> |
| Windows Server 2016 | Microsoft에서 제공하거나 개발하지 않는 타사 제품 | 아니요 | 비활성화해야 합니다(수동으로) <sup> [[2](#fn2)]<sup> |

(<a id="fn1">1)</a>Windows Server, 버전 1803 이상 또는 Windows Server 2019에서 Microsoft Defender 바이러스 백신은 Microsoft가 아닌 바이러스 백신 제품을 설치할 때 수동 모드로 자동 전환되지 않습니다. 이러한 경우 [Microsoft Defender 바이러스](microsoft-defender-antivirus-on-windows-server.md#need-to-set-microsoft-defender-antivirus-to-passive-mode) 백신을 수동 모드로 설정하여 여러 바이러스 백신 제품을 서버에 설치하여 문제를 방지합니다.

Windows Server, 버전 1803 이상 또는 Windows Server 2019를 사용하는 경우 다음 레지스트리 키를 설정하여 Microsoft Defender 바이러스 백신을 수동 모드로 설정할 수 있습니다.
- 경로: `HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection`
- 이름: `ForceDefenderPassiveMode`
- 유형: `REG_DWORD`
- 값: `1`

> [!NOTE]
> 레지스트리 `ForcePassiveMode` 키는 Windows Server 2016에서 지원되지 않습니다.

(<a id="fn2">2)</a>Windows Server 2016에서는 Microsoft가 아닌 바이러스 백신 제품을 설치할 때 Microsoft Defender 바이러스 백신이 자동으로 수동 모드로 전환되지 않습니다. 또한 Microsoft Defender 바이러스 백신은 수동 모드에서 지원되지 않습니다. 이러한 경우 서버에 여러 바이러스 백신 제품을 설치하여 문제를 방지하려면 [Microsoft Defender 바이러스](microsoft-defender-antivirus-on-windows-server.md#are-you-using-windows-server-2016) 백신을 수동으로 사용하지 않도록 설정/제거합니다.

Windows Server 설치에 대한 주요 차이점 및 관리 옵션은 Windows [Server의 Microsoft Defender](microsoft-defender-antivirus-on-windows-server.md) 바이러스 백신을 참조하세요.

> [!IMPORTANT]
> Microsoft Defender 바이러스 백신은 Windows 10, Windows Server 2016, Windows Server, 버전 1803 이상 및 Windows Server 2019를 실행하는 장치에서만 사용할 수 있습니다.
>
> Windows 8.1 및 Windows Server 2012 엔터프라이즈 수준의 끝점 바이러스 백신 보호는 Microsoft Endpoint Configuration Manager를 통해 관리되는 [System Center Endpoint Protection으로](/previous-versions/system-center/system-center-2012-R2/hh508760(v=technet.10))제공됩니다.
>
> Windows Defender Windows [8.1](/previous-versions/windows/it-pro/windows-8.1-and-8/dn344918(v=ws.11)#BKMK_WindowsDefender)및 Windows Server 2012 디바이스에 대해 제공될 수도 있습니다. 그러나 엔터프라이즈 수준 관리(또는 Windows Server 2012 Server Core 설치의 인터페이스)는 제공하지 않습니다.

## <a name="functionality-and-features-available-in-each-state"></a>각 상태의 기능 및 사용 가능한 기능

이 섹션의 표에는 각 상태의 사용 가능한 기능이 요약되어 있습니다. 이 표는 정보 전용으로 디자인됩니다. Microsoft Defender 바이러스 백신이 활성 모드인지& 수동 모드인지 또는 사용하지 않도록 설정/제거되어 있는지에 따라 적극적으로 작동하거나 작동하지 않는 기능을 설명하기 위한 것입니다. 

> [!IMPORTANT]
> 수동 모드에서 Microsoft Defender 바이러스 백신을 사용하거나 차단 모드에서 EDR을 사용하는 경우 실시간 보호, 클라우드 제공 보호 또는 제한된 주기적 검사와 같은 기능을 끄지 않습니다. 

|보호 |활성 모드 |수동 모드 |차단 모드의 EDR |사용 안 되거나 제거 |
|:---|:---|:---|:---|:---|
| [실시간 보호 및](./configure-real-time-protection-microsoft-defender-antivirus.md) [클라우드 제공 보호](./enable-cloud-protection-microsoft-defender-antivirus.md) | 예 | 아니요 <sup> [[3](#fn3)]<sup> | 아니요 | 아니요 |
| [제한된 주기적 검사 가용성](./limited-periodic-scanning-microsoft-defender-antivirus.md) | 아니요 | 아니요 | 아니요 | 예 |
| [파일 검색 및 검색 정보](./customize-run-review-remediate-scans-microsoft-defender-antivirus.md) | 예 | 예 | 예 | 아니요 |
|  [위협 수정](./configure-remediation-microsoft-defender-antivirus.md) | 예 | 참고 <sup> 참조 [[4](#fn4)]<sup> | 예 | 아니요 |
| [보안 인텔리전스 업데이트](./manage-updates-baselines-microsoft-defender-antivirus.md) | 예 | 예 | 예 | 아니요 |

(<a id="fn3">3)</a>일반적으로 Microsoft Defender 바이러스 백신이 수동 모드인 경우 실시간 보호는 활성화되어 있으며 수동 모드에서도 차단 또는 적용을 제공하지 않습니다. 

(<a id="fn4">4)</a>Microsoft Defender 바이러스 백신이 수동 모드인 경우 위협 수정 기능은 예약된 검사 또는 수동 검사 중에만 활성화됩니다.

> [!NOTE]
> [Microsoft 365 엔드포인트](/microsoft-365/compliance/endpoint-dlp-learn-about) 데이터 손실 방지 보호는 Microsoft Defender 바이러스 백신이 활성 모드 또는 수동 모드일 때 정상적으로 작동합니다.

## <a name="keep-the-following-points-in-mind"></a>다음에 유의해야 합니다.

- 활성 모드에서는 Microsoft Defender 바이러스 백신이 컴퓨터의 바이러스 백신 앱으로 사용됩니다. Configuration Manager, 그룹 정책, Intune 또는 기타 관리 제품으로 만든 모든 구성이 적용됩니다. 파일을 검색하고 위협을 해결하며 구성 도구(예: 구성 관리자 또는 컴퓨터 자체의 Microsoft Defender 바이러스 백신 앱)에 검색 정보가 보고됩니다.

- 수동 모드에서는 Microsoft Defender 바이러스 백신이 바이러스 백신 앱으로 사용되지 않습니다. 위협은 Microsoft Defender 바이러스 백신에 의해 해결되지 않습니다. 파일을 검사하고 끝점용 Microsoft Defender 서비스와 공유되는 위협 감지에 대한 보고서가 제공됩니다. 따라서 Microsoft Defender 바이러스 백신이 수동 모드인 경우에도 Microsoft Defender 바이러스 백신이 원본으로 있는 보안 센터 콘솔에서 경고가 발생할 수 있습니다.

- 차단 [모드의 EDR이](/microsoft-365/security/defender-endpoint/edr-in-block-mode) 켜져 있으며 Microsoft Defender 바이러스 백신이 기본 바이러스 백신 솔루션이 아닌 경우 악의적인 항목을 검색하고 치료할 수 있습니다.

- 사용하지 않도록 설정하면 Microsoft Defender 바이러스 백신이 바이러스 백신 앱으로 사용되지 않습니다. 파일을 검사하지 않은 경우 위협이 해결되지 않습니다. 일반적으로 Microsoft Defender 바이러스 백신을 사용하지 않음/제거하지 않는 것이 좋습니다. 가능하면 Microsoft가 아닌 맬웨어 방지/바이러스 백신 솔루션을 사용하는 경우 Microsoft Defender 바이러스 백신을 수동 모드로 유지하세요.

- 끝점용 Microsoft Defender에 등록되어 있으며 타사 맬웨어 방지 제품을 사용하는 경우 수동 모드가 사용하도록 설정됩니다. [이 서비스를 사용하려면 침입](/microsoft-365/security/defender-endpoint/defender-compatibility) 시도 및 공격에 대한 장치 및 네트워크를 제대로 모니터링하기 위해 Microsoft Defender 바이러스 백신 서비스의 일반 정보 공유가 필요합니다.

- Microsoft Defender 바이러스 백신이 자동으로 비활성화되면 비 Microsoft 바이러스 백신 제품에서 제공하는 보호가 만료되거나 바이러스, 맬웨어 또는 기타 위협으로부터 실시간 보호를 제공하는 것을 중지하면 자동으로 다시 활성화할 수 있습니다. 자동 다시 사용하도록 설정하면 장치에서 바이러스 백신 보호가 유지 관리됩니다. 또한 Microsoft Defender [](limited-periodic-scanning-microsoft-defender-antivirus.md)바이러스 백신 엔진을 사용하여 기본 바이러스 백신 앱 외에 위협을 주기적으로 검사하는 제한된 주기적 검사를 사용하도록 설정할 수 있습니다.

- Microsoft Defender 바이러스 백신이 수동 모드인 경우 Microsoft Defender 바이러스 백신에 대한 업데이트를 [관리할 수 있습니다.](manage-updates-baselines-microsoft-defender-antivirus.md) 그러나 장치에 맬웨어로부터 실시간 보호를 제공하는 비 Microsoft 바이러스 백신 제품이 있는 경우 Microsoft Defender 바이러스 백신을 활성 모드로 이동할 수 없습니다. 보안 계층 방어 및 검색 기능을 최적화하기 위해 [Microsoft Defender](./manage-updates-baselines-microsoft-defender-antivirus.md) 바이러스 백신이 수동 모드에서 실행 중인 경우에도 Microsoft Defender 바이러스 백신 보호(보안 인텔리전스 업데이트, 엔진 및 플랫폼)를 업데이트해야 합니다.

   Microsoft가 아닌 바이러스 백신 제품을 제거하고 Microsoft Defender 바이러스 백신을 사용하여 장치에 보호 기능을 제공하는 경우 Microsoft Defender 바이러스 백신은 자동으로 일반 활성 모드로 돌아갑니다.

> [!WARNING]
> Microsoft Defender 바이러스 백신, 끝점용 Microsoft Defender 또는 Windows 보안 앱에서 사용되는 관련 서비스를 비활성화, 중지 또는 수정하지 않습니다. 이 권장에는 *wscsvc,* *SecurityHealthService,* *MsSense,* *Sense,* *WinDefend* 또는 *MsMpEng* 서비스 및 프로세스가 포함됩니다. 이러한 서비스를 수동으로 수정하면 장치에 심각한 문제가 발생할 수 있으며 네트워크가 취약해질 수 있습니다. 이러한 서비스를 사용하지 않고 중지하거나 수정하면 Microsoft가 아닌 바이러스 백신 솔루션을 사용할 때와 해당 정보가 Windows 보안 앱에 표시되는 방법도 문제가 [발생할 수 있습니다.](microsoft-defender-security-center-antivirus.md)


## <a name="see-also"></a>참고 항목

- [Windows 10의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-in-windows-10.md)
- [Windows Server의 Microsoft Defender 바이러스 백신](microsoft-defender-antivirus-on-windows-server.md)
- [차단 모드의 EDR](edr-in-block-mode.md)
- [끝점 보호 구성](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
- [Endpoint용 Microsoft Defender에서 가양성/가음성 처리](defender-endpoint-false-positives-negatives.md)
- [Microsoft 365 끝점 데이터 손실 방지에 대한 자세한 정보](/microsoft-365/compliance/endpoint-dlp-learn-about)
