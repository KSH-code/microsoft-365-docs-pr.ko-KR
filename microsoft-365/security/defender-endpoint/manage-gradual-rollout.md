---
title: Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 관리
description: 서진 업데이트 프로세스 및 컨트롤에 대한 자세한 정보
keywords: 업데이트, 업데이트 프로세스, 컨트롤, 릴리스
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
ms.openlocfilehash: 0a264f16c35a9fe122c2cb62a56c16334fb162d2
ms.sourcegitcommit: d1eb1c26609146ff5a59b2a1b005dd7ac43ae64e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/05/2021
ms.locfileid: "60099708"
---
# <a name="manage-the-gradual-rollout-process-for-microsoft-defender-updates"></a>Microsoft Defender 업데이트에 대한 서진적 출시 프로세스 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**

- [엔드포인트용 Microsoft Defender](/microsoft-365/security/defender-endpoint/)

중요한 보호 기능을 전달하고 공격을 방지하기 위해 클라이언트 구성 요소를 최신으로 유지해야 합니다.

기능은 여러 구성 요소를 통해 제공됩니다.

- [끝점 검색 & 응답](overview-endpoint-detection-response.md)
- [클라우드 제공 보호를](microsoft-defender-antivirus-windows.md) 통해 [차세대 보호](cloud-protection-microsoft-defender-antivirus.md)
- [공격 표면 감소](overview-attack-surface-reduction.md)

업데이트는 서진 릴리스 프로세스를 사용하여 월별 릴리스됩니다. 이 프로세스는 조기 오류 검색이 발생할 때 영향을 catch하고 더 큰 롤아웃 전에 빠르게 해결할 수 있도록 하는 데 도움이 됩니다.

> [!NOTE]
> 일일 보안 인텔리전스 업데이트를 제어하는 방법에 대한 자세한 내용은 Schedule [Microsoft Defender 바이러스 백신 protection updates을 참조하십시오.](manage-protection-update-schedule-microsoft-defender-antivirus.md) 업데이트를 통해 클라우드 제공 보호를 끝점에서 사용할 수 없는 경우에도 차세대 보호가 새로운 위협으로부터 보호할 수 있습니다.

## <a name="microsoft-gradual-rollout-model"></a>Microsoft의 서진적 출시 모델

월별 Defender 업데이트에는 다음과 같은 단계별 출시 모델이 따라야 합니다.

1. 첫 번째 릴리스는 베타 채널 구독자에게 공개됩니다.
2. 유효성 검사, 피드백 및 수정 후 제한된 방식으로 먼저 미리 보기 채널 구독자에게 서서한 롤아웃 프로세스를 시작합니다.
3. 그런 다음 나머지 전역 인구에 대한 업데이트를 계속 릴리스하여 10~100%로 확장합니다.

엔지니어는 지속적으로 영향을 모니터링하고 문제를 에스컬레이터하여 필요한 경우 수정을 생성합니다.

## <a name="how-to-customize-your-internal-deployment-process"></a>내부 배포 프로세스를 사용자 지정하는 방법

컴퓨터는 Windows 업데이트에서 Defender 업데이트를 수신하는 경우 일부 컴퓨터는 다른 컴퓨터보다 더 빨리 Defender 업데이트를 수신하게 될 수 있습니다. 다음 섹션에서는 업데이트 채널 구성을 활용하여 자동 업데이트가 특정 장치 그룹으로 다르게 흐를 수 있도록 하는 전략을 정의하는 방법에 대해 설명합니다.

> [!NOTE]
> 자체의 단계적 릴리스를 계획할 때 미리 보기 및 미리 보기 채널에 구독된 디바이스를 항상 선택해야 합니다. 이렇게 하면 조직뿐만 아니라 Microsoft도 사용자 환경과 관련한 문제를 방지하거나 찾아 해결할 수 있습니다.

WSUS(Windows Server Update Services) 또는 MECM(Microsoft Endpoint Configuration Manager)과 같은 업데이트를 받는 컴퓨터의 경우 끝점용 Microsoft Defender 옵션을 포함하여 모든 Windows 업데이트에 더 많은 옵션을 사용할 수 있습니다.

