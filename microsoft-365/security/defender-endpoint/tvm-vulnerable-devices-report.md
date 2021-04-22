---
title: 취약한 장치 보고서 - 위협 및 취약성 관리
description: 취약한 장치 추세 및 현재 통계를 보여주는 보고서입니다. 목표는 장치 노출의 숨과 범위를 이해하는 데 있습니다.
keywords: Endpoint-tvm 취약 디바이스용 Microsoft Defender, 끝점용 Microsoft Defender, tvm, 위협 & 노출 감소, 위협 및 취약성 감소, 보안 구성 모니터링
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4b2b581d570bd0924970a845c66a599495ff9829
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933712"
---
# <a name="vulnerable-devices-report---threat-and-vulnerability-management"></a>취약한 장치 보고서 - 위협 및 취약성 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [위협 및 취약점 관리](next-gen-threat-and-vuln-mgt.md)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

이 보고서에는 취약한 장치 추세 및 현재 통계가 있는 그래프 및 막대 차트가 표시됩니다. 목표는 장치 노출의 숨과 범위를 이해하는 데 있습니다. 

보고서 및 취약한 장치로 > **Microsoft Defender 보안 센터의 보고서에 액세스**

두 개의 열이 있습니다.

- 추세(시간 경과에 따라) 지난 30일, 3개월, 6개월 또는 사용자 지정 날짜 범위를 표시 할 수 있습니다.
- 오늘(현재 정보)

**필터:** 취약성 심각도 수준, 악용 가용성, 취약성 사용 시간, 운영 체제 플랫폼, Windows 10 버전 또는 장치 그룹별로 데이터를 필터링할 수 있습니다.

**드릴다운:** 추가 탐색할 인사이트가 있는 경우 관련 막대 차트를 선택하여 장치 인벤토리 페이지에서 필터링된 장치 목록을 확인합니다. 이 목록에서 목록을 내보낼 수 있습니다.

## <a name="severity-level-graphs"></a>심각도 수준 그래프

각 장치는 해당 디바이스에서 발견되는 가장 심각한 취약점에 따라 한 번만 계산됩니다.

![현재 장치 취약성 심각도 수준의 그래프 1개와 시간의 따라 수준을 표시하는 그래프 1개](images/tvm-report-severity.png)

## <a name="exploit-availability-graphs"></a>Exploit availability graphs

각 장치는 알려진 가장 높은 수준의 악용에 따라 한 번만 계산됩니다.

![현재 장치 악용 가용성의 그래프 하나와 시간의 따라 가용성을 보여 주는 그래프 한 개](images/tvm-report-exploit-availability.png)

## <a name="vulnerability-age-graphs"></a>취약성 연령 그래프

각 장치는 가장 오래된 취약점 게시 날짜에 한 번만 계산됩니다. 오래된 취약성은 악용 가능성이 더 높습니다.

![현재 장치 취약성 연령의 그래프 1개와 시간이 지난 기간을 보여주는 그래프 한 개.](images/tvm-report-age.png)

## <a name="vulnerable-devices-by-operating-system-platform-graphs"></a>운영 체제 플랫폼 그래프를 통해 취약한 장치

소프트웨어 취약성으로 인해 노출되는 각 운영 체제의 장치 수입니다.

![운영 체제 플랫폼을 통해 현재 취약한 장치의 그래프 한 개와 시간이 지날 때 OS 플랫폼에 의해 취약한 장치를 보여주는 그래프 하나.](images/tvm-report-os.png)

## <a name="vulnerable-devices-by-windows-10-version-graphs"></a>Windows 10 버전 그래프의 취약한 장치

취약한 응용 프로그램 또는 OS로 인해 노출되는 각 Windows 10 버전의 장치 수입니다.

![Windows 10 버전당 현재 취약한 장치 그래프 한 개와 Windows 10 버전에 의해 시간이 지날 때 취약한 디바이스를 보여주는 그래프 한 개.](images/tvm-report-version.png)

## <a name="related-topics"></a>관련 항목

- [위협 및 취약성 관리 개요](next-gen-threat-and-vuln-mgt.md)
- [보안 권장 사항](tvm-security-recommendation.md)
