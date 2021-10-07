---
title: 끝점 인시던트에 대한 Microsoft Defender 관리
description: 인시던트 할당, 상태 업데이트 또는 분류 설정으로 인시던트 관리
keywords: 인시던트, 관리, 할당, 상태, 분류, 참 경고, 거짓 경고
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 051f339d1043aaea2c81954d51493cee1c52a969
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156249"
---
# <a name="manage-microsoft-defender-for-endpoint-incidents"></a>끝점 인시던트에 대한 Microsoft Defender 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

인시던트 관리는 모든 사이버 보안 작업의 중요한 부분입니다. 인시던트 큐 또는 인시던트 관리 창에서 인시던트 를 선택하여 인시던트 **관리를 할 수 있습니다.**  


인시던트 큐에서 인시던트를 선택하면 인시던트 관리 창이 표시되어 자세한 내용을 볼 수 있습니다.  


![인시던트 관리 창의 이미지입니다.](images/atp-incidents-mgt-pane-updated.png)

인시던트는 사용자에게 할당하거나, 상태 및 분류를 변경하거나, 이름을 바꾸거나, 설명을 추가하여 진행 상황을 추적할 수 있습니다.

> [!TIP]
> 추가 가시성을 위해 인시던트 이름은 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 자동으로 생성됩니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다.
>
> 예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*
>
> 자동 인시던트 명명을 출시하기 전에 존재한 인시던트의 이름은 그대로 유지됩니다.
>


![인시던트 세부 정보 페이지의 이미지입니다.](images/atp-incident-details-updated.png)

## <a name="assign-incidents"></a>인시던트 할당
인시던트가 아직 할당되지 않은  경우 할당을 선택하여 인시던트가 사용자에게 할당될 수 있습니다. 이렇게 하면 인시던트뿐만 아니라, 관련된 모든 알림의 소유권을 가정합니다.

## <a name="set-status-and-classification"></a>상태 및 분류 설정
### <a name="incident-status"></a>인시던트 상태
조사가 진행됨에 따라 상태를 변경하여 인시던트(**활성** 또는 **해결됨**)를 분류할 수 있습니다. 이렇게 하면 팀에서 인시더트에 대한 대응 방법을 구성하고 관리할 수 있습니다.

예를 들어 SoC 분석가가 해당  일에 대한 긴급한 활성 인시던트들을 검토하고 조사를 위해 자신을 할당할 수 있습니다.

또는 인시던트가 수정된 경우  SoC 분석가가 인시던트 해결로 설정할 수 있습니다. 

### <a name="classification"></a>분류
분류를 설정하지 않도록 선택하거나 인시던트가 true 또는 false인지 여부를 지정하도록 결정할 수 있습니다. 이렇게 하면 팀에서 패턴을 보고 해당 정보에서 배울 수 있습니다.

### <a name="add-comments"></a>메모 추가
인시던트에 대한 메모를 추가하고 기록 이벤트를 보고 이전에 변경한 내용을 확인할 수 있습니다.

알림에 대해 변경 사항이나 메모가 작성될 때마다, 해당 내용이 메모 및 기록 섹션에 기록됩니다.

추가된 메모는 창에 바로 표시됩니다.



## <a name="related-topics"></a>관련 항목
- [인시던트 큐](/microsoft-365/security/defender-endpoint/view-incidents-queue)
- [인시던트 큐 보기 및 구성](view-incidents-queue.md)
- [인시던트 조사](investigate-incidents.md)
