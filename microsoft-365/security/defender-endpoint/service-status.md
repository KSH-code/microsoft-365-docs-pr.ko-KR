---
title: Microsoft Defender에서 끝점 서비스 상태 확인
description: Microsoft Defender에서 끝점 서비스 상태 확인, 서비스에 문제가 발생하는지 확인하고 해결된 이전 문제를 검토합니다.
keywords: 대시보드, 서비스, 문제, 서비스 상태, 현재 상태, 상태 기록, 영향 요약, 예비 근본 원인, 해결, 해결 시간, 예상 해결 시간
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 728d152d8c755464669d59e11746566472acd737
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/23/2021
ms.locfileid: "60553871"
---
# <a name="check-the-microsoft-defender-for-endpoint-service-health"></a>Microsoft Defender에서 끝점 서비스 상태 확인

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-servicestatus-abovefoldlink)

**서비스 상태는** Endpoint용 Defender 서비스의 현재 상태에 대한 정보를 제공합니다. 서비스 상태 또는 현재 문제가 있는지 확인할 수 있습니다. 문제가 있는 경우 문제가 검색된 시간, 예비 근본 원인, 예상 해결 시간 등의 정보가 표시될 수 있습니다.

또한 해결된 이전 문제에 대한 정보와 문제가 해결된 날짜 및 시간 등의 세부 정보도 볼 수 있습니다. 서비스에 문제가 없는 경우 정상 상태가 표시됩니다.

보안 작업 대시보드에서 타일을 클릭하거나 탐색 창에서 서비스 상태 메뉴를  선택하여 서비스 상태의 세부 정보를 볼 수 있습니다. 

서비스 **상태** 세부 정보 페이지에는 다음 탭이 있습니다.

- **현재 상태**
- **상태 기록**

## <a name="current-status"></a>현재 상태

현재 **상태 탭에는** Endpoint 서비스용 Defender의 현재 상태가 표시됩니다. 서비스가 원활하게 실행되는 경우 서비스 상태는 정상으로 표시됩니다. 문제가 있는 경우 문제에 대한 더 나은 정보를 얻을 수 있도록 다음과 같은 서비스 세부 정보가 표시됩니다.

- 문제가 검색된 날짜 및 시간
- 문제의 간단한 설명
- 업데이트 시간
- 영향 요약
- 예비 근본 원인
- 다음 단계
- 예상 해결 시간

문제가 해결되면 문제 진행률에 대한 업데이트가 페이지에 반영됩니다. 업데이트된 예상 해결 시간 또는 다음 단계와 같은 정보에 대한 업데이트가 표시될 것입니다.

문제가 해결되면 상태 기록 탭에 **기록됩니다.**

## <a name="status-history"></a>상태 기록

상태 **기록 탭에는** 표시 및 해결된 모든 이전 문제가 반영됩니다. 해결된 문제에 대한 세부 정보와 해결되는 동안 포함된 다른 정보가 표시될 수 있습니다.

### <a name="related-topic"></a>관련 항목

- [보안 작업 대시보드 보기](security-operations-dashboard.md)
