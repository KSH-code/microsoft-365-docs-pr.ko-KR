---
title: 2016에서 인시던트 Microsoft 365 Defender
description: 상태, 인시던트, 경고, 연관된 경고, 할당, 업데이트, 상태, 관리, 분류, microsoft, 365, m365를
keywords: 인시던트, 인시던트, 분석, 대응, 경고, 상관 관계 경고, 할당, 업데이트, 상태, 관리, 분류, Microsoft, 365, m365
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
ms.openlocfilehash: 41a0c893e193c8690c0c50e5b12ecc8630b9a899
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185692"
---
# <a name="manage-incidents-in-microsoft-365-defender"></a>2016에서 인시던트 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

인시던트 관리는 위협이 포함 및 해결될 수 있도록 하는 중요한 요소입니다.

인시던트  및 인시던트 & 포털(>)의 빠른 실행에서 인시던트 Microsoft 365 Defender 관리합니다 security.microsoft.com.[](https://security.microsoft.com) 다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="인시던트 큐의 예입니다.":::

인시던트 관리 방법은 다음과 같습니다.

- [인시던트 이름 편집](#edit-the-incident-name)
- [인시던트 태그 추가](#add-incident-tags)
- [인시던트 할당](#assign-incidents)
- [해결](#resolve-an-incident)
- [분류 및 결정 설정](#set-the-classification-and-determination)
- [설명 추가](#add-comments)

인시던트에 대한 **인시던트 관리** 창에서 인시던트를 관리할 수 있습니다. 다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="인시던트의 인시던트 관리 창 예":::

이 창은 다음의  문제 관리 링크에서 표시할 수 있습니다.

- 인시던트 큐에 있는 인시던트의 속성 창입니다.
- **인시던트의** 요약 페이지입니다.

한 인시던트에서 다른 인시던트로 경고를 이동하려는  경우 경고 탭에서 알림을 이동하여 모든 관련 알림을 포함하는 더 크거나 작은 인시던트가 생성될 수도 있습니다.

## <a name="edit-the-incident-name"></a>인시던트 이름 편집

Microsoft 365 Defender 영향을 받는 끝점 수, 영향을 받는 사용자, 검색 원본 또는 범주와 같은 경고 특성에 따라 이름을 자동으로 할당합니다. 이렇게 하면 인시던트의 범위를 빠르게 이해할 수 있습니다. 예: 여러 원본에서 보고한 여러 끝점의 다단계 *인시던트*

문제 관리 창의 인시던트 이름 필드에서 문제 이름을 **편집할 수** 있습니다. 

> [!NOTE]
> 자동 인시던트 명명 기능을 출시하기 전에 존재한 인시던트의 이름은 유지됩니다.

## <a name="add-incident-tags"></a>인시던트 태그 추가

예를 들어 인시던트 그룹에 공통 특성을 플래그 지정하기 위해, 사용자 지정 태그를 인시던트에 추가할 수 있습니다. 나중에 특정 태그가 포함된 모든 인시던트의 인시던트 큐를 필터링할 수 있습니다.

입력을 시작할 때 선택한 태그 목록에서 선택할 수 있는 옵션이 있습니다.

## <a name="assign-incidents"></a>인시던트 할당

인시던트 할당하려면 나에게 **할당을 선택합니다.** 이렇게 하면 인시던트의 소유권과 인시던트와 관련된 모든 경고가 사용자 계정에 할당됩니다.

인시던트 큐를 필터링하여 사용자에게 할당된 인시던트 목록을 얻을 수 있습니다. 

1. 인시던트 큐에서 필터 를 **선택합니다.**
2. **인시던트 할당 섹션에서** 모두 선택을 **취소하고** **할당된 내게 할당을 선택합니다.**
3. **적용을** 선택한 다음 필터 **창을** 닫습니다.

그런 다음 결과 URL을 브라우저에 책갈피로 저장하여 할당된 인시던트 목록을 빠르게 볼 수 있습니다.

## <a name="resolve-an-incident"></a>인시던트 해결

인시던트가 수정된 경우 인시던트 해결을 **선택하여** 토글을 오른쪽으로 이동합니다. 인시던트 해결을 통해 인시던트와 관련된 연결된 경고 및 활성 경고도 모두 해결됩니다.

해결되지 않은 인시던트가 활성으로 **표시됩니다.**

## <a name="set-the-classification-and-determination"></a>분류 및 결정 설정

인시던트 분류는 실제 경고인지 또는 거짓 경고인지를 분류 필드에서 구성하는 **것입니다.** 

실제 경고인 경우 결정 필드를 사용하여 위협의 유형도 **지정해야** 합니다. 위협 유형을 지정하면 보안 팀이 위협 패턴을 보고 조직을 방어하는 데 도움이 됩니다. 

## <a name="add-comments"></a>메모 추가

설명 필드를 사용하여 인시던트에 여러 개의 설명을 추가할 **수** 있습니다. 각 설명은 인시던트의 기록 이벤트에 추가됩니다. 인시던트에 대한 설명과 기록은  요약 페이지의 설명 및 기록 **링크에서 볼 수** 있습니다.

## <a name="next-steps"></a>다음 단계

새 인시던트의 경우 조사를 [시작합니다.](investigate-incidents.md)

In-process 인시던트의 경우 조사를 [계속합니다.](investigate-incidents.md)

해결된 인시던트의 경우 인시던트 [사후 검토를 수행 합니다.](first-incident-post.md)

## <a name="see-also"></a>참고 항목

- [인시던트 개요](incidents-overview.md)
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 조사](investigate-incidents.md)
