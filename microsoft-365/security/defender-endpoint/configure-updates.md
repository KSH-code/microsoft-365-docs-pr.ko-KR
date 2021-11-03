---
title: Microsoft Defender 업데이트에 대한 사용자 지정 서진 배포 프로세스 만들기
description: 지원되는 도구를 사용하여 업데이트에 대한 사용자 지정 서진 롤아웃 프로세스를 만드는 방법에 대해 자세히 알아보기
keywords: 업데이트 도구, gpo, intune, mdm, Microsoft 끝점 관리자, 정책, powershell
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 523a73477343bc9face75bcceda1ed603d1f6439
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704634"
---
# <a name="create-a-custom-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender 업데이트에 대한 사용자 지정 서진 배포 프로세스 만들기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> 이 기능을 사용하려면 Microsoft Defender 바이러스 백신 4.18.2106.X 이상 버전이 필요합니다.

Defender 업데이트에 대한 사용자 지정 서서적 출시 프로세스를 직접 만들기 위해 그룹 정책, Microsoft Endpoint Manager 및 PowerShell을 사용할 수 있습니다.

다음 표에는 업데이트 채널 구성에 사용할 수 있는 그룹 정책 설정이 나열되어 있습니다.

<br>

****

|제목 설정|설명|위치|
|---|---|---|
|Microsoft Defender 월별 플랫폼 업데이트 출시 채널 서서히 선택|이 정책을 사용하여 장치가 월별 서진 기간 동안 Microsoft Defender 플랫폼 업데이트를 받는 시기를 지정합니다. <p> 베타 채널: 이 채널로 설정된 장치는 새 업데이트를 수신하는 첫 번째 채널입니다. 베타 채널을 선택하여 문제를 식별하고 Microsoft에 보고합니다. Windows 프로그램의 장치는 기본적으로 이 채널을 구독합니다. (수동) 테스트 환경에서만 사용하며 제한된 수의 장치를 사용합니다. <p> 현재 채널(미리 보기): 이 채널로 설정된 장치는 월별 서진 릴리스 주기 동안 가장 빠른 시간 동안 업데이트를 제공합니다. 프로덕션 전/유효성 검사 환경에 권장됩니다. <p> 현재 채널(단계적): 월별 단계별 릴리스 주기 후에 디바이스에 업데이트가 제공됩니다. 생산 인구의 대표적인 소규모(~10%)에 적용하는 것이 좋습니다. <p> 현재 채널(광범위): 디바이스는 서서한 릴리스 주기가 완료된 후에만 업데이트를 제공합니다. 프로덕션 인구의 광범위한 디바이스 집합(~10-100%)에 적용하는 것이 좋습니다. <p> Critical- Time Delay: 장치에는 48시간이 지연된 업데이트가 제공됩니다. 중요한 환경에만 권장됩니다. <p>해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 서서한 릴리스 주기 동안 자동으로 최신으로 유지됩니다. 대부분의 장치에 적합합니다.|Windows 구성 요소\Microsoft Defender 바이러스 백신|
|Microsoft Defender 월별 엔진 업데이트 출시 채널 서서히 선택|이 정책을 사용하여 장치가 월별 서진 기간 동안 Microsoft Defender 엔진 업데이트를 받는 시기를 지정합니다. <p> 베타 채널: 이 채널로 설정된 장치는 새 업데이트를 수신하는 첫 번째 채널입니다. 베타 채널을 선택하여 문제를 식별하고 Microsoft에 보고합니다. Windows 프로그램의 장치는 기본적으로 이 채널을 구독합니다. (수동) 테스트 환경에서만 사용하며 제한된 수의 장치를 사용합니다. <p> 현재 채널(미리 보기): 이 채널로 설정된 장치는 월별 서진 릴리스 주기 동안 가장 빠른 시간 동안 업데이트를 제공합니다. 프로덕션 전/유효성 검사 환경에 권장됩니다. <p> 현재 채널(단계적): 월별 단계별 릴리스 주기 후에 디바이스에 업데이트가 제공됩니다. 생산 인구의 대표적인 소규모(~10%)에 적용하는 것이 좋습니다. <p> 현재 채널(광범위): 디바이스는 서서한 릴리스 주기가 완료된 후에만 업데이트를 제공합니다. 프로덕션 인구의 광범위한 디바이스 집합(~10-100%)에 적용하는 것이 좋습니다. <p> Critical- Time Delay: 장치에는 48시간이 지연된 업데이트가 제공됩니다. 중요한 환경에만 권장됩니다.<p> 해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 서서한 릴리스 주기 동안 자동으로 최신으로 유지됩니다. 대부분의 장치에 적합합니다.|Windows 구성 요소\Microsoft Defender 바이러스 백신|
|Microsoft Defender 일별 보안 인텔리전스 업데이트 출시 채널의 서서한 선택|이 정책을 사용하여 장치가 매일의 서서한 배포 중에 Microsoft Defender 보안 인텔리전스 업데이트를 받는 시기를 지정합니다. <p> 현재 채널(단계적): 릴리스 주기 후 디바이스에 업데이트가 제공됩니다. 생산 인구의 대표적인 소규모(~10%)에 적용하는 것이 좋습니다. <p> 현재 채널(광범위): 디바이스는 서서한 릴리스 주기가 완료된 후에만 업데이트를 제공합니다. 프로덕션 인구의 광범위한 디바이스 집합(~10-100%)에 적용하는 것이 좋습니다. <p>  해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 매일 릴리스 주기 동안 자동으로 최신으로 유지됩니다. 대부분의 장치에 적합합니다.|Windows 구성 요소\Microsoft Defender 바이러스 백신|
|Microsoft Defender 업데이트의 서서한 배포 사용 안 하세요.|Defender 업데이트의 서서한 배포를 사용하지 않도록 설정하려면 이 정책을 사용하도록 설정하세요. <p> 현재 채널(광범위): 이 채널로 설정된 장치는 서서한 릴리스 주기 동안 마지막으로 업데이트가 제공됩니다. 제한된 업데이트만 수신하는 데이터 센터 머신에 가장 좋습니다. <p> 참고: 이 설정은 월별 및 일별 Defender 업데이트 둘 다에 적용될 뿐만 아니라 플랫폼 및 엔진 업데이트에 대해 이전에 구성한 모든 채널 선택을 다시 의합니다. <p> 해당 정책을 사용하지 않도록 설정하거나 구성하지 않으면 플랫폼 및 엔진 업데이트에 대한 특정 채널에서 달리 지정하지 않는 한 장치가 현재 채널(기본값)에 남아 있습니다. 서서한 릴리스 주기 동안 자동으로 최신을 유지 합니다. 대부분의 장치에 적합합니다.|Windows 구성 요소\Microsoft Defender 바이러스 백신|
|

