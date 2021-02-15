---
title: 공격 시뮬레이션 교육용 페이로드 만들기
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 관리자는 Microsoft Defender for Office 365에서 공격 시뮬레이션 교육을 위한 사용자 지정 페이로드를 만드는 방법을 배울 수 있습니다.
ms.technology: mdo
ms.openlocfilehash: 6cc5dd4a48ab89193133cfaf823d0a1b1868fa79
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929193"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>공격 시뮬레이션 교육에 대한 사용자 지정 페이로드 만들기

Microsoft는 공격 시뮬레이션 교육과 쌍을 이을 수 있는 다양한 소셜 엔지니어링 기술을 위한 강력한 페이로드 카탈로그를 제공합니다. 그러나 조직에 더 잘 작동할 수 있는 사용자 지정 페이로드를 만들 수 있습니다. 이 문서에서는 Microsoft Defender for Office 365의 공격 시뮬레이션 교육에서 페이로드를 만드는 방법을 설명합니다.

전용 페이로드 탭 또는 시뮬레이션  만들기 마법사에서 페이로드 만들기를 클릭하여 페이로드를 [만들 수 있습니다.](attack-simulation-training.md#selecting-a-payload) [  ](https://security.microsoft.com/attacksimulator?viewid=payload)

마법사의 첫 번째 단계에서는 페이로드 유형을 선택합니다. **현재 전자 메일만 사용할 수 있습니다.**

다음으로 관련 기술을 선택합니다. 기술에 대한 자세한 내용은 소셜 엔지니어링 기술 [선택을 참조합니다.](attack-simulation-training.md#selecting-a-social-engineering-technique)

다음 단계에서 페이로드 이름을 지정합니다. 필요한 경우 설명을 입력할 수 있습니다.

## <a name="configure-payload"></a>페이로드 구성

이제 페이로드를 빌드해야 합니다. 보낸 사람 세부 정보 섹션에 보낸 사람 이름, 전자 메일 주소 및 전자 메일 **제목을 입력합니다.** 제공된 목록에서 피싱 URL을 선택합니다. 이 URL은 나중에 메시지 본문에 포함됩니다.

> [!TIP]
> 페이로드를 보낸 사람에 대한 내부 전자 메일을 선택하면 페이로드가 회사의 다른 직원에게서 오는 것으로 표시될 수 있습니다. 이렇게 하면 페이로드에 대한 인식이 높아지며 직원에게 내부 위협의 위험을 교육하는 데 도움이 됩니다.

다양한 텍스트 편집기를 사용하여 페이로드를 만들 수 있습니다. 또한 앞서 만든 전자 메일을 가져올 수도 있습니다. 전자 메일 본문을 만들 때 동적  태그를 사용하여 전자 메일을 대상에 맞게 개인 설정하세요. 피싱 **링크를 클릭하여** 이전에 선택한 피싱 URL을 메시지 본문에 추가합니다.

![Microsoft Defender for Office 365용 페이로드 만들기에서 강조 표시된 피싱 링크 및 동적 태그](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 시간을 절약하려면 전자 메일 메시지의 모든 링크를 피싱 링크로 바꾸는 옵션을 **토글합니다.**

원하는 페이로드를 원하는 것으로 구성한 후 다음을 **클릭합니다.**

## <a name="adding-indicators"></a>표시기 추가

표시기는 공격 시뮬레이션을 진행하는 직원이 이후 공격에서 찾아 볼 수 있는 단서를 이해하는 데 도움이 될 것입니다. 시작하려면 **표시기 추가를 클릭합니다.**

드롭다운 목록에서 사용할 표시기를 선택합니다. 이 목록은 피싱 전자 메일 메시지에 나타나는 가장 일반적인 단서를 포함하기 위해 구성됩니다. 선택한 후 표시기 배치가 전자 메일 본문에서 **시작으로** 설정되어 있는지 확인한 후 텍스트 **선택을 클릭합니다.** 이 표시기가 나타나는 페이로드 부분을 강조 표시하고 선택을 **클릭합니다.**

![공격 시뮬레이션 교육의 지표에 추가할 메시지 본문의 강조 표시된 텍스트](../../media/attack-sim-preview-select-text.png)

표시기를 설명하는 사용자 지정 설명을 추가하고 표시기 미리 보기 프레임 내에서 클릭하여 표시기 미리 보기를 볼 수 있습니다. 완료되면 추가를 **클릭합니다.** 페이로드의 모든 표시기를 다를 때까지 이러한 단계를 반복합니다.

## <a name="review-payload"></a>페이로드 검토

페이로드를 완료했습니다. 이제 세부 정보를 검토하고 페이로드의 미리 보기를 볼 시간입니다. 미리 보기에는 만든 모든 표시기가 포함됩니다. 이 단계에서 페이로드의 각 부분을 편집할 수 있습니다. 충족하면 **페이로드를 제출할** 수 있습니다.

> [!IMPORTANT]
> 만든 페이로드에는 **테넌트가** 원본으로 있습니다. 페이로드를 선택할 때 테넌트는 필터링하지 **않는지 확인**

## <a name="related-links"></a>관련 링크

[공격의 신나는 교육 사용 시작](attack-simulation-training-get-started.md)

[피싱 공격 시뮬레이션 만들기](attack-simulation-training.md)

[공격 시뮬레이션 교육 활용](attack-simulation-training-insights.md)
