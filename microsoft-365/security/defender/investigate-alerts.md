---
title: Microsoft 365 Defender에서 경고 조사
description: 여러 장치, 사용자 및 사서함에 걸쳐 경고를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 989574a860bea798c48e077f5633c31eb857e85e
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500943"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 경고 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease](../includes/prerelease.md)]

경고는 모든 인시던트의 기반이 며 사용자 환경에서 악의적 또는 의심스러운 이벤트가 발생하는 것을 나타냅니다. 경고는 일반적으로 더 광범위한 공격의 일부로, 인시던트에 대한 단서를 제공합니다.

Microsoft 365 Defender에서 관련 경고는 인시던트 형성을 위해 함께 집계됩니다. 인시던트는 항상 공격의 광범위한 컨텍스트를 제공하겠지만, 심층 분석이 필요한 경우 경고 조사가 중요할 수 있습니다. 



## <a name="using-alert-pages-in-investigations"></a>조사에서 경고 페이지 사용

인시던트 페이지의 경고 탭에서 알림을 선택하면 개별 경고 페이지로 이동합니다. 경고 페이지는 영향을 받는 자산, 경고 스토리 및 세부 정보 창의 세 섹션으로 구성됩니다.

![경고 예제 페이지 이미지](../../media/new-alert-page2.png)

경고 페이지 전체에서 엔터티 옆에 있는 3개의 점 아이콘(**...**)을 선택하여 특정 자산 페이지를 열거나 특정 수정 단계를 수행하는 등 사용 가능한 작업을 볼 수 있습니다.

### <a name="analyze-affected-assets"></a>영향을 받는 자산 분석
영향을 받는 자산 섹션에는 사서함, 장치 및 이 경고의 영향을 받는 사용자가 나열됩니다. 자산 카드를 선택하면 세부 정보 쪽 창에 자산과 관련된 다른 경고(있는 경우)가 포함 된 정보를 채우게 됩니다.


### <a name="trace-an-alerts-role-in-the-alert-story"></a>경고 스토리에서 경고의 역할 추적
경고 스토리에는 프로세스 트리 보기에서 경고와 관련된 모든 자산 또는 엔터티가 표시됩니다. 제목의 경고는 선택한 경고 페이지에 처음 방문할 때 포커스가 있는 경고입니다. 경고 스토리의 자산은 확장 가능하고 클릭할 수 있습니다. 경고 페이지의 컨텍스트에서 바로 조치를 취할 수 있도록 하여 추가 정보와 즉석 응답을 제공합니다. 

> [!NOTE]
> 경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.

### <a name="view-more-alert-information-in-the-details-pane"></a>세부 정보 창에서 추가 경고 정보 보기

세부 정보 창에는 처음에 선택한 경고의 세부 정보와 관련된 세부 정보 및 작업이 표시됩니다. 경고 스토리에서 영향을 받는 자산 또는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 개체에 대한 상황 정보 및 작업을 제공합니다.

관심 있는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 엔터티 유형에 대한 정보, 사용 가능한 기록 정보 및 경고 페이지에서 이 엔터티에 대해 직접 작업을 수행하기 위한 옵션이 표시됩니다.

### <a name="manage-alerts"></a>경고 관리

경고 조사가 완료되면 시작한 경고로 돌아가 경고 상태를 해결된 것으로 표시하고 이를 False 경고 또는 True 경고로 분류할 수 있습니다. 경고를 분류하면 더 많은 실제 경고와 거짓 경고를 덜 제공하기 위해 제품을 조정하는 데 도움이 됩니다.

> [!NOTE]
> 한 가지 관리 방법은 태그를 사용하여 경고합니다. Microsoft Defender for Office 365에 대한 태그 지정 기능은 증분적으로 배포되고 있으며 현재 미리 보기로 제공됩니다. <br>
> 현재 수정된 태그 이름은 업데이트 후에 만들어진 *경고에만* 적용됩니다. 수정 전에 생성된 알림에는 업데이트된 태그 이름이 반영되지 않습니다. 


## <a name="manage-the-unified-alert-queue"></a>통합 경고 큐 관리

Microsoft 365 보안 센터 & 창에서 인시던트 및 경고를 선택하면 통합 경고 큐로 이동합니다. 이 섹션에는 끝점용 Microsoft Defender, Office 365용 Microsoft Defender 및 Microsoft 365 Defender와 같은 다양한 Microsoft 보안 솔루션의 알림이 표시됩니다. 

![샘플 경고 페이지의 이미지](../../media/unified-alert-queue.png)

경고 큐에는 네트워크에서 플래그가 지정된 경고 목록이 표시됩니다. 기본적으로 큐에는 지난 30일 동안의 경고가 표시됩니다. 가장 최근 경고는 가장 최근 경고를 먼저 볼 수 있도록 목록 맨 위에 표시됩니다.

> [!NOTE]
> 시작 시 통합 경고 큐에는 7일 동안의 Office 365용 Microsoft Defender 경고만 사용할 수 있습니다. 큐는 시간이 지날 때에도 계속 빌드됩니다. 통합 경고 큐를 실행하기 전에 경고를 평가해야 하는 경우 보안 및 준수 센터의 경고 [큐를 사용 합니다.](https://protection.office.com/viewalerts)


위쪽 탐색에서 다음을 할 수 있습니다.

- 필터 적용
- 열을 추가 또는 제거하기 위해 열 사용자 지정
- 데이터 내보내기

다른 기준에 따라 경고를 필터링할 수도 있습니다.

- 심각도
- 상태
- 범주
- 검색 원본
- 정책
- 영향을 미치는 자산
- 첫 번째 활동
- 마지막 활동


인시던트에 대한 조사를 시작하기 위해 [Microsoft 365 Defender에서](investigate-incidents.md) 인시던트 조사를 읽어 보시고
## <a name="see-also"></a>참고 항목

- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
