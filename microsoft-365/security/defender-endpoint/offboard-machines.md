---
title: Microsoft Defender ATP 서비스에서 장치 오프보딩
description: Microsoft Defender ATP 서비스에서 Windows 10 장치, 서버, 비 Windows 장치 온보딩
keywords: 오프보딩, 끝점 오프보딩용 Microsoft Defender, Windows atp 오프보딩
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: db22a19da58ba70ff09af781ca56e0b3c0d88dfd
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069215"
---
# <a name="offboard-devices-from-the-microsoft-defender-for-endpoint-service"></a>Microsoft Defender for Endpoint Service에서 장치 오프보딩

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**플랫폼**
- macOS
- Linux
- Windows Server 2012 R2
- Windows Server 2016

>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-offboarddevices-abovefoldlink)

기본 배포 방법에 따라 해당 지침을 따릅니다.

>[!NOTE]
> 장치 상태는 오프보더 후 [7일](fix-unhealthy-sensors.md#inactive-devices) 후에 비활성으로 전환됩니다. <br> 오프보더된 장치의 데이터(예: 타임라인, 경고, 취약성 등)는 구성된 보존 기간이 만료될 때까지 [포털에](data-storage-privacy.md#how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy) 유지됩니다. <br>
> 디바이스의 프로필(데이터 없이)은 180일 이상 장치 목록에 남아 있습니다. [](machines-view-overview.md)
> 또한 지난 30일 동안 활성이 아닌 장치는 조직의 위협 및 취약성 관리 노출 점수와 장치용 Microsoft 보안 점수를 반영하는 데이터에 반영되지 않습니다. [](tvm-exposure-score.md) <br>
> 활성 장치만 표시하려면 상태, [](machines-view-overview.md#health-state)장치 [](machine-tags.md) 태그 또는 컴퓨터 그룹 을 [필터링할 수 있습니다.](machine-groups.md) 

## <a name="offboard-windows-10-devices"></a>Windows 10 장치 오프보드
- [로컬 스크립트를 사용하여 디바이스 오프보딩](configure-endpoints-script.md#offboard-devices-using-a-local-script)
- [그룹 정책을 사용하여 디바이스 오프보드](configure-endpoints-gp.md#offboard-devices-using-group-policy)
- [모바일 장치 관리 도구를 사용하여 장치 오프보드](configure-endpoints-mdm.md#offboard-and-monitor-devices-using-mobile-device-management-tools)

## <a name="offboard-servers"></a>오프보드 서버
- [오프보드 서버](configure-server-endpoints.md#offboard-windows-servers)

## <a name="offboard-non-windows-devices"></a>비 Windows 장치 온보드
- [비 Windows 장치 온보드](configure-endpoints-non-windows.md#offboard-non-windows-devices)

