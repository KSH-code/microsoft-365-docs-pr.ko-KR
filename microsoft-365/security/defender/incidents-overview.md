---
title: Microsoft 365 Defender의 인시던트 개요
description: 여러 장치, 사용자 및 사서함에 표시되는 인시던트를 조사합니다.
keywords: 인시던트, 경고, 조사, 상관 관계, 공격, 컴퓨터, 장치, 사용자, IDs, ID, 사서함, 전자 메일, 365, microsoft, m365
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
ms.openlocfilehash: ef05609da50bc73fa59fb582b77faa5d87b9ece3
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060736"
---
# <a name="incidents-overview-in-microsoft-365-defender"></a>Microsoft 365 Defender의 인시던트 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

> Microsoft 365 Defender를 경험하고 싶나요? 랩 [환경에서 평가하거나](m365d-evaluation.md?ocid=cx-docs-MTPtriallab) 프로덕션 [환경에서 파일럿](m365d-pilot.md?ocid=cx-evalpilot)프로젝트를 실행할 수 있습니다.
>


인시던트는 관련 경고를 기반으로 합니다. 네트워크에서 악성 이벤트 또는 활동이 발견되면 경고가 만들어집니다. 개별 경고는 진행 중 공격에 대한 중요한 단서를 제공합니다. 그러나 공격은 일반적으로 다양한 벡터와 기술을 사용하여 위반을 수행합니다. 개별 단서를 함께 Piecing하는 것은 어렵고 시간이 많이 소요될 수 있습니다.

이 짧은 비디오에서는 Microsoft 365 Defender의 인시던트에 대한 개요를 제공합니다.
<br>

>[!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bzwz?]

인시던트는 공격의 스토리를 만드는 상호 관련 경고의 모음입니다. 네트워크의 여러 장치, 사용자 및 사서함 엔터티에서 발견되는 악성 및 의심스러운 이벤트는 Microsoft 365 Defender에 의해 자동으로 집계됩니다. 관련 경고를 인시던트에 그룹화하면 보안 방어자가 공격을 포괄적으로 볼 수 있습니다. 

예를 들어 보안 방어자는 공격이 시작된 위치, 사용된 전술 및 공격이 네트워크로 들어간 거리를 볼 수 있습니다. 또한 영향을 받은 장치, 사용자 및 사서함의 수, 영향의 심각도 및 영향을 받는 엔터티에 대한 기타 세부 정보 등 공격 범위를 볼 수도 있습니다.

사용하도록 설정하면 Microsoft 365 Defender는 자동화 및 인공 지능을 통해 개별 경고를 자동으로 조사하고 해결할 수 있습니다. 또한 보안 방어자는 추가 수정 단계를 수행하여 인시던트 보기에서 공격을 직접 해결할 수 있습니다. 

지난 30일 동안의 인시던트는 인시던트 큐에 표시됩니다. 여기서 보안 방어자는 위험 수준 및 기타 요인에 따라 우선 순위를 지정해야 하는 인시던트를 볼 수 있습니다. 

또한 보안 방어자는 인시던트 이름을 변경하고, 개별 분석가에게 할당하고, 인시던트에 태그를 분류하고, 인시던트에 태그를 추가하여 보다 사용자 지정된 인시던트 관리 환경을 개선할 수 있습니다.



## <a name="see-also"></a>참고 항목
- [인시던트 우선 순위 지정](incident-queue.md)
- [인시던트 조사](investigate-incidents.md)
- [인시던트 관리](manage-incidents.md)