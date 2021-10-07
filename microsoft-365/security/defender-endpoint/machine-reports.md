---
title: 엔드포인트용 Microsoft Defender의 장치 상태 및 준수 보고서
description: 장치 상태 및 준수 보고서를 사용하여 장치 상태 검색, 바이러스 Windows 10 OS 플랫폼 및 버전 추적
keywords: 상태, 바이러스 백신, os 플랫폼, Windows 10 버전, 버전, 상태, 규정 준수, 상태
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 07aec0c4ff4c6ea42fcc6e4bb95357bd98bf5cba
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60162605"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender의 장치 상태 및 준수 보고서

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

장치 상태 보고서는 조직의 장치에 대한 높은 수준의 정보를 제공합니다. 이 보고서에는 센서 상태, 바이러스 백신 상태, OS 플랫폼 및 최신 버전을 보여 Windows 10 포함되어 있습니다.

대시보드는 다음 두 섹션으로 구성됩니다.

![장치 보고서의 이미지입니다.](images/device-reports.png)

<br>

****

|섹션|설명|
|---|---|
|1|디바이스 추세|
|2|장치 요약(현재 일)|
|||

## <a name="device-trends"></a>디바이스 추세

기본적으로 장치 추세는 마지막 전체 일에 끝나는 30일 기간의 장치 정보를 표시합니다. 조직에서 발생하는 추세에 대한 더 나은 관점을 얻기 위해 표시된 기간을 조정하여 보고 기간을 미세 조정할 수 있습니다. 기간을 조정하려면 드롭다운 옵션에서 시간 범위를 선택합니다.

- 30일
- 3개월
- 6개월
- 사용자 지정

> [!NOTE]
> 이러한 필터는 장치 추세 섹션에만 적용됩니다. 장치 요약 섹션에는 영향을 주지 않습니다.

## <a name="device-summary"></a>디바이스 요약

장치 추세는 추세 장치 정보를 표시하는 반면, 장치 요약에는 현재 일자까지의 장치 정보가 표시됩니다.

> [!NOTE]
> 요약 섹션에 반영된 데이터는 현재 날짜 이전 180일로 범위가 지정됩니다. 예를 들어 오늘 날짜가 2019년 3월 27일인 경우 요약 섹션의 데이터에는 2018년 9월 28일에서 2019년 3월 27일까지의 숫자가 반영됩니다.
>
> 추세 섹션에 적용된 필터는 요약 섹션에 적용되지 않습니다.

장치 추세 섹션에서는 해당 필터가 적용된 장치 목록으로 드릴다운할 수 있습니다. 예를 들어 센서 상태 카드에서 비활성 막대를 클릭하면 센서 상태가 비활성 상태인 장치만 표시하는 결과가 있는 장치 목록이 표시됩니다.

## <a name="device-attributes"></a>장치 특성

이 보고서는 다음과 같은 장치 특성을 표시하는 카드로 표시됩니다.

- **상태**: 장치의 센서 상태 정보를 표시하여 활성 상태, 통신 장애가 발생하거나, 비활성 상태 또는 센서 데이터가 없는 경우 집계된 보기를 제공합니다.
- **활성 Windows 10 장치의** 바이러스 백신 상태 : 장치 수와 장치 상태 Microsoft Defender 바이러스 백신.
- **OS 플랫폼**: 조직 내에 있는 OS 플랫폼의 배포를 보여줍니다.
- **Windows 10** 버전 : 조직에서 Windows 10 장치 및 해당 버전의 배포를 보여줍니다.

## <a name="filter-data"></a>데이터 필터링

제공된 필터를 사용하여 특정 특성의 장치를 포함하거나 제외할 수 있습니다.

장치 특성에서 적용할 여러 필터를 선택할 수 있습니다.

> [!NOTE]
> 이러한 필터는 **보고서의 모든** 카드에 적용됩니다.

예를 들어 활성 센서 상태의 Windows 10 장치에 대한 데이터를 표시하는 경우:

1. 필터에서 > 활성 상태인 > **상태입니다.**
2. 그런 다음 **에서 OS 플랫폼을 > Windows 10.**
3. **적용** 을 선택합니다.

## <a name="related-topic"></a>관련 항목

- [위협 방지 보고서](threat-protection-reports.md)
