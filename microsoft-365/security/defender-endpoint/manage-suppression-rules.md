---
title: 끝점 제거 규칙에 대한 Microsoft Defender 관리
description: 제거 규칙을 사용하여 포털에 경고가 나타나지 않도록 해야 할 수 있습니다. 끝점용 Microsoft Defender에서 제거 규칙을 관리하는 방법을 배워야 합니다.
keywords: 제거 관리, 규칙, 규칙 이름, 범위, 작업, 경고, 켜기, 끄기
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ac8b6255b46c20582d43680b3287f324f4f63c42
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214902"
---
# <a name="manage-suppression-rules"></a>제거 규칙 관리

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


포털에 경고가 나타나지 않을 수 있는 시나리오가 있을 수 있습니다. 조직의 알려진 도구 또는 프로세스와 같이 무해한 것으로 알려진 특정 경고에 대한 제거 규칙을 만들 수 있습니다. 경고를 표시하지는 방법에 대한 자세한 내용은 경고 표시 안 [를 참조하세요.](manage-alerts.md)

모든 제거 규칙의 목록을 보고 한 장소에서 관리할 수 있습니다. 경고 제거 규칙을 설정하거나 해제할 수도 있습니다.


1. 탐색 창에서 **끝점 규칙 설정** \>  \>  \> **제거를 선택합니다.** 조직의 사용자가 만든 제거 규칙 목록이 표시됩니다.

2. 규칙 이름 옆의 확인란을 클릭하여 규칙을 선택합니다.

3. 규칙 **켜기, 규칙 편집** 또는 규칙  **삭제를 클릭합니다.** 규칙을 변경할 때 이러한 경고가 새 기준과 일치하는지 여부에 관계없이 이미 표시하지 않은 경고를 해제할 수 있습니다. 


## <a name="view-details-of-a-suppression-rule"></a>제거 규칙의 세부 정보 보기

1. 탐색 창에서 **끝점 규칙 설정** \>  \>  \> **제거를 선택합니다.** 조직의 사용자가 만든 제거 규칙 목록이 표시됩니다.

2. 규칙 이름을 클릭합니다. 규칙의 세부 정보가 표시됩니다. 상태, 범위, 작업, 일치하는 경고 수, 생성한 경고 수, 규칙을 만든 날짜 등의 규칙 세부 정보가 표시됩니다. 관련 경고 및 규칙 조건을 볼 수도 있습니다.

## <a name="related-topics"></a>관련 항목

- [경고 관리](manage-alerts.md)
