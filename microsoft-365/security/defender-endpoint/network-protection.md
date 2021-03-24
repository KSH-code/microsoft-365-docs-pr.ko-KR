---
title: 네트워크 보호를 사용하여 잘못된 사이트에 대한 연결 방지
description: 사용자가 알려진 악성 및 의심스러운 네트워크 주소에 액세스하지 못하게 하여 네트워크 보호
keywords: 네트워크 보호, 악용, 악성 웹 사이트, ip, 도메인, 도메인
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.date: 03/08/2021
ms.openlocfilehash: b6069d392da1b8610d018908d172dc27044baffc
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069380"
---
# <a name="protect-your-network"></a>네트워크 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

네트워크 보호는 인터넷 기반 이벤트에서 장치의 공격 표면을 줄이는 데 도움이 됩니다. 이를 통해 직원이 응용 프로그램을 사용하여 인터넷에서 피싱 사기, 악용 및 기타 악성 콘텐츠를 호스팅할 수 있는 위험한 도메인에 액세스할 수 없습니다. 네트워크 보호는 Microsoft [Defender SmartScreen의](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) 범위를 확장하여 신뢰도가 낮은 원본(도메인 또는 호스트 이름 기반)에 연결하려고 하는 모든 아웃바운드 HTTP 트래픽을 차단합니다.

네트워크 보호는 Windows 10 버전 1709부터 Windows에서 지원됩니다. 

네트워크 보호를 사용하도록 설정하는 방법에 대한 자세한 내용은 네트워크 보호 사용 [을 참조하세요.](enable-network-protection.md) 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.

> [!TIP]
> 네트워크 보호가 작동하는 방법을 demo.wd.microsoft.com Microsoft [Defender](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) ATP 테스트그라운드 사이트를 참조하세요.

네트워크 보호는 Exploit Protection 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-advanced-threat-protection) [가장 잘 작동합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

네트워크 보호가 연결을 차단하면 알림 센터에서 알림이 표시됩니다. 보안 운영 팀은 조직의 [세부](customize-attack-surface-reduction.md#customize-the-notification) 정보 및 연락처 정보로 알림을 사용자 지정할 수 있습니다. 또한 모니터링할 특정 기술에 맞게 개별 공격 표면 감소 규칙을 사용하도록 설정하고 사용자 정의할 수 있습니다.

감사 모드를 [사용하여](audit-windows-defender.md) 네트워크 보호가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수도 있습니다.

## <a name="requirements"></a>요구 사항

네트워크 보호에는 Windows 10 Pro 또는 Enterprise 및 Microsoft Defender 바이러스 백신 실시간 보호가 필요합니다.

| Windows 버전 | Microsoft Defender 바이러스 백신 |
|:---|:---|
| Windows 10 버전 1709 이상 <p>Windows Server 1803 이상 | [Microsoft Defender 바이러스 백신 실시간 보호](https://docs.microsoft.com/windows/security/threat-protection/configure-real-time-protection-microsoft-defender-antivirus.md) 및 클라우드 [제공](https://docs.microsoft.com/windows/security/threat-protection/enable-cloud-protection-microsoft-defender-antivirus.md) 보호를 사용하도록 설정해야 합니다. |

서비스를 사용하도록 설정한 후 서비스와 장치(끝점이라고도 하는) 간의 연결을 허용하도록 네트워크 또는 방화벽을 구성해야 할 수 있습니다.  

- .smartscreen.microsoft.com
- .smartscreen-prod.microsoft.com

## <a name="review-network-protection-events-in-the-microsoft-defender-for-endpoint-security-center"></a>Microsoft Defender for Endpoint 보안 센터에서 네트워크 보호 이벤트 검토

끝점용 Microsoft Defender는 이벤트에 대한 자세한 보고를 제공하며 경고 조사 시나리오의 일부로 [차단합니다.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/investigate-alerts)

고급 헌팅을 사용하여 Microsoft Defender에서 끝점 데이터를 [쿼리할 수 있습니다.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-windows-defender-advanced-threat-protection) 감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 네트워크 보호 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다.

다음은 예제 쿼리입니다.

```kusto
DeviceEvents
| where ActionType in ('ExploitGuardNetworkProtectionAudited','ExploitGuardNetworkProtectionBlocked')
```

## <a name="review-network-protection-events-in-windows-event-viewer"></a>Windows 이벤트 뷰어에서 네트워크 보호 이벤트 검토

Windows 이벤트 로그를 검토하여 네트워크 보호가 악성 IP 또는 도메인에 대한 액세스를 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.

1. [XML을 직접 복사합니다.](event-views.md)

2. **확인** 을 선택합니다.

이 절차에서는 네트워크 보호와 관련된 다음 이벤트만 표시하기 위해 필터를 지정하는 사용자 지정 보기를 만듭니다.

| 이벤트 ID | 설명 |
|:---|:---|
| 5007 | 설정이 변경될 때의 이벤트 |
| 1125 | 감사 모드에서 네트워크 보호가 발생 하는 경우 이벤트 |
| 1126 | 차단 모드에서 네트워크 보호가 발생하면 이벤트 |

## <a name="related-articles"></a>관련 문서

- [네트워크 보호 |](evaluate-network-protection.md) 기능의 작동 방식과 일반적으로 만들어지게 될 이벤트를 보여줄 수 있는 빠른 시나리오를 진행합니다.

- [네트워크 보호 기능](enable-network-protection.md) | 그룹 정책, PowerShell 또는 MDM CSP를 사용하여 네트워크에서 네트워크 보호를 사용하도록 설정하고 관리할 수 있습니다.
