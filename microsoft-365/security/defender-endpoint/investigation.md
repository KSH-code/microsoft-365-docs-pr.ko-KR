---
title: 조사 리소스 유형
description: 끝점 조사 엔터티용 Microsoft Defender.
keywords: api, 그래프 api, 지원되는 api, get, 경고, 조사
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 252b273995d48d523604802c0c4365a613d86dbe
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2021
ms.locfileid: "52771732"
---
# <a name="investigation-resource-type"></a>조사 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

끝점용 Defender의 자동화된 조사 엔터티를 나타냅니다.
<br> 자세한 [내용은 자동화된](automated-investigations.md) 조사 개요를 참조하세요.

## <a name="methods"></a>메서드
메서드|반환 형식 |설명
:---|:---|:---
[조사 목록](get-investigation-collection.md) | 조사 컬렉션 | 조사 컬렉션을 얻습니다.
[단일 조사하기](get-investigation-object.md) | 조사 엔터티 | 단일 조사 엔터티를 만듭니다.
[조사 시작](initiate-autoir-investigation.md) | 조사 엔터티 | 장치에서 조사를 시작합니다.


## <a name="properties"></a>특성
속성 |  유형    |   설명
:---|:---|:---
id | String | 조사 엔터티의 ID입니다. 
startTime | DateTime Nullable | 조사를 만든 날짜 및 시간입니다. 
endTime | DateTime Nullable | 조사가 완료된 날짜 및 시간입니다. 
cancelledBy | String | 해당 조사를 취소한 사용자/응용 프로그램의 ID입니다. 
investigationState | Enum | 조사의 현재 상태입니다. 가능한 값은 '알 수 없음', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.
statusDetails | String | 조사 상태 관련 추가 정보입니다.
machineId | String | 조사가 실행되는 장치의 ID입니다.
computerDnsName | String | 조사가 실행되는 장치의 이름입니다.
triggeringAlertId | String | 조사를 트리거한 경고의 ID입니다.


## <a name="json-representation"></a>Json 표현

```json
{
    "id": "63004",
    "startTime": "2020-01-06T13:05:15Z",
    "endTime": null,
    "state": "Running",
    "cancelledBy": null,
    "statusDetails": null,
    "machineId": "e828a0624ed33f919db541065190d2f75e50a071",
    "computerDnsName": "desktop-test123",
    "triggeringAlertId": "da637139127150012465_1011995739"
}
```
