---
title: 경고 엔터티 API 업데이트
description: 이 API를 사용하여 끝점용 Microsoft Defender 경고를 업데이트하는 방법을 학습합니다. 상태, 결정, 분류 및 assignedTo 속성을 업데이트할 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, get, alert, information, id
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
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 00c02bad3f95d2bd8def69d5dd6ad8e1c2e857df
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59213365"
---
# <a name="update-alert"></a>업데이트 경고

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명
기존 Alert의 속성을 [업데이트합니다.](alerts.md)

설명 **제출은** 속성을 업데이트하거나 업데이트하지 않고 사용할 수 있습니다.

업데이트할 수 있는 속성은 `status` `determination` , 및 `classification` `assignedTo` 입니다.

## <a name="limitations"></a>제한 사항

1. API에서 사용할 수 있는 경고를 업데이트할 수 있습니다. 자세한 [내용은 목록 경고를](get-alerts.md) 참조하세요.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Alerts.ReadWrite.All|'모든 경고 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Alert.ReadWrite|'경고 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '경고 조사'와 같은 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
PATCH /api/alerts/{id}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.
Content-Type|String|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에서 업데이트해야 하는 관련 필드의 값을 제공합니다.

요청 본문에 포함되지 않은 기존 속성은 이전 값을 유지 관리하거나 다른 속성 값의 변경 내용에 따라 다시 계산됩니다.

최상의 성능을 위해 변경되지 않은 기존 값은 포함하지 말아야 합니다.

속성|유형|설명
:---|:---|:---
status|String|경고의 현재 상태를 지정합니다. 속성 값은 'New', 'InProgress' 및 'Resolved'입니다.
assignedTo|String|경고의 소유자
classification|String|경고의 사양을 지정합니다. 속성 값은 '알 수 없음', 'FalsePositive', 'TruePositive'입니다.
determination|String|경고 결정 속성 값은 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'입니다.
comment|문자열|경고에 추가할 설명입니다.

## <a name="response"></a>응답

성공하면 이 메서드는 200 OK를 [](alerts.md) 반환하고 업데이트된 속성을 사용하여 응답 본문의 경고 엔터티를 반환합니다. 지정된 ID가 있는 알림을 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
PATCH https://api.securitycenter.microsoft.com/api/alerts/121688558380765161_2136280442
```

```json
{
    "status": "Resolved",
    "assignedTo": "secop2@contoso.com",
    "classification": "FalsePositive",
    "determination": "Malware",
    "comment": "Resolve my alert and assign to secop2"
}
```
