---
title: 제어된 폴더 액세스로 파일을 암호화하지 않는 랜섬웨어로부터 중요한 폴더 보호
description: 기본 폴더의 파일은 악성 앱에 의해 변경되지 못하게 보호할 수 있습니다. 랜섬웨어가 파일을 암호화하지 못하게 합니다.
keywords: 제어된 폴더 액세스, windows 10, windows defender, 랜섬웨어, 보호, 파일, 폴더
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
audience: ITPro
ms.date: 06/10/2021
ms.reviewer: v-maave
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 19737781f2c22a356da2c237e2f059a362140956
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59222886"
---
# <a name="protect-important-folders-with-controlled-folder-access"></a>제어된 폴더 액세스를 사용하여 중요한 폴더 보호

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="what-is-controlled-folder-access"></a>제어된 폴더 액세스란?

제어된 폴더 액세스는 랜섬웨어와 같은 악성 앱 및 위협으로부터 중요한 데이터를 보호하는 데 도움이 됩니다. 제어된 폴더 액세스는 알려진 신뢰할 수 있는 앱 목록에서 앱을 확인하여 데이터를 보호합니다. Windows Server 2019 및 Windows 10 클라이언트에서 지원되는 제어된 폴더 액세스는 Windows 보안 App, Microsoft Endpoint Configuration Manager 또는 Intune(관리되는 디바이스의 경우)을 사용하여 켜져 있을 수 있습니다.

> [!NOTE]
> 스크립팅 엔진은 신뢰할 수 없습니다. 제어된 보호된 폴더에 대한 액세스를 허용할 수 없습니다. 예를 들어 인증서 및 파일 표시기를 사용하여 허용하는 경우에도 PowerShell은 제어된 폴더 액세스에서 [신뢰되지 않습니다.](/microsoft-365/security/defender-endpoint/indicator-certificates)

제어된 폴더 액세스는 제어된 폴더 액세스 이벤트에 대한 자세한 보고를 제공하고 일반적인 경고 조사 시나리오의 일부로 차단하는 [끝점용 Microsoft Defender와](microsoft-defender-endpoint.md)가장 [잘 작동합니다.](investigate-alerts.md)

> [!TIP]
> 제어된 폴더 액세스 블록은 경고 큐에 [경고를 생성하지 않습니다.](alerts-queue.md) 그러나 고급 헌팅을 사용하는 동안 또는 [](investigate-machines.md)사용자 지정 검색 [](advanced-hunting-overview.md)규칙과 함께 장치 타임라인 보기에서 제어된 폴더 액세스 블록에 대한 정보를 볼 [수 있습니다.](custom-detection-rules.md)

## <a name="how-does-controlled-folder-access-work"></a>제어된 폴더 액세스는 어떻게 작동하나요?

제어된 폴더 액세스는 신뢰할 수 있는 앱이 보호된 폴더에 액세스할 수만 있도록 허용하여 작동합니다. 보호된 폴더는 제어된 폴더 액세스를 구성할 때 지정됩니다. 일반적으로 일반적으로 문서, 그림, 다운로드 등에서 사용되는 폴더와 같이 일반적으로 사용되는 폴더는 제어된 폴더 목록에 포함됩니다.

제어된 폴더 액세스는 신뢰할 수 있는 앱 목록에서 작동합니다. 신뢰할 수 있는 소프트웨어 목록에 포함된 앱은 예상대로 작동됩니다. 목록에 포함되지 않은 앱은 보호된 폴더 내부의 파일을 변경할 수 없습니다.

앱이 보전 및 신뢰도에 따라 목록에 추가됩니다. 조직 전체에서 매우 만연하며 악의적인 것으로 간주되는 동작을 표시하지 않은 앱은 신뢰할 수 있는 앱으로 간주됩니다. 이러한 앱은 목록에 자동으로 추가됩니다.

Configuration Manager 또는 Intune을 사용하여 앱을 신뢰할 수 있는 목록에 수동으로 추가할 수도 있습니다. 앱에 대한 [](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file) 파일 표시기 추가와 같은 추가 작업은 보안 센터 콘솔에서 수행할 수 있습니다.

## <a name="why-controlled-folder-access-is-important"></a>제어된 폴더 액세스가 중요한 이유

