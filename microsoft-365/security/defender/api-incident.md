---
title: Microsoft 365 수비수 인시던트 API 및 인시던트 리소스 유형
description: Microsoft 365 Defender에서 인시던트 리소스 유형의 메서드 및 속성에 대해 알아보기
keywords: 인시던트, 인시던트, API
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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 5cc149668e49e21b38b5fb95ae3f40db6c296e1d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572588"
---
# <a name="microsoft-365-defender-incidents-api-and-the-incident-resource-type"></a>Microsoft 365 수비수 인시던트 API 및 인시던트 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 일부 정보는 상용으로 출시되기 전에 실질적으로 수정될 수 있는 사전 릴리스된 제품과 관련이 있습니다. Microsoft는 여기에서 제공하는 정보와 관련하여 명시적이거나 묵시적인 어떠한 보증도 제공하지 않습니다.

[인시던트는](incidents-overview.md) 공격을 설명하는 데 도움이 되는 관련 경고 모음입니다. 조직의 여러 엔터티의 이벤트는 Microsoft 365 Defender에 의해 자동으로 집계됩니다. 인시던트 API를 사용하여 조직의 인시던트 및 관련 경고에 프로그래밍하여 액세스할 수 있습니다.

## <a name="quotas-and-resource-allocation"></a>할당량 및 리소스 할당

분당 최대 50건의 통화 또는 시간당 1,500건의 통화를 요청할 수 있습니다. 각 메서드에는 자체 할당량도 있습니다. 메서드별 할당량에 대한 자세한 내용은 사용하려는 메서드에 대한 각 문서를 참조하세요.

`429`HTTP 응답 코드는 전송된 요청 수 또는 할당된 실행 시간으로 할당량에 도달했음을 나타냅니다. 응답 본문에는 도달한 할당량이 재설정될 때까지의 시간이 포함됩니다.

## <a name="permissions"></a>권한

인시던트 API에는 각 메서드에 대해 서로 다른 종류의 권한이 필요합니다. 필요한 권한에 대한 자세한 내용은 각 메서드의 문서를 참조하십시오.

## <a name="methods"></a>메서드

메서드 | 리턴 타입 | 설명
-|-|-
[인시던트 열거](api-list-incidents.md) | [인시던트](api-incident.md) 목록 | 인시던트 목록을 가져옵니다.
[인시던트 업데이트](api-update-incidents.md) | [인시던트](api-incident.md) | 특정 인시던트를 업데이트합니다.

## <a name="request-body-response-and-examples"></a>본문, 응답 및 예제 요청

요청을 구성하거나 응답을 구문 분석하는 방법과 실제 예제에 대한 자세한 내용은 각 메서드 문서를 참조하십시오.

## <a name="common-properties"></a>공통 속성

속성 | 유형 | 설명
-|-|-
인시던트Id | long | 인시던트 고유 ID입니다.
리디렉션우연히이드 | 무효화 할 수 있는 긴 | 현재 인시던트인시던트 ID가 병합되었습니다.
인시던트 이름 | 문자열 | 인시던트 이름입니다.
만든 시간 | 날짜 시간 오프셋 | 인시던트(UTC)에서 인시던트가 생성된 날짜와 시간입니다.
마지막 업데이트 시간 | 날짜 시간 오프셋 | 인시던트(UTC)에서 인시던트가 마지막으로 업데이트되었습니다.
할당To | 문자열 | 사건의 소유자.
심각도 | 이넘 (주) | 사건의 심각도. 가능한 값은 다음과 ```UnSpecified``` ```Informational``` ```Low``` ```Medium``` ```High``` 같습니다.
상태 | 이넘 (주) | 인시던트의 현재 상태를 지정합니다. 가능한 값은 다음과 ```Active``` ```Resolved``` ```Redirected``` 같습니다.
분류 | 이넘 (주) | 인시던트 사양입니다. 가능한 값은 다음과 ```Unknown``` ```FalsePositive``` ```TruePositive``` 같습니다.
결심 | 이넘 (주) | 인시던트 의 결정을 지정합니다. 가능한 값은 다음과 같습니다 : ```NotAvailable``` , , , , , , ```Apt``` ```Malware``` ```SecurityPersonnel``` ```SecurityTesting``` ```UnwantedSoftware``` . ```Other```
태그 | 문자열 목록 | 인시던트 태그 목록입니다.
코멘트 | 인시던트 댓글 목록 | 인시던트 주석 개체에는 주석 문자열, 생성됨 문자열 및 createTime 날짜 시간이 포함됩니다.
경고 | 경고 목록 | 관련 경고 목록입니다. [인시던트 목록](api-list-incidents.md) API 설명서에서 예제를 참조하십시오.

## <a name="related-articles"></a>관련 문서

- [Microsoft 365 수비수 API 개요](api-overview.md)
- [인시던트 개요](incidents-overview.md)
- [인시던트 API 목록](api-list-incidents.md)
- [인시던트 API 업데이트](api-update-incidents.md)