## <a name="group-policy"></a>그룹 정책

> [!NOTE]
> 업데이트된 Defender ADMX 템플릿이 21H2 릴리스와 함께 Windows 10. 지역화되지 않은 버전은 에서 다운로드할 수 https://github.com/microsoft/defender-updatecontrols 있습니다.

그룹 정책을 [사용하여](/windows/win32/srvnodes/group-policy?redirectedfrom=MSDN) 끝점에서 Microsoft Defender 바이러스 백신 관리할 수 있습니다.

일반적으로 다음 절차에 따라 그룹 정책 설정을 구성하거나 Microsoft Defender 바이러스 백신 수 있습니다.

1. 그룹 정책 관리 컴퓨터의 그룹 정책 관리 콘솔을 열고 구성할 GPO(그룹 정책 개체)를 마우스 오른쪽 단추로 클릭하고 편집을 **클릭합니다.** 

2. 그룹 정책 관리 편집기를 사용하여 컴퓨터 **구성으로 이동하십시오.**

3. 관리 **템플릿 을 클릭합니다.**

4. 트리를 확장하여 **Windows 구성 요소를 > Microsoft Defender 바이러스 백신.**

5. 구성할 설정이 포함된  섹션(이 항목의 표에서 위치)을 확장하고 설정을 두 번 클릭하여 열고 구성을 변경합니다.

6. [평소처럼 업데이트된 GPO를 배포합니다.](https://msdn.microsoft.com/library/ee663280(v=vs.85).aspx)

## <a name="intune"></a>Intune

아래 링크의 지침에 따라 Intune에서 사용자 지정 정책을 만들 수 있습니다.

[Windows 10 디바이스에 대한 사용자 지정 설정 Microsoft Intune - Azure \| Microsoft Docs](/mem/intune/configuration/custom-settings-windows-10)

서서한 롤아웃 프로세스에 사용되는 Defender CSP에 대한 자세한 내용은 [Defender CSP 를 참조하세요.](/windows/client-management/mdm/defender-csp)

## <a name="powershell"></a>PowerShell

`Set-MpPreference`cmdlet을 사용하여 서진 업데이트의 롤아웃을 구성합니다.

다음 매개 변수를 사용합니다.

```powershell
Set-MpPreference
-PlatformUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-EngineUpdatesChannel Beta|Preview|Staged|Broad|Delayed|NotConfigured
-DisableGradualRelease True|False
-SignaturesUpdatesChannel Staged|Broad|NotConfigured
```

예제:

베타 `Set-MpPreference -PlatformUpdatesChannel Beta` 채널에서 도착하도록 플랫폼 업데이트를 구성하는 데 사용할 수 있습니다.

매개 변수 및 매개 변수를 구성하는 방법에 대한 자세한 내용은 [Set-MpPreference (Defender)| Microsoft Docs.](/powershell/module/defender/set-mppreference)
