---
title: 자동화된 조사 후 보류 중인 작업 승인 또는 거부
description: 자동화된 조사 및 대응과 관련된 조치를 관리하는 작업 센터의 사용
keywords: 조치, 센터, 자동 공기, 자동화, 조사, 대응, 수정
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.date: 12/09/2020
ms.openlocfilehash: b34f4a532571d6215500ab2bec022489fd462d0f
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683370"
---
# <a name="approve-or-reject-pending-actions-following-an-automated-investigation"></a>자동화된 조사 후 보류 중인 작업 승인 또는 거부

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

자동화 조사가 실행되면 승인이 필요한 [수정 작업](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-remediation-actions)이 하나 이상 진행될 수 있습니다. 예를 들어 전자 메일 메시지의 클러스터를 삭제 하거나 격리된 파일을 제거해야 할 수 있습니다. 자동화된 조사가 진행되고 적시에 완료될 수 있도록 가능한 한 빨리 보류 중인 작업을 승인하거나 거부하는 것이 중요합니다. 

> [!TIP]
> Microsoft 365 Defender의 자동화된 조사 및 응답 기능으로 누락되거나 잘못 감지된 것으로 생각되면 알려주세요! [Microsoft 365 Defender의 자동화된](mtp-autoir-report-false-positives-negatives.md)조사 및 응답(AIR) 기능에서 가음성/부정을 보고하는 방법을 참조합니다.

보류 중인 작업은 작업 센터 또는 [](#review-a-pending-action-in-the-action-center) 조사 세부 정보 보기를 사용하여 검토하고 승인할 [수 있습니다.](#review-a-pending-action-in-the-investigation-details-view)

> [!NOTE]
> 수정 작업을 승인하거나 거부하려면 [적절한 사용 권한](mtp-action-center.md#required-permissions-for-action-center-tasks)이 있어야 합니다. 자세한 내용은 [Microsoft 365 Defender의](mtp-configure-auto-investigation-response.md#prerequisites-for-automated-investigation-and-response-in-microsoft-365-defender)자동화된 조사 및 대응을 위한 선행 작업을 참조하세요.

## <a name="review-a-pending-action-in-the-action-center"></a>알림 센터에서 대기 중인 작업 검토

1. [https://security.microsoft.com](https://security.microsoft.com)으로 이동하여 로그인합니다. 

2. 탐색 창에서 **알림 센터** 를 선택합니다. 

3. 알림 센터의 **보류 중인** 탭의 목록에서 항목을 선택합니다. 

    - **조사 번호** 열에서 항목을 선택하면 조사 세부 정보 페이지가 열립니다. 거기에서 조사 결과를 보고 권장 조치를 승인하거나 거부할 수 있습니다.
 
    - 목록에서 행을 선택하면 플라이 아웃이 열리면서 해당 항목에 대한 정보를 볼 수 있습니다. <br/>![조치 승인 또는 거부](../../media/air-actioncenter-itemselected.png)<br/>링크를 사용하여 연결 된 경고나 확인을 보고 작업을 승인하거나 거부합니다.

## <a name="review-a-pending-action-in-the-investigation-details-view"></a>조사 세부 정보 보기에서 보류 중인 작업을 검토합니다.

![조사 세부 정보](../../media/mtp-air-investdetails.png)

1. [조사 세부 정보](mtp-autoir-results.md) 페이지에서 **보류 중인 작업** (또는 **작업**) 탭을 선택합니다. 승인이 보류 중인 항목은 여기에 나열됩니다.

2. 목록에서 항목을 선택한 다음 **승인** 또는 **거부** 를 선택합니다.

## <a name="next-steps"></a>다음 단계

- [자동화 조사 세부정보 및 결과 보기](mtp-autoir-results.md)
- [자동화된 조사 및 응답 기능에서 가짓 긍정/부정 처리](mtp-autoir-report-false-positives-negatives.md)
