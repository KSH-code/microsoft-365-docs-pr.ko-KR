---
title: 공격 시뮬레이션 교육을 위한 페이로드 만들기
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Microsoft Defender for Office 365에서 공격 시뮬레이션 교육을 위한 사용자 지정 페이로드를 만드는 방법을 알아봅니다.
ms.openlocfilehash: ffb5397d9b39a35b4cb8bd0fdb3301cd156896e1
ms.sourcegitcommit: dab50e1cc5bba920720b80033c93457f5ca1c330
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/07/2020
ms.locfileid: "48944595"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>공격 시뮬레이션 교육을 위한 사용자 지정 페이로드 만들기

Microsoft는 공격 시뮬레이션 교육을 통해 다양 한 소셜 엔지니어링 기술로 쌍을 두는 강력한 페이로드 카탈로그를 제공 합니다. 그러나 조직에 더 적합 한 방식으로 작동 하는 사용자 지정 페이로드를 만들 수도 있습니다. 다음은 Office 365 용 Microsoft Defender를 통한 공격 시뮬레이션 교육에서 페이로드를 만드는 방법에 대해 설명 합니다.

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[전용 **페이로드** 탭](https://security.microsoft.com/attacksimulator?viewid=payload) 또는 [시뮬레이션 만들기 마법사](attack-simulation-training.md#selecting-a-payload)내에서 **페이로드 만들기** 를 클릭 하 여 페이로드를 만들 수 있습니다.

마법사의 첫 번째 단계에서는 페이로드 유형을 선택 합니다. **현재 전자 메일만 사용할 수** 있습니다.

다음으로, 관련 기술을 선택 합니다. [소셜 엔지니어링 기법을 선택할](attack-simulation-training.md#selecting-a-social-engineering-technique)때의 자세한 기술 정보를 참조 하세요.

다음 단계에서 페이로드 이름입니다. 원하는 경우 설명을 지정할 수 있습니다.

## <a name="configure-payload"></a>페이로드 구성

이제 페이로드를 구축 해야 합니다. 보낸 사람 **정보** 섹션에 보낸 사람의 이름, 전자 메일 및 전자 메일 제목을 입력 합니다. 제공 된 목록에서 피싱 URL을 선택 합니다. 이 URL은 나중에 메시지 본문에 포함 됩니다.

> [!TIP]
> 페이로드의 보낸 사람에 대 한 내부 전자 메일을 선택 하 여 페이로드가 회사의 다른 직원 으로부터 들어오는 것으로 표시 되도록 할 수 있습니다. 이렇게 하면 susceptibility 증가 하 고 내부 위협의 위험에 대해 직원을 교육 하는 데 도움이 됩니다.

페이로드를 만들기 위해 서식 있는 텍스트 편집기를 사용할 수 있습니다. 미리 만든 전자 메일을 가져올 수도 있습니다. 전자 메일의 본문을 구성할 때 **동적 태그** 를 활용 하 여 대상에 전자 메일을 개인 설정 합니다. **피싱 링크** 를 클릭 하 여 이전에 선택한 피싱 URL을 전자 메일의 본문에 추가 합니다.

![Microsoft Defender for Office 365에 대 한 페이로드 만들기에서 강조 표시 된 피싱 링크 및 동적 태그](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 잠시 시간을 절약 하려면 **전자 메일 메시지에 포함 된 모든 링크를 피싱 링크로 바꾸려면** 옵션을 전환 합니다.

원하는 대로 페이로드를 작성 했으면 **다음** 을 클릭 합니다.

## <a name="adding-indicators"></a>지표 추가

지표는 공격 시뮬레이션을 통해 직원 들이 향후 공격에 대해 확인할 수 있는 단서를 이해 하는 데 도움이 됩니다. 시작 하려면 **지표 추가** 를 클릭 합니다.

드롭다운 목록에서 사용할 지표를 선택 합니다. 이 목록은 피싱 전자 메일 메시지에 표시 되는 가장 일반적인 단서를 포함 하는 맞게 조정 된입니다. 선택한 후 지표 배치가 **전자 메일 본문에서** 으로 설정 되어 있는지 확인 하 고 **텍스트 선택을** 클릭 합니다. 이 표시기가 표시 되는 페이로드의 부분을 강조 표시 하 고 **선택을** 클릭 합니다.

![메시지 본문에서 강조 표시 된 텍스트를 공격 시뮬레이션 교육의 지표에 추가할 수 있습니다.](../../media/attack-sim-preview-select-text.png)

지표를 설명 하는 사용자 지정 설명을 추가 하 고 지표 미리 보기 프레임 내에서 클릭 하 여 지표의 미리 보기를 표시 합니다. 작업이 완료 되 면 **추가** 를 클릭 합니다. 페이로드의 모든 표시기를 다룰 때까지 이러한 단계를 반복 합니다.

## <a name="review-payload"></a>페이로드 검토

페이로드 작성이 완료 되었습니다. 이제 세부 정보를 검토 하 고 페이로드 미리 보기를 볼 수 있습니다. 미리 보기에는 사용자가 만든 모든 표시기가 포함 됩니다. 이 단계에서 페이로드의 각 부분을 편집할 수 있습니다. 충족 되 면 페이로드를 **전송** 합니다. 

> [!IMPORTANT]
> 만든 페이로드에는 **테 넌 트** 집합이 원본으로 포함 됩니다. 페이로드를 선택할 때 **테 넌 트가** 필터링 되지 않았는지 확인 합니다.