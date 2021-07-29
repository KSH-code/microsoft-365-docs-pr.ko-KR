---
title: 끝점 장치용 Microsoft Defender 목록 보기 및 구성
description: 조사를 향상하기 위해 목록을 정렬, 필터링 및 내보내기와 같은 장치 목록에서 사용할 수 있는 사용 가능한 기능에 대해 자세히 알아보습니다.
keywords: 정렬, 필터, 내보내기, csv, 장치 이름, 도메인, 마지막으로 본, 내부 IP, 상태, 활성 경고, 활성 맬웨어 감지, 위협 범주, 경고 검토, 네트워크, 연결, 맬웨어, 유형, 암호 도용자, 랜섬웨어, 악용, 위협, 일반 맬웨어, 원치 않는 소프트웨어
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d70825f8bdcd47f17d2f61834f4353c537a033ed
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622571"
---
# <a name="view-and-organize-the-microsoft-defender-for-endpoint-devices-list"></a>끝점 장치용 Microsoft Defender 목록 보기 및 구성

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-machinesview-abovefoldlink)

장치 **목록에는** 경고가 생성된 네트워크의 장치 목록이 표시됩니다. 기본적으로 큐에는 지난 30일 동안의 장치가 표시됩니다.  

도메인, 위험 수준, OS 플랫폼 등의 정보와 가장 위험한 장치를 쉽게 식별할 수 있는 기타 세부 정보를 한눈에 볼 수 있습니다.

장치 목록 보기를 사용자 지정하기 위해 선택할 수 있는 몇 가지 옵션이 있습니다. 위쪽 탐색에서 다음을 할 수 있습니다.

- 열 추가 또는 제거
- 전체 목록 내보내기(CSV 형식)
- 페이지당 표시해야 하는 항목 수 선택
- 필터 적용

온보더링 프로세스 중에  장치 목록은 센서 데이터 보고를 시작하면 디바이스로 점진적으로 채워지고 있습니다. 이 보기를 사용하여 온보드 엔드포인트가 온라인 상태로 전환될 때 추적하거나, 전체 끝점 목록을 오프라인 분석을 위한 CSV 파일로 다운로드합니다.

>[!NOTE]
> 장치 목록을 내보낼 경우 조직의 모든 장치가 포함되어 있습니다. 조직의 규모에 따라 다운로드하는 데 많은 시간이 걸릴 수 있습니다. 목록을 CSV 형식으로 내보내면 데이터가 필터되지 않은 방식으로 표시됩니다. CSV 파일에는 보기 자체에 적용된 필터링에 관계없이 조직의 모든 장치가 포함됩니다.

![장치 목록이 있는 장치 목록의 이미지](images/device-inventory.png)

## <a name="sort-and-filter-the-device-list"></a>장치 목록 정렬 및 필터링

다음 필터를 적용하여 경고 목록을 제한하고 보다 집중적인 보기를 얻을 수 있습니다.

### <a name="risk-level"></a>위험 수준

위험 수준은 장치의 활성 경고 유형 및 심각도 등 여러 요인의 조합에 따라 장치의 전반적인 위험 평가를 반영합니다. 활성 경고를 해결하고, 재구성 활동을 인가하고, 후속 경고를 표시하지는하면 위험 수준이 낮아집니다.

### <a name="exposure-level"></a>노출 수준

노출 수준은 보류 중인 보안 권장 사항의 누적 영향에 따라 장치의 현재 노출을 반영합니다. 가능한 수준은 낮음, 보통 및 높음입니다. 노출이 낮을 경우 장치가 악용에 덜 취약하다는 의미입니다.

노출 수준에 "데이터를 사용할 수 없음"이면 몇 가지 이유가 있을 수 있습니다.

- 장치가 30일 이상 보고를 중지했습니다. 이 경우 비활성으로 간주하고 노출이 계산되지 않습니다.
- 장치 OS가 지원되지 않습니다. [끝점용 Microsoft Defender에 대한 최소 요구 사항 참조](minimum-requirements.md)
- 부실 에이전트가 있는 장치(매우 가능성 낮음)

### <a name="os-platform"></a>OS 플랫폼

조사할 OS 플랫폼만 선택합니다.

### <a name="health-state"></a>상태

다음 장치 상태로 필터링합니다.

- **활성:** 서비스에 센서 데이터를 적극적으로 보고하는 장치입니다.
- **비활성:** 7일 이상 신호 전송을 완전히 중지한 장치입니다.
- **잘못 구성:** 서비스와의 통신이 손상되거나 센서 데이터를 보낼 수 없는 장치입니다. 잘못 구성된 장치는 다음으로 더 분류될 수 있습니다.
  - 센서 데이터 없음
  - 통신 장애

  잘못 구성 된 장치에서 문제를 해결하는 방법에 대한 자세한 내용은 [Unhealthy sensors](fix-unhealthy-sensors.md)를 참조하세요.

### <a name="antivirus-status"></a>바이러스 백신 상태

바이러스 백신 상태를 사용하여 장치를 필터링합니다. 활성 디바이스에만 Windows 10 적용됩니다.

- **사용 안 하게** & 위협 방지가 꺼져 있습니다.
- **보고하지 않습니다.** 위협 & 바이러스 백신이 보고되지 않습니다.
- **업데이트되지** 않습니다. 위협 & 바이러스가 최신이 아닙니다.

자세한 내용은 [View the Threat & Vulnerability Management dashboard를 참조하세요.](tvm-dashboard-insights.md)

### <a name="threat-mitigation-status"></a>위협 완화 상태

특정 위협의 영향을 받을 수 있는 장치를 확인하려면 드롭다운 메뉴에서 위협을 선택한 다음 완화해야 하는 취약성 측면을 선택합니다.

특정 위협에 대한 자세한 내용은 [위협 분석을 참조하세요.](threat-analytics.md) 완화 정보는 위협 및 [& 관리를 참조하세요.](next-gen-threat-and-vuln-mgt.md)

### <a name="windows-10-version"></a>Windows 10 버전

조사할 Windows 10 버전만 선택합니다.

### <a name="tags--groups"></a>태그 & 그룹

개별 장치에 추가한 그룹화 및 태그 지정에 따라 목록을 필터링합니다. 디바이스 태그 만들기 [및 관리](machine-tags.md) 및 장치 그룹 만들기 및 관리를 [참조하세요.](machine-groups.md)

## <a name="related-topics"></a>관련 항목

- [Microsoft Defender for Endpoint Devices 목록에서 장치 조사](investigate-machines.md)
