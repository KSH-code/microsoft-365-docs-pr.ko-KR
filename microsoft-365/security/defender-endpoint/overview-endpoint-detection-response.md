---
title: 끝점 검색 및 응답 기능 개요
ms.reviewer: ''
description: 끝점용 Microsoft Defender의 엔드포인트 감지 및 응답 기능에 대해 자세히 알아보시고
keywords: 끝점용 Microsoft Defender, 엔드포인트 감지 및 대응, 대응, 탐지, 사이버 보안, 보호
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: f1461cc9871e57cf422c261191723d8d229cc3c9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205214"
---
# <a name="overview-of-endpoint-detection-and-response"></a>엔드포인트 검색 및 대응 개요

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

Endpoint 끝점 감지 및 응답 기능에 대한 Defender는 거의 실시간으로 실행 가능한 고급 공격 감지를 제공합니다. 보안 분석가는 알림에 효과적으로 우선 순위를 지정하고, 침해의 전체 범위에 대한 가시성을 확보하고 위협을 수정하기 위한 대응 조치를 취할 수 있습니다.

위협이 탐지되면 분석가가 조사할 수 있도록 시스템에서 경고가 생성됩니다. 동일한 공격 기법 혹은 동일한 공격자에 기인한 경고는 _인시던트_ 라는 엔터티로 집계됩니다. 이처럼 경고를 집계하면 분석가가 위협을 손쉽게 일괄적으로 조사하고 이에 대응할 수 있습니다.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4o1j5]

"위반 가정" 마음가림에 따라 엔드포인트용 Defender는 행동적 사이버 원격 분석도 지속적으로 수집합니다. 여기에는 프로세스 정보, 네트워크 활동, 커널 및 메모리 관리자에 대한 심도있는 광학, 사용자 로그인 활동, 레지스트리와 파일 시스템 변경 등이 포함됩니다. 이 정보는 6개월간 저장이 되어 분석가가 공격의 시작 시점으로 돌아가볼 수 있게 해줍니다. 그런 다음 분석가는 다양한 벡터를 통해 다양한 보기로 회전하고 조사를 수행할 수 있습니다.

대응 기능은 사용자가 영향을 받는 엔터티에 대처하여 위협을 즉시 수정할 수 있도록 해줍니다.

## <a name="related-topics"></a>관련 항목

- [보안 운영 대시보드](security-operations-dashboard.md)
- [인시던트 큐](view-incidents-queue.md)
- [경고 큐](alerts-queue.md)
- [장치 목록](machines-view-overview.md)
