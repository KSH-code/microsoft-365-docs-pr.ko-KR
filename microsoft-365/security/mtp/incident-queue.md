---
title: Microsoft Threat Protection 사고 우선순위
description: Microsoft Threat Protection의 사고 큐에서 우선 순위를 지정 하는 방법을 알아봅니다.
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
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
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 382cfd374c40d0c5a0dd7d7705281bd56263d8b8
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430826"
---
# <a name="prioritize-incidents-in-microsoft-threat-protection"></a>Microsoft Threat Protection 사고 우선순위

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft Threat Protection 



Microsoft Threat Protection은 상관 관계 분석을 하고 관련된 모든 알람을 수집한 뒤 각각의 다른 제품에서 발생한 알람을 하나의 사고로 조사합니다.  Microsoft Threat Protection 전체 항목 및 제품군 엔드 투 엔드 가시성에서 악성으로 판단된 작업에 대해서는 특별 알람을 발생시킵니다.  Microsoft Threat Protection은 보다 광범위한 공격내용을 구연함으로써 보안 운영 분석가가 조직 전반을 위협하는 복잡한 공격을 이해하고 처리할 수 있도록 합니다. 


**사고 큐**는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.


![사고 큐의 이미지](../../media/incidents-queue.png) 

기본적으로 Microsoft 365 보안 센터의 큐에는\ 최근 30일 동안 발생한 사고가 표시 되며, 최신 사고가 목록의 맨 위에 표시 되어 최신 사고를 가장 먼저 확인 할 수 있습니다. 

사고 큐는 사고나 사고 관련 항목을 알려주는 커스터마이징이 가능한 열을 보여줌으로써 사고 처리 우선수위를 결정하는데 도움을 줍니다.

보다 쉽게 확인할 수 있도록, 자동 인시던트 명명은 영향을 받는 끝점 (예: 사용자에 게 영향을 받음, 검색 원본 또는 범주)와 같은 경고 특성을 기반으로 하는 인시던트 이름을 생성 합니다. 이를 통해 사고의 범위를 빠르게 파악할 수 있습니다.

예를 들어 *여러 출처에서 보고 하는 여러 끝점에 대 한 다단계 인시던트가 있습니다.*

> [!NOTE]
> 자동 인시던트 이름 지정 롤아웃 이전에 존재 했던 인시던트는 이름을 변경할 수 없습니다.

또한 사고 큐는 여러 개의 필터링 옵션을 제공 합니다. 이 옵션을 적용 하면 환경이 허용하는 모든 기존 사고에 대한 광범위 한 스위프를 수행 하도록 선택 하거나 특정 시나리오 또는 위협에 집중할 수 있도록 결정할 수 있습니다. 사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다. 

## <a name="available-filters"></a>사용 가능한 필터

### <a name="status"></a>상태
상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.

### <a name="severity"></a>심각도
사고의 심각도는 자산에 미칠 수 있는 영향을 의미합니다.  심각도가 높아지면 영향을 크게 받게 되므로 일반적으로 가장 즉각적으로 주의 해야 합니다. 

### <a name="assigned-to-owner"></a>담당자(소유자)
필터를 사용하여 특정 담당자에게 할당 된 목록이나 자신에게 할당된 목록을 선택할 수 있습니다. 

### <a name="multiple-alerts"></a>다중 경고  
하나 이상의 경고를 포함 하는 사고만 표시 하도록 필터링 할 수 있습니다.  이는 보다 복잡하거나 진화된 킬체인 공격일 수 있습니다.  


### <a name="multiple-service-sources"></a>다중 서비스 원인 
다중 원인(Microsoft Defender ATP, Microsoft Cloud App Security, Azure ATP, Office 365 ATP) 알림이 포함 된 사고만 표시 하도록 필터링 할 수 있습니다. 
### <a name="service-sources"></a>서비스 원인
특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다. 

### <a name="multiple-categories"></a>다중 범주 
킬체인의 다중 범주에 매핑된 사고 및 잠재적으로 더 큰 손상을 유발할만한 사고를 선택해서 표시할 수 있습니다. 

### <a name="categories"></a>범주
범주를 선택 하여 킬체인 특정 단계에 집중할 수 있습니다. 

### <a name="data-sensitivity"></a>데이터 민감도
일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다.  필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  

>[!NOTE]
>Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.


## <a name="next-steps"></a>다음 단계
사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. 
- [사고 조사](investigate-incidents.md)


## <a name="related-topics"></a>관련 항목
- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
