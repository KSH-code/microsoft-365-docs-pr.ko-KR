---
title: Microsoft 365 Defender에서 인시던트 관리
description: 상태, 인시던트, 경고, 연관된 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365를
keywords: 할당하고 업데이트하는 방법을 알아봅니다.인시던트, 인시던트, 경고, 연관 되는 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
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
ms.openlocfilehash: 4e216f841c8728b1cabd98a931e7326f53344a74
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072716"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender에서 인시던트 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



인시던트 관리는 위협이 포함되어 있고 해결되었는지 확인하는 데 매우 중요합니다. Microsoft 365 Defender에서 장치, 사용자 및 사서함의 인시던트 관리에 액세스할 수 있습니다. 


**인시던트 큐** 에서 인시던트를 선택하여 인시던트를 관리할 수 있습니다. 

인시던트의 이름을 편집하고 문제를 해결하며 분류 및 결정을 설정할 수 있습니다. 인시던트를 자신에게 할당하고 인시던트 태그와 메모를 추가할 수도 있습니다.

조사 중에 한 인시던트의 알림을 다른 인시던트로 이동하려는 경우, 모든 관련된 알림이 포함된 더 크거나 작은 인시던트를 만들어 알림 탭에서 해당 작업을 수행할 수도 있습니다.

## <a name="edit-incident-name"></a>인시던트 이름 편집
인시던트에는 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 이름이 자동으로 할당됩니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.

예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*

기본 명명 규칙에 맞게 인시던트 이름을 수정할 수 있습니다.

> [!NOTE]
> 자동 인시던트 명명 기능을 출시하기 전에 존재한 인시던트의 이름은 유지됩니다.



## <a name="assign-incidents"></a>인시던트 할당
아직 인시던트가 할당되지 않은 경우 **나에게 할당** 을 선택하여 인시던트를 자신에게 할당할 수 있습니다. 이렇게 하면 인시던트뿐만 아니라, 관련된 모든 알림의 소유권을 가정합니다.

## <a name="set-status-and-classification"></a>상태 및 분류 설정
### <a name="incident-status"></a>인시던트 상태
조사가 진행됨에 따라 상태를 변경하여 인시던트(**활성** 또는 **해결됨**)를 분류할 수 있습니다. 이렇게 하면 팀에서 인시더트에 대한 대응 방법을 구성하고 관리할 수 있습니다.

예를 들어, SOC 분석가가 해당 일의 긴급한 **활성** 인시던트를 검토하고 조사를 위해 자신에게 인시던트를 할당할 수 있습니다.ㅎ

또는, 인시던트가 조정된 경우 SOC 분석가가 인시던트를 **해결됨** 으로 설정할 수 있습니다. 문제를 해결하면 인시던트의 일부이며 계속 열려 있는 모든 알림이 자동으로 닫힙니다. 

### <a name="classification-and-determination"></a>분류 및 결정
분류를 설정하지 않도록 선택하거나 인시던트가 true 또는 false인지 여부를 지정하도록 결정할 수 있습니다. 이렇게 하면 팀에서 패턴을 보고 해당 정보에서 배울 수 있습니다. 

## <a name="add-comments"></a>메모 추가
인시던트에 대한 메모를 추가하고 기록 이벤트를 보고 이전에 변경한 내용을 확인할 수 있습니다.

알림에 대해 변경 사항이나 메모가 작성될 때마다, 해당 내용이 메모 및 기록 섹션에 기록됩니다.

추가된 메모는 창에 바로 표시됩니다.

## <a name="add-incident-tags"></a>인시던트 태그 추가
예를 들어 인시던트 그룹에 공통 특성을 플래그 지정하기 위해, 사용자 지정 태그를 인시던트에 추가할 수 있습니다. 나중에 특정 태그가 포함된 모든 인시던트의 인시던트 큐를 필터링할 수 있습니다.