- WSUS, MECM과 같은 솔루션을 사용하여 업데이트 배포 및 응용 프로그램을 관리하는 방법에 대한 자세한 내용은 [Manage Microsoft Defender 바이러스 백신 updates and apply baselines - Windows 를 읽어 보십시오.](manage-updates-baselines-microsoft-defender-antivirus.md#product-updates)

## <a name="update-channels-for-monthly-updates"></a>월별 업데이트 채널 업데이트

업데이트 채널에 컴퓨터 할당을 통해 컴퓨터는 월별 엔진 및 플랫폼 업데이트를 받는 케이던스를 정의할 수 있습니다.

업데이트를 구성하는 방법에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 사용자 지정점적 출시 프로세스 [만들기를 참조하세요.](configure-updates.md)

다음 업데이트 채널을 사용할 수 있습니다.

<br>

****

|채널 이름|설명|응용 프로그램|
|---|---|---|
|베타 채널 - 시험 출시|다른 사람 앞에 업데이트 테스트|이 채널로 설정된 장치는 새 월별 업데이트를 수신하는 첫 번째 장치입니다. 베타 채널을 선택하여 문제를 식별하고 Microsoft에 보고합니다. Windows 프로그램의 장치는 기본적으로 이 채널을 구독합니다. 테스트 환경에서만 사용됩니다.|
|현재 채널(미리 보기)|서서한 **릴리스의** 이전 현재 채널 업데이트 다운로드|이 채널로 설정된 장치는 서서한 릴리스 주기 동안 가장 빠른 시기에 업데이트를 제공합니다. 프로덕션 전/유효성 검사 환경에 권장됩니다.|
|현재 채널(단계적)|나중에 서서한 릴리스 동안 현재 채널 업데이트 다운로드|디바이스는 나중에 서서한 릴리스 주기 동안 업데이트가 제공됩니다. 디바이스 인구의 대표적인 소규모 부분에 적용하는 것이 좋습니다(~10%).|
|현재 채널(광범위)|서서한 릴리스가 끝날 때 업데이트 다운로드|디바이스는 서서한 릴리스 주기가 완료된 후에만 업데이트를 제공합니다. 프로덕션 인구의 광범위한 디바이스 집합(~10-100%)에 적용하는 것이 좋습니다.|
|중요: 시간 지연|Defender 업데이트 지연|장치에는 48시간이 지연된 업데이트가 제공됩니다. 제한된 업데이트만 수신하는 데이터 센터 머신에 가장 좋습니다. 중요한 환경에만 권장됩니다.|
|기본값||해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 현재 채널(기본값)에 남아 있습니다. 서서히 릴리스 주기 동안 자동으로 최신 상태로 유지됩니다. 대부분의 장치에 적합합니다.|
|

### <a name="update-channels-for-daily-updates"></a>매일 업데이트 채널 업데이트

채널에 컴퓨터 할당을 통해 매일 업데이트를 받는 케이던스를 정의할 수 있습니다. 월별 프로세스와 달리 베타 채널이 없습니다. 이 점진적 릴리스 주기는 매일 여러 번 발생합니다.

<br>

****

|채널 이름|설명|응용 프로그램|
|---|---|---|
|현재 채널(단계적)|나중에 서서한 릴리스 동안 현재 채널 업데이트 다운로드|디바이스는 나중에 서서한 릴리스 주기 동안 업데이트가 제공됩니다. 디바이스 인구의 대표적인 소규모 부분에 적용하는 것이 좋습니다(~10%).|
|현재 채널(광범위)|서서한 릴리스가 끝날 때 업데이트 다운로드|디바이스는 서서한 릴리스 주기 후 업데이트를 제공합니다. 제한된 업데이트만 수신하는 데이터 센터 머신에 가장 좋습니다. 참고: 이 설정은 모든 Defender 업데이트에 적용됩니다.|
|기본값||해당 정책을 사용하지 않도록 설정하거나 구성하지 않는 경우 장치는 현재 채널(기본값)에 남아 있습니다. 서서히 릴리스 주기 동안 자동으로 최신 상태로 유지됩니다. 대부분의 장치에 적합|
|

> [!NOTE]
> 시간 지연을 활용하는 대신 최신 서명을 강제로 업데이트하려면 먼저 이 정책을 제거해야 합니다.

## <a name="update-guidance"></a>업데이트 지침

대부분의 경우 Windows 업데이트 사용 시 권장되는 구성은 끝점이 도착할 때 월별 Defender 업데이트를 수신하고 적용할 수 있도록 하는 것입니다. 이렇게 하면 보호와 적용될 수 있는 변경 내용과 관련된 가능한 영향 간의 최상의 균형을 제공합니다.

자동 Defender 업데이트의 보다 제어된 단계적 배포가 필요한 환경에서는 배포 그룹을 사용할 수 있는 방법을 고려하세요.

1. 베타 Windows 프로그램에 참여하거나 디바이스 그룹을 베타 채널에 할당합니다.
2. 미리 보기 채널(일반적으로 유효성 검사 환경)에 옵트인(opt in)하는 파일럿 그룹을 지정하여 새 업데이트를 조기에 받을 수 있습니다.
3. 단계적 채널의 단계적 출시 중에 나중에 업데이트를 받는 컴퓨터 그룹을 지정합니다. 일반적으로 이 개체는 인구의 10%를 대표하는 것입니다.
4. 서서히 릴리스 주기가 완료된 후 업데이트를 받는 컴퓨터 그룹을 지정합니다. 이는 일반적으로 중요한 프로덕션 시스템입니다.

나머지 장치의 경우 기본 설정은 Microsoft의 서서히 출시 프로세스 중에 도착할 때 새 업데이트를 수신하고 추가 구성이 필요하지 않습니다.

이 모델 채택:

- 프로덕션 환경에 도달하기 전에 초기 릴리스를 테스트할 수 있습니다.
- 프로덕션 환경이 정기적인 업데이트를 계속 받는지 확인하여 중요한 위협으로부터 보호합니다.

## <a name="management-tools"></a>관리 도구

월별 업데이트에 대해 사용자 지정 서서히 출시 프로세스를 직접 만들 수 있는 도구는 다음과 같습니다.

- 그룹 정책
- Microsoft Endpoint Manager
- PowerShell

이러한 도구를 사용하는 방법에 대한 자세한 내용은 Microsoft Defender 업데이트에 대한 사용자 지정점적 출시 프로세스 [만들기를 참조하세요.](configure-updates.md)
