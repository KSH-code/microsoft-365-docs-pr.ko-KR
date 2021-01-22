---
title: Microsoft 365 Defender에서 인시던트 우선 순위 지정
description: Microsoft 365 Defender의 인시던트 큐에서 인시던트 필터링 방법 학습
keywords: 사고, 큐, 개요, 장치, 식별, 사용자, 사서함, 전자 메일, 사고
search.product: eADQiWindows 10XVcnh
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
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: e01fce970b806bc425db2cd4886e82f79434656f
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929297"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 인시던트 우선 순위 지정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



Microsoft 365 Defender는 상관 관계 분석을 적용하고 서로 다른 제품의 모든 관련 경고 및 조사를 하나의 인시던트로 집계합니다. 또한 Microsoft 365 Defender는 전체 자산 및 제품군에서 Microsoft 365 Defender가 가지고 있는 종단 간 가시성을 통해 악성으로만 식별될 수 있는 활동에 대해 고유한 경고를 트리거합니다. 이 보기는 보안 운영 분석가에게 보다 광범위한 공격 스토리를 제공하여 조직 전체의 복잡한 위협을 더 잘 이해하고 처리하는 데 도움이 됩니다.


**사고 큐** 는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.


![사고 큐의 이미지](../../media/incidents-queue.png) 

기본적으로 Microsoft 365 보안 센터의 큐에는 지난 30일 동안의 인시던트가 표시됩니다. 가장 최근 인시던트는 목록 맨 위에 있으므로 먼저 볼 수 있습니다.

인시던트 큐는 인시던트 또는 포함된 엔터티의 다양한 특성을 표시하는 사용자 지정 가능한 열을 노출합니다. 이렇게 하면 처리할 인시던트의 우선 순위에 대한 정보를 통해 결정을 내리는 데 도움이 됩니다.

추가 가시성을 위해 자동 인시던트 명명은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성을 기반으로 인시던트 이름을 생성합니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.

예: 여러 원본에서 보고하는 여러 끝점의 다단계 *인시던트입니다.*

> [!NOTE]
> 자동 인시던트 명명을 롤아웃하기 전에 존재한 인시던트의 이름은 변경되지 않습니다.

또한 인시던트 큐는 여러 필터링 옵션을 노출합니다. 이 옵션을 적용하면 환경의 모든 기존 인시던트에 대한 광범위한 스위프를 수행하거나 특정 시나리오 또는 위협에 집중할 수 있습니다. 사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다. 

## <a name="available-filters"></a>사용 가능한 필터

### <a name="assigned-to"></a>할당된 사용자
사용자에게 할당된 경고 또는 자동화에서 처리하는 경고를 표시하기로 선택할 수 있습니다.

### <a name="categories"></a>범주
범주를 선택해 특정 전략, 기술 또는 공격 구성 요소에 집중합니다. 

### <a name="classification"></a>분류
관련 경고의 설정된 분류에 따라 인시던트 필터링 값에는 실제 경고, 거짓 경고 또는 설정되지 않은 알림이 포함됩니다.

### <a name="data-sensitivity"></a>데이터 민감도
일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다.  필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  

>[!NOTE]
>Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.

### <a name="device-group"></a>디바이스 그룹
정의된 장치 그룹으로 필터링합니다.

### <a name="investigation-state"></a>조사 상태
자동화된 조사 상태를 통해 인시던트 필터링 

### <a name="multiple-categories"></a>다중 범주 
여러 범주에 매핑된 인시던트만 표시하여 잠재적으로 더 많은 손상을 일으킬 수 있습니다. 

### <a name="multiple-service-sources"></a>다중 서비스 원인 
다양한 원본에서 경고를 포함하는 인시던트만 확인을 위해 필터링합니다(끝점용 Microsoft Defender, Microsoft Cloud App Security, ID용 Microsoft Defender, Office 365용 Microsoft Defender).

### <a name="os-platform"></a>OS 플랫폼
운영 체제에 따라 인시던트 큐 보기를 제한합니다.

### <a name="service-sources"></a>서비스 원인
특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다. 

### <a name="severity"></a>심각도
인시던트의 심각도는 자산에 미칠 수 있는 영향을 나타내는 것입니다. 심각도가 높을수록 영향이 커지며 일반적으로 가장 즉각적인 주의가 필요합니다. 

### <a name="status"></a>상태
상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.




## <a name="next-steps"></a>다음 단계
사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. 
- [사고 조사](investigate-incidents.md)


## <a name="see-also"></a>기타 참고 항목
- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
