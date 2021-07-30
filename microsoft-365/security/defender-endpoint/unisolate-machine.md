---
title: 장치 해제(Isolation API)
description: 이 API를 사용하여 장치를 해제할 때와 관련된 호출을 만들 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, 장치 분리
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
ms.openlocfilehash: 9dde952f8dd67084cf8d2b466f51d3077fcc4458
ms.sourcegitcommit: d817a3aecb700f7227a05cd165ffa7dbad67b09d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/29/2021
ms.locfileid: "53648899"
---
# <a name="release-device-from-isolation-api"></a>장치 해제(Isolation API)

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:** 
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

디바이스의 고르지 않은 경우

## <a name="limitations"></a>제한 사항

1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.Isolate|'컴퓨터 격리'
위임(직장 또는 학교 계정)|Machine.Isolate|'컴퓨터 격리'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/machines/{id}/unisolate
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
Comment|String|작업과 연결되는 설명입니다. **필수입니다**.

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/unisolate 
```

```json
{
  "Comment": "Unisolate machine since it was clean and validated"
}
```

장치를 격리하려면 장치 [격리를 참조하세요.](isolate-machine.md)
