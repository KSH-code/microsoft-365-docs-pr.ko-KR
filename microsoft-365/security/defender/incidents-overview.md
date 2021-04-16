---
title: Microsoft 365 Defender의 인시던트
description: 여러 장치, 사용자 및 사서함에 표시되는 인시던트를 조사합니다.
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
ms.openlocfilehash: e1e028f7b58df07eccf945b3a79012b4ea12366d
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861626"
---
# <a name="incidents-in-microsoft-365-defender"></a>Microsoft 365 Defender의 인시던트

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험해 보고 싶으신가요? [랩 환경에서 평가](m365d-evaluation.md?ocid=cx-docs-MTPtriallab)하거나 [프로덕션에서 파일럿 프로젝트를 실행](m365d-pilot.md?ocid=cx-evalpilot)할 수 있습니다.
>

Microsoft 365 Defender의 인시던트는 공격의 스토리를 만드는 상관 관계 있는 경고 및 관련 데이터의 모음입니다. 

Microsoft 365 서비스 및 앱은 의심스러운 또는 악의적인 이벤트 또는 활동을 감지할 때 경고를 생성합니다. 개별 경고는 완료되거나 지속적인 공격에 대한 중요한 단서를 제공합니다. 그러나 공격은 일반적으로 장치, 사용자 및 사서함과 같은 다양한 유형의 엔터티에 대해 다양한 기술을 사용합니다. 그 결과 테넌트의 여러 엔터티에 대한 여러 경고가 생성됩니다. 

개별 경고를 함께 하여 공격에 대한 통찰력을 확보하는 것은 어렵고 시간이 많이 소요될 수 있기 때문에 Microsoft 365 Defender는 경고 및 관련 정보를 인시던트에 자동으로 집계합니다.

:::image type="content" source="../../media/incidents-overview/incidents.png" alt-text="Microsoft 365 Defender가 엔터티의 이벤트를 인시던트와 상관 관계 지정하는 방법":::

Microsoft 365 Defender의 인시던트에 대한 간략한 개요(4분)를 시청하세요.

<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

관련 경고를 인시던트로 그룹화하면 공격을 포괄적으로 볼 수 있습니다. 예를 들어 다음을 볼 수 있습니다.

- 공격이 시작된 위치입니다.
- 사용된 전술
- 공격이 테넌트에 얼마나 들어갔는가.
- 공격 범위(예: 영향을 받는 장치, 사용자 및 사서함 수)입니다. 
- 공격과 관련된 모든 데이터입니다.

[활성화된](m365d-enable.md)경우 Microsoft 365 Defender는 자동화 및 인공 지능을 통해 경고를 자동으로 조사하고 해결할 수 있습니다. 추가 수정 단계를 수행하여 공격을 해결할 수도 있습니다. 

## <a name="incidents-and-alerts-in-the-microsoft-365-security-center"></a>Microsoft 365 보안 센터의 인시던트 및 경고

Microsoft 365 보안 센터(&)의 > 인시던트 및 인시던트 경고에서 인시던트 security.microsoft.com[관리합니다.](https://security.microsoft.com)  다음은 예입니다.

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="Microsoft 365 보안 센터의 인시던트 페이지":::

인시던트 이름을 선택하면 인시던트 요약이 표시될 수 있으며 추가 정보가 있는 탭에 액세스할 수 있습니다.

:::image type="content" source="../../media/incidents-overview/incidents-ss-incident-summary.png" alt-text="Microsoft 365 보안 센터의 인시던트에 대한 요약 페이지 예":::

인시던트에 대한 추가 탭은:

- 경고 

  인시던트 및 해당 정보와 관련된 모든 경고입니다.

- 디바이스

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 장치입니다.

- 사용자

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사용자입니다.

- 사서함

  인시던트의 일부로 식별되거나 인시던트와 관련된 모든 사서함입니다.

- 조사

  인시던트의 경고에 의해 트리거된 모든 자동화된 조사.

- 증거 및 응답

  인시던트의 경고에서 지원되는 모든 이벤트 및 의심스러운 엔터티

다음은 인시던트와 인시던트 데이터 및 Microsoft 365 보안 센터의 인시던트 탭 간의 관계입니다.

:::image type="content" source="../../media/incidents-overview/incidents-security-center.png" alt-text="Microsoft 365 보안 센터에서 인시던트와 인시던트의 데이터와 인시던트의 관계":::

## <a name="next-step"></a>다음 단계

인시던트  페이지의 인시던트 큐에 최근 인시던트가 나열됩니다. 여기에서 다음을 할 수 있습니다.

- 심각도 및 기타 [](incident-queue.md) 요인에 따라 우선 순위를 지정해야 하는 사고를 참조합니다. 
- [인시던트에 대한](investigate-incidents.md) 조사를 수행합니다.
- [인시던트](manage-incidents.md)관리 를 관리합니다. 여기에는 인시던트 이름 변경, 할당, 분류 및 인시던트 관리 워크플로에 대한 태그 추가가 포함됩니다.
