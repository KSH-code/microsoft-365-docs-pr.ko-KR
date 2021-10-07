---
title: 표시기 API 삭제.
description: 지표 삭제 API를 사용하여 끝점용 Microsoft Defender에서 ID로 표시기 엔터티를 삭제하는 방법을 학습합니다.
keywords: api, 공개 api, 지원되는 api, 삭제, ti 표시기, 엔터티, ID
search.product: eADQiWindows 10XVcnh
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
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7d1c235c66472d5c09e8993783c92a134fc0d05b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211306"
---
# <a name="delete-indicator-api"></a>표시기 삭제 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명

ID로 [Indicator](ti-indicator.md) 엔터티를 삭제합니다.

## <a name="limitations"></a>제한 사항

이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

사용 권한 유형 | 사용 권한 | 사용 권한 표시 이름
:---|:---|:---
응용 프로그램 | Ti.ReadWrite | 'TI 지표 읽기 및 쓰기'
응용 프로그램 | Ti.ReadWrite.All | '읽기 및 쓰기 표시기'

## <a name="http-request"></a>HTTP 요청

```http
Delete https://api.securitycenter.microsoft.com/api/indicators/{id}
```

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여 | String | Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

Indicator가 존재하고 삭제된 경우 - 콘텐츠가 없는 204 OK.

지정한 ID가 있는 Indicator를 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
DELETE https://api.securitycenter.microsoft.com/api/indicators/995
```