제어된 폴더 액세스는 랜섬웨어로부터 문서 및 정보를 보호하는 데 [특히 유용합니다.](https://www.microsoft.com/wdsi/threats/ransomware) 랜섬웨어 공격에서 파일은 암호화되고 인질로 보호될 수 있습니다. 제어된 폴더 액세스가 적용된 경우 앱이 보호된 폴더의 파일을 변경하려고 시도한 컴퓨터에 알림이 표시됩니다. 회사 세부 정보 및 연락처 정보로 [알림을 사용자 지정](customize-attack-surface-reduction.md#customize-the-notification)할 수 있습니다. 규칙을 개별적으로 사용하도록 설정하여 기능에서 모니터링하는 기술을 사용자 지정할 수도 있습니다.

보호된 [폴더에는](#review-controlled-folder-access-events-in-windows-event-viewer) 일반적인 시스템 폴더(부팅 섹터 포함)가 포함되고 폴더를 더 추가할 [수 있습니다.](customize-controlled-folders.md#protect-additional-folders) 앱에서 보호된 [폴더에](customize-controlled-folders.md#allow-specific-apps-to-make-changes-to-controlled-folders) 대한 액세스 권한을 부여하도록 허용할 수도 있습니다.

감사 모드를 [사용하여](audit-windows-defender.md) 제어된 폴더 액세스가 사용하도록 설정된 경우 조직에 어떤 영향을 미치는지 평가할 수 있습니다. 또한 Windows Defender 테스트 demo.wd.microsoft.com 웹 사이트를 [](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 방문하여 기능이 작동하는지 확인하고 작동 방법을 확인할 수 있습니다.

제어된 폴더 액세스는 다음 버전의 폴더에서 Windows.

- [Windows 10 버전 1709](/windows/whats-new/whats-new-windows-10-version-1709) 이상
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

## <a name="windows-system-folders-are-protected-by-default"></a>Windows 폴더는 기본적으로 보호됩니다.

Windows 폴더는 기본적으로 몇 가지 다른 폴더와 함께 보호됩니다.

- `c:\Users\<username>\Documents`
- `c:\Users\Public\Documents`
- `c:\Users\<username>\Pictures`
- `c:\Users\Public\Pictures`
- `c:\Users\Public\Videos`
- `c:\Users\<username>\Videos`
- `c:\Users\<username>\Music`
- `c:\Users\Public\Music`
- `c:\Users\<username>\Favorites`

> [!NOTE]
> 추가 폴더를 보호된 폴더로 구성할 수는 있지만 기본적으로 보호되는 Windows 폴더는 제거할 수 없습니다.

## <a name="requirements-for-controlled-folder-access"></a>제어된 폴더 액세스에 대한 요구 사항

제어된 폴더 액세스를 사용하려면 실시간 Microsoft Defender 바이러스 백신 [활성화해야 합니다.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)

## <a name="review-controlled-folder-access-events-in-the-microsoft-365-defender-portal"></a>웹 사이트 포털에서 제어된 폴더 액세스 Microsoft 365 Defender 검토

Endpoint용 Defender는 이벤트에 대한 자세한 보고를 [](investigate-alerts.md) 제공하며, 이벤트 포털에서 경고 조사 시나리오의 일부로 Microsoft 365 Defender 차단합니다. (자세한 내용은 [Microsoft Defender for Endpoint를 Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md)참조).

고급 헌팅을 사용하여 Microsoft Defender에서 끝점 데이터를 [쿼리할 수 있습니다.](/microsoft-365/security/defender-endpoint/advanced-hunting-windows-defender-advanced-threat-protection) 감사 모드를 사용하는 [](audit-windows-defender.md)경우 고급 헌팅을 사용하여 제어된 폴더 액세스 설정이 사용하도록 설정된 경우 환경에 어떤 영향을 주는지 볼 수 있습니다. [](advanced-hunting-overview.md)

쿼리 예제:

```PowerShell
DeviceEvents
| where ActionType in ('ControlledFolderAccessViolationAudited','ControlledFolderAccessViolationBlocked')
```

## <a name="review-controlled-folder-access-events-in-windows-event-viewer"></a>이벤트 뷰어에서 제어된 폴더 액세스 Windows 검토

제어된 Windows 로그를 검토하여 제어된 폴더 액세스가 앱을 차단(또는 감사)할 때 생성되는 이벤트를 볼 수 있습니다.

1. 평가 [패키지를](https://aka.ms/mp7z2w) 다운로드하고  디바이스에서cfa-events.xml쉽게 액세스할 수 있는 위치에 파일을 추출합니다.
2. 이벤트 **뷰어를** 시작 메뉴 이벤트 뷰어를 Windows 합니다.
3. 왼쪽 패널의 **동작에서** 사용자 지정 보기 **가져오기... 를 선택합니다.**
4. 추출한 위치로 *이동하여cfa-events.xml* 선택합니다. 또는 [XML을 직접 복사합니다.](event-views.md)
5. **확인** 을 선택합니다.

다음 표에는 제어된 폴더 액세스와 관련된 이벤트가 표시됩니다.

<br>

****

|이벤트 ID|설명|
|---|---|
|5007|설정이 변경될 때의 이벤트|
|1124|감사된 제어된 폴더 액세스 이벤트|
|1123|차단된 제어된 폴더 액세스 이벤트|
|

## <a name="view-or-change-the-list-of-protected-folders"></a>보호된 폴더 목록 보기 또는 변경

앱 앱을 Windows 보안 제어된 폴더 액세스로 보호되는 폴더 목록을 볼 수 있습니다.

1. 디바이스에서 Windows 10 앱을 Windows 보안 를 니다.
2. **바이러스 및 위협 방지** 를 선택합니다.
3. **랜섬웨어 보호에서** **랜섬웨어** 보호 관리를 선택합니다.
4. 제어된 폴더 액세스가 꺼져 있는 경우 이를 켜야 합니다. 보호된 **폴더를 선택합니다.**
5. 다음 단계 중 하나를 실행합니다.
   - 폴더를 추가하려면 **+ 보호된 폴더 추가를 선택합니다.**
   - 폴더를 제거하려면 폴더를 선택하고 제거 를 **선택합니다.**

> [!NOTE]
> [Windows 시스템](#windows-system-folders-are-protected-by-default) 폴더는 기본적으로 보호되어 있으며 목록에서 제거할 수 없습니다.
