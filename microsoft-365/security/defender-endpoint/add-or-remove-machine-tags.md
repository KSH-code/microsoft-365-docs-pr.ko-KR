---
title: 컴퓨터 태그 API 추가 또는 제거
description: 컴퓨터 태그 추가 또는 제거 API를 사용하여 끝점용 Microsoft Defender에서 컴퓨터의 태그를 추가하거나 제거하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 태그, 컴퓨터 태그
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
ms.openlocfilehash: 15eef9097687e794c8aa88d8625fd481adb117af
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208616"
---
# <a name="add-or-remove-machine-tags-api"></a>컴퓨터 태그 API 추가 또는 제거

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

특정 Machine 에 태그를 추가하거나 [제거합니다.](machine.md)

## <a name="limitations"></a>제한 사항

1. 구성된 보존 기간에 따라 마지막으로 본 컴퓨터를 게시할 수 있습니다.

2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 끝점 API에 [Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.ReadWrite.All|'모든 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Machine.ReadWrite|'컴퓨터 정보 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '보안 설정 관리'의 역할 권한이 필요합니다. 자세한 내용은 [역할 만들기](user-roles.md) 및 관리를 참조하세요.
> - 사용자는 컴퓨터 그룹 설정에 따라 컴퓨터 액세스 권한이 필요합니다(자세한 내용은 컴퓨터 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/tags
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.
Content-Type|문자열|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수|유형|설명
:---|:---|:---
값|String|태그 이름입니다. **필수입니다**.
작업|Enum|추가 또는 제거. 허용되는 값은 '추가' 또는 '제거'입니다. **필수입니다**.

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 업데이트된 Machine을 반환합니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 컴퓨터 태그를 추가하는 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/tags
```

```json
{
  "Value" : "test Tag 2",
  "Action": "Add"
}
```

- 컴퓨터 태그를 제거하려면 요청 본문에서 동작이 '추가' 대신 '제거'로 설정됩니다.
