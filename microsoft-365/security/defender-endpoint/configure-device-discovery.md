---
title: 장치 검색 구성
description: 기본 검색 또는 표준 검색을 사용하여 Microsoft 365 Defender 장치 검색을 구성하는 방법 학습
keywords: 기본, 표준, 끝점 검색 구성, 장치 검색
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
ms.openlocfilehash: 261f5128c0ef26843f20e1d94b26ba86f0850349
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192982"
---
# <a name="configure-device-discovery"></a>장치 검색 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

검색은 표준 모드 또는 기본 모드로 구성할 수 있습니다. 표준 옵션을 사용하여 네트워크에서 장치를 적극적으로 찾으면 끝점 검색을 보다 잘 보장하고 더 풍부한 장치 분류를 제공할 수 있습니다.

표준 검색을 수행하는 데 사용되는 장치 목록을 사용자 지정할 수 있습니다. 이 기능을 지원하는 모든 온보드 디바이스(현재 - Windows 10 장치만 해당)에서 표준 검색을 사용하도록 설정하거나 장치 태그를 지정하여 장치의 하위 집합 또는 하위 집합을 선택할 수 있습니다.

> [!IMPORTANT]
> 미리 보기의 경우 먼저 미리 보기에서 미리 보기 기능을 켜야 Microsoft 365 Defender.
> 그런 다음 보안 센터에서 장치 검색 구성에 액세스할 Microsoft 365 있습니다. 관리되지 않는 장치 및 보안 권장 사항 목록은 Microsoft 365 Defender 및 Microsoft 365 보안 센터에서 사용할 수 있으며 대시보드 타일은 Microsoft 365 보안 센터에서만 사용할 수 있습니다.

보안 센터에서 다음 구성 Microsoft 365 수행합니다.

1. 장치 **검색 설정 > 로 이동합니다.**
2. 온보드 디바이스에서 사용할 검색 모드를 선택합니다.
3. 표준 검색을 사용하기로 선택한 경우 해당 장치 태그를 지정하여 활성 프로비전에 사용할 장치(모든 장치 또는 하위 집합)를 선택합니다.
4. **저장** 을 클릭합니다.

## <a name="exclude-devices-from-being-actively-probed-in-standard-discovery"></a>표준 검색에서 디바이스가 적극적으로 프로브되지 못하게 제외

네트워크에 적극적으로 검사하지 말아야 하는 장치(예: 다른 보안 도구의 허니팟으로 사용되는 장치)가 있는 경우 제외 목록을 정의하여 검사하지 못하게 할 수도 있습니다. 기본 검색 모드를 사용하여 디바이스를 검색할 수 있습니다. 이러한 디바이스는 수동적으로 검색되지만 적극적으로 프로브되지 않습니다.

## <a name="select-networks-to-monitor"></a>모니터링할 네트워크 선택

 끝점용 Microsoft Defender는 네트워크를 분석하여 모니터링해야 하는 회사 네트워크인지 또는 무시할 수 있는 회사 네트워크가 아닌 네트워크인지 확인합니다. 회사 네트워크는 일반적으로 모니터링할 수 있는 것으로 선택됩니다. 그러나 온보드 장치가 있는 회사 네트워크가 아닌 네트워크를 모니터링하기로 선택하여 이 결정을 다시 정할 수 있습니다.

모니터링할 네트워크를 지정하여 장치 검색을 수행할 수 있는 위치를 구성할 수 있습니다. 네트워크가 모니터링될 때 디바이스 검색을 수행할 수 있습니다.

장치 검색을 수행할 수 있는 네트워크 목록이 모니터링된 네트워크 **페이지에 표시됩니다.**

> [!NOTE]
> 네트워크 목록에서는 연결된 장치 수에 따라 상위 50개 네트워크만 사용할 수 있습니다.

모니터링된 네트워크 목록은 지난 7일 동안 네트워크에 표시된 총 장치 수를 기준으로 정렬됩니다.

필터를 적용하여 다음 네트워크 검색 상태 중 원하는 경우를 볼 수 있습니다.

- **모니터링된 네트워크** - 장치 검색이 수행되는 네트워크.
- **무시된 네트워크** - 이 네트워크는 무시되고 디바이스 검색이 수행되지 않습니다.
- **모두** - 모니터링된 네트워크와 무시된 네트워크가 모두 표시됩니다.

### <a name="configure-the-network-monitor-state"></a>네트워크 모니터 상태 구성

디바이스 검색이 진행되는 위치를 제어할 수 있습니다. 모니터링된 네트워크는 장치 검색이 수행될 위치로, 일반적으로 회사 네트워크입니다. 네트워크를 무시하거나 상태를 수정한 후 초기 검색 분류를 선택할 수도 있습니다.

초기 검색 분류를 선택하면 기본 시스템 구성 네트워크 모니터 상태를 적용하는 것입니다. 기본 시스템 구성 네트워크 모니터 상태를 선택하면 회사로 식별된 네트워크가 모니터링되고 회사가 아닌 것으로 식별된 네트워크는 자동으로 무시됩니다.

1. 장치 **설정 > 를 선택합니다.**
2. 모니터링된 **네트워크를 선택합니다.**
3. 네트워크 목록을 시청하세요.
4. 네트워크 이름 옆의 세 점을 선택합니다.
5. 초기 검색 분류를 모니터링할지, 무시할지 또는 사용할지 여부를 선택해야 합니다.

    > [!WARNING]
    >
    > - 회사 네트워크로 Microsoft Defender for Endpoint에서 식별되지 않은 네트워크를 모니터링하기로 선택하면 회사 네트워크 외부에서 장치 검색이 발생할 수 있으므로 홈 또는 기타 회사용이 아닌 장치를 검색할 수 있습니다.
    > - 네트워크를 무시하기로 선택하면 네트워크에서 장치 모니터링 및 검색이 중지됩니다. 이미 검색된 장치는 인벤토리에서 제거되지 않지만 더 이상 업데이트되지 않습니다. 끝점용 Defender의 데이터 보존 기간이 만료될 때까지 세부 정보가 보존됩니다.
    > - 회사 네트워크가 아닌 네트워크를 모니터링하도록 선택하기 전에 해당 작업을 할 수 있는 권한이 있어야 합니다. <br>

6. 변경하려는지 확인

## <a name="explore-devices-in-the-network"></a>네트워크에서 디바이스 탐색

다음 고급 헌팅 쿼리를 사용하여 네트워크 목록에 설명된 각 네트워크 이름에 대한 더 많은 컨텍스트를 얻을 수 있습니다. 이 쿼리에는 지난 7일 이내에 특정 네트워크에 연결된 모든 온보드 장치가 나열됩니다.

```kusto
DeviceNetworkInfo
| where Timestamp > ago(7d)
| where ConnectedNetworks  != ""
| extend ConnectedNetworksExp = parse_json(ConnectedNetworks)
| mv-expand bagexpansion = array ConnectedNetworks=ConnectedNetworksExp
| extend NetworkName = tostring(ConnectedNetworks ["Name"]), Description = tostring(ConnectedNetworks ["Description"]), NetworkCategory = tostring(ConnectedNetworks ["Category"])
| where NetworkName == "<your network name here>"
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="get-information-on-device"></a>디바이스에 대한 정보 얻기

다음 고급 헌팅 쿼리를 사용하여 특정 장치에 대한 최신 전체 정보를 얻을 수 있습니다.

```kusto
DeviceInfo
| where DeviceName == "<device name here>" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId
```

## <a name="see-also"></a>참고 항목

- [장치 검색 개요](device-discovery.md)
- [장치 검색 FAQ](device-discovery-faq.md)
