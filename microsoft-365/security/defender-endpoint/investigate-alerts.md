---
title: 끝점 경고에 대한 Microsoft Defender 조사
description: 조사 옵션을 사용하여 네트워크에 영향을 주는 경고, 경고의 의미 및 경고를 해결하는 방법에 대한 세부 정보를 얻을 수 있습니다.
keywords: 조사, 조사, 장치, 장치, 경고 큐, 대시보드, IP 주소, 파일, 제출, 심층 분석, 타임라인, 검색, 도메인, URL, IP
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
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: ae6ae9ac805c2b49273f30b3266496a8c4be4d1b
ms.sourcegitcommit: da11ffdf7a09490313dfc603355799f80b0c60f9
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/26/2021
ms.locfileid: "60588080"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a>Microsoft Defender에서 끝점에 대한 경고 조사

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-investigatealerts-abovefoldlink)

네트워크에 영향을 주는 경고를 조사하고 해당 경고의 의미와 경고를 해결하는 방법을 이해합니다.

경고 큐에서 경고를 선택하여 경고 페이지로 이동합니다. 이 보기에는 경고 제목, 영향을 받는 자산, 세부 정보 쪽 창 및 경고 스토리가 포함되어 있습니다.

경고 페이지에서 경고 스토리 트리 보기에서 영향을 받는 자산 또는 엔터티를 선택하여 조사를 시작합니다. 세부 정보 창에는 선택한 내용에 대한 추가 정보가 자동으로 채워집니다. 여기에서 볼 수 있는 정보의 종류를 표시하기 위해 [끝점용 Microsoft Defender의 경고 검토를 참조하세요.](/microsoft-365/security/defender-endpoint/review-alerts)

## <a name="investigate-using-the-alert-story"></a>경고 스토리를 사용하여 조사

경고 스토리에서는 경고가 트리거된 이유, 전후에 발생된 관련 이벤트 및 기타 관련 엔터티에 대해 자세히 설명합니다.

엔터티는 클릭할 수 있으며 경고가 아닌 모든 엔터티는 해당 엔터티 카드 오른쪽의 확장 아이콘을 사용하여 확장할 수 있습니다. 포커스에 있는 엔터티는 해당 엔터티 카드 왼쪽에 파란색 스트라이프로 표시되고 제목의 경고가 처음에 포커스를 하게 됩니다.

엔터티를 확장하여 세부 정보를 한눈에 볼 수 있습니다. 엔터티를 선택하면 세부 정보 창의 컨텍스트가 이 엔터티로 전환됩니다. 그러면 추가 정보를 검토하고 해당 엔터티를 관리할 수 있습니다. 엔터티 카드 오른쪽에서 *...를* 선택하면 해당 엔터티에 사용할 수 있는 모든 작업이 표시됩니다. 이러한 동일한 작업은 해당 엔터티가 포커스에 있는 경우 세부 정보 창에 나타납니다.

> [!NOTE]
> 경고 스토리 섹션에는 두 개 이상의 경고가 포함될 수 있습니다. 이 섹션에서는 선택한 경고 전후에 동일한 실행 트리와 관련된 추가 경고가 나타납니다.

![포커스가 있는 경고와 일부 확장된 카드가 있는 경고 스토리의 예입니다.](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a>세부 정보 창에서 작업 수행

관심 있는 엔터티를 선택하면 세부 정보 창이 변경되어 선택한 엔터티 유형, 사용 가능한 기록 정보 및 경고 페이지에서  직접 이 엔터티에 대한 작업을 수행하기 위한 컨트롤을 제공합니다.

조사가 완료되면 시작한 경고로 돌아가 경고 상태를 **해결된** 것으로 표시하고 **False** 경고 또는 True 경고로 **분류합니다.** 경고를 분류하면 보다 실제 경고와 거짓 경고를 줄이기 위해 이 기능을 조정하는 데 도움이 됩니다.

이를 실제 경고로 분류하는 경우 아래 이미지에 표시된 같이 결정도 선택할 수 있습니다.

![해결된 경고 및 결정 드롭다운이 확장된 세부 정보 창의 스니킷입니다.](images/alert-details-resolved-true.png)

업무용 응용 프로그램에서 거짓 경고가 발생하는 경우 향후 이러한 유형의 경고를 방지하는 제거 규칙을 만들어야 합니다.

![제거 규칙이 강조 표시된 세부 정보 창의 작업 및 분류](images/alert-false-suppression-rule.png)

> [!TIP]
> 위에서 설명하지 않은 문제가 발생하는 경우 단추를 사용하여 피드백을 제공하거나 지원 🙂 티켓을 여십시오.


## <a name="related-topics"></a>관련 항목
- [엔드포인트용 Microsoft Defender 경고 큐 보기 및 구성](alerts-queue.md)
- [끝점 경고에 대한 Microsoft Defender 관리](manage-alerts.md)
- [끝점 경고에 대한 Defender와 관련된 파일 조사](investigate-files.md)
- [Endpoint 장치용 Defender 목록에서 장치 조사](investigate-machines.md)
- [끝점 경고에 대한 Defender와 연결된 IP 주소 조사](investigate-ip.md)
- [끝점 경고에 대한 Defender와 연결된 도메인 조사](investigate-domain.md)
- [Defender에서 끝점에 대한 사용자 계정 조사](investigate-user.md)


