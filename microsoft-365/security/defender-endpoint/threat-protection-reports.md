---
title: 엔드포인트용 Microsoft Defender의 위협 방지 보고서
description: 위협 방지 보고서를 사용하여 경고 감지, 범주 및 심각도 추적
keywords: 경고 검색, 원본, 범주별 경고, 경고 심각도, 경고 분류, 결정
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
ms.openlocfilehash: 4413c536eb5ee1b748996c21891a9801c6488fc2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159345"
---
# <a name="threat-protection-report-in-microsoft-defender-for-endpoint"></a>엔드포인트용 Microsoft Defender의 위협 방지 보고서

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)

위협 방지 보고서는 조직에서 생성된 경고에 대한 높은 수준의 정보를 제공합니다. 이 보고서에는 검색 원본, 범주, 심각도, 상태, 분류 및 시간 경과에 대한 경고 확인을 보여주는 추세 정보가 포함되어 있습니다.

대시보드는 다음 두 섹션으로 구성됩니다.

![위협 방지 보고서의 이미지입니다.](images/threat-protection-reports.png)

섹션|설명
---|---
1|경고 추세
2|경고 요약

## <a name="alert-trends"></a>경고 추세
기본적으로 경고 추세는 마지막 전체 일에 끝나는 30일 기간의 경고 정보를 표시합니다. 조직에서 발생하는 추세에 대한 더 나은 관점을 얻기 위해 표시된 기간을 조정하여 보고 기간을 미세 조정할 수 있습니다. 기간을 조정하려면 드롭다운 옵션에서 시간 범위를 선택합니다.

- 30일
- 3개월
- 6개월
- 사용자 지정

> [!NOTE]
> 이러한 필터는 경고 추세 섹션에만 적용됩니다. 경고 요약 섹션에는 영향을 주지 않습니다.

## <a name="alert-summary"></a>경고 요약

경고 추세는 추세 경고 정보를 표시하는 반면, 경고 요약에는 현재 일자까지의 경고 정보가 표시됩니다.

 경고 요약을 사용하면 해당 필터가 적용된 특정 경고 큐로 드릴다운할 수 있습니다. 예를 들어 검색 원본 카드에서 EDR 표시줄을 클릭하면 경고 큐에 알림 큐가 표시될 수 있습니다. 이 경우 검색된 검색에서 생성된 경고만 EDR 표시됩니다.

> [!NOTE]
> 요약 섹션에 반영된 데이터는 현재 날짜 이전 180일로 범위가 지정됩니다. 예를 들어 오늘 날짜가 2019년 11월 5일인 경우 요약 섹션의 데이터에는 2019년 5월 5일부터 2019년 11월 5일까지의 숫자가 반영됩니다.
>
> 추세 섹션에 적용된 필터는 요약 섹션에 적용되지 않습니다.

## <a name="alert-attributes"></a>경고 특성

보고서는 다음과 같은 경고 특성을 표시하는 카드로 생성됩니다.

- **검색 원본**: 경고를 트리거하기 위해 끝점용 Microsoft Defender에서 사용하는 데이터를 제공하는 센서 및 감지 기술에 대한 정보를 보여줍니다.
- **위협 범주**: 경고를 트리거한 위협 또는 공격 활동의 유형을 표시하여 보안 작업에 대한 가능한 포커스 영역을 보여줍니다.
- **심각도**: 경고의 심각도 수준을 표시하여 조직에 위협이 미칠 수 있는 총체적인 영향과 경고를 해결하기 위해 필요한 대응 수준을 표시합니다.
- **상태**: 수동 경고 응답의 효율성과 자동화된 수정(활성화된 경우)의 효율성을 나타내는 경고의 해결 상태를 보여 줍니다.
- **분류 & 결정**: 해결 시 경고를 분류한 방법, 실제 위협(실제 경고) 또는 잘못된 검색(거짓 경고)으로 분류한 방법을 보여줍니다. 또한 이러한 카드는 확인된 경고의 확인을 보여 주며, 발견된 실제 위협 유형 또는 잘못 감지된 합법적인 활동과 같은 추가 정보를 제공합니다.

## <a name="filter-data"></a>데이터 필터링

제공된 필터를 사용하여 특정 특성의 경고를 포함하거나 제외할 수 있습니다.

> [!NOTE]
> 이러한 필터는 **보고서의 모든** 카드에 적용됩니다.

예를 들어 심각도 높은 경고에 대한 데이터만 표시하는 경우:

1. **인시던트 및 &** 경고 필터에서 심각도 > \>  \> 높음 을 **선택합니다.**
2. 심각도에 있는 다른 모든 **옵션이** 선택을 하지 않도록 합니다.
3. **적용** 을 선택합니다.

## <a name="related-topic"></a>관련 항목

- [디바이스 상태 및 규정 준수 보고서](machine-reports.md)
