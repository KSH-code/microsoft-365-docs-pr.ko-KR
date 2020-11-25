---
title: Microsoft 365 Defender의 문제점 우선 순위 지정
description: Microsoft 365 Defender의 인시던트 큐에서 인시던트를 필터링 하는 방법에 대해 알아봅니다.
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
ms.openlocfilehash: e587004fbb3bc6defab985cea9b427f64b3aab35
ms.sourcegitcommit: a9486f9dc51f0908393000ec3c211e3430c26abd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/25/2020
ms.locfileid: "49409258"
---
# <a name="prioritize-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender의 문제점 우선 순위 지정

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



Microsoft 365 Defender는 상관 분석을 적용 하 고 다양 한 제품의 모든 관련 알림과 조사를 하나의 인시던트로 집계 합니다. Microsoft 365 Defender는 또한 Microsoft 365 Defender가 전체 부동산 및 제품군에 걸쳐 있는 종단 간 가시성과 함께 악의적으로 식별 될 수 있는 작업에 대 한 고유한 경고를 트리거합니다. 이 보기는 보안 작업 분석가에 게 보다 폭넓은 공격 정보를 제공 하므로 조직 전체에서 복잡 한 위협을 보다 효율적으로 이해 하 고 처리할 수 있습니다.


**사고 큐** 는 장치, 사용자 및 사서함에 대해 플래그가 지정 된 사고의 모음을 보여 줍니다. 이 기능은 사고 우선순위를 정하고 사이버 보안 반응 결정을 내리는 데 도움을 줍니다.


![사고 큐의 이미지](../../media/incidents-queue.png) 

기본적으로 Microsoft 365 보안 센터의 큐에는 지난 30 일 동안 표시 된 인시던트가 표시 됩니다. 가장 최근 인시던트가 목록 맨 위에 표시 되므로 먼저 해당 인시던트를 확인할 수 있습니다.

인시던트 큐는 인시던트 또는 포함 된 엔터티에 대 한 다양 한 특성을 표시 하는 사용자 지정 가능한 열을 제공 합니다. 이를 통해 처리할 인시던트의 우선 순위에 대 한 정보를 확인할 수 있습니다.

보다 한눈에 확인할 수 있도록, 자동 인시던트 명명은 영향을 받는 끝점 (예: 사용자에 게 영향을 받음, 검색 원본 또는 범주) 등의 경고 특성을 기반으로 하는 인시던트 이름을 생성 합니다. 이를 통해 사고의 범위를 빠르게 파악할 수 있습니다.

예를 들어 *여러 출처에서 보고 하는 여러 끝점에 대 한 다단계 인시던트가 있습니다.*

> [!NOTE]
> 자동 인시던트 이름 지정 롤아웃 이전에 존재 했던 인시던트는 이름을 변경할 수 없습니다.

또한 인시던트 큐는 여러 필터링 옵션을 제공 하며,이를 적용 하면 사용자 환경에서 기존의 모든 인시던트가 광범위 하 게 작동 하거나 특정 시나리오 또는 위협에 집중할 수 있도록 결정 됩니다. 사고 큐 필터를 적용 하면 즉시 주의가 필요한 사고를 결정할 수 있습니다. 

## <a name="available-filters"></a>사용 가능한 필터

### <a name="assigned-to"></a>담당자
자신에 게 할당 되거나 자동화로 처리 되는 경고를 표시 하도록 선택할 수 있습니다.

### <a name="categories"></a>범주
표시 되는 특정 기법, 기술 또는 공격 구성 요소에 중점을 둘 범주를 선택 합니다. 

### <a name="classification"></a>분류
관련 된 알림의 분류 설정에 따라 인시던트를 필터링 합니다. 값에는 true 알림, 거짓 경고 또는 설정 되지 않음이 포함 됩니다.

### <a name="data-sensitivity"></a>데이터 민감도
일부 공격은 민감하거나 가치있는 데이터 수집을 목적으로 합니다.  필터를 적용하여 민감한 데이터가 사건에 연루되었는지를 확인한 후 민감 정보의 누출 여부를 결정하고 해당 사고의 우선순위를 결정할 수 있습니다.  

>[!NOTE]
>Microsoft Threat Protection이 설정 된 경우에만 적용 됩니다.

### <a name="device-group"></a>장치 그룹
정의 된 장치 그룹으로 필터링 합니다.

### <a name="investigation-state"></a>조사 상태
자동화 된 조사 상태별로 인시던트를 필터링 합니다. 

### <a name="multiple-categories"></a>다중 범주 
여러 범주에 매핑된 인시던트만 표시 하도록 선택할 수 있으므로 손상을 더 많이 유발할 수 있습니다. 

### <a name="multiple-service-sources"></a>다중 서비스 원인 
서로 다른 원본 (끝점에 대 한 microsoft Defender, Microsoft Cloud App Security, Microsoft Defender for Identity, Microsoft Defender for Office 365에 대 한 알림)이 포함 된 인시던트만 표시 되도록 필터링 합니다.

### <a name="os-platform"></a>OS 플랫폼
운영 체제별로 인시던트 큐 보기를 제한 합니다.

### <a name="service-sources"></a>서비스 원인
특정 원인을 선택 하면 해당 원인에서 최소 하나의 알림을 포함 하는 사고에 집중할 수 있습니다. 

### <a name="severity"></a>심각도
인시던트의 심각도는 해당 자산의 영향을 자산에 미칠 수 있음을 말합니다. 심각도가 높을수록 영향은 더 높고 일반적으로는 가장 즉각적인 주의가 필요 합니다. 

### <a name="status"></a>상태
상태에 따라 표시 되는 사고의 목록을 제한하여 활성 또는 해결 완료 된 사고를 확인할 수 있습니다.




## <a name="next-steps"></a>다음 단계
사고의 우선순위를 결정한 뒤 사고에 대한 조사를 진행할 수 있습니다. 
- [사고 조사](investigate-incidents.md)


## <a name="see-also"></a>참고 항목
- [사고 개요](incidents-overview.md)
- [사고 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)
