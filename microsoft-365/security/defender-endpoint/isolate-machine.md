---
title: 컴퓨터 격리 API
description: 컴퓨터 격리 API를 사용하여 디바이스가 끝점용 Microsoft Defender의 외부 네트워크에 액세스하지 못하게 격리하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 장치 격리
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
ms.technology: mde
ms.openlocfilehash: b9c8d4da528ba065dc1b4a68ddaa816a1ad78c4a
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187839"
---
# <a name="isolate-machine-api"></a>컴퓨터 격리 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
장치가 외부 네트워크에 액세스하지 않습니다.


## <a name="limitations"></a>제한 사항
1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


[!include[Device actions note](../../includes/machineactionsnote.md)]

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   Machine.Isolate |   '컴퓨터 격리'
위임(직장 또는 학교 계정) | Machine.Isolate |  '컴퓨터 격리'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 최소한 '활성 수정 작업' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
>- 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).


## <a name="http-request"></a>HTTP 요청
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/isolate
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.
Content-Type | 문자열 | application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문
요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수 | 유형    | 설명
:---|:---|:---
Comment |   String |    작업과 연결되는 설명입니다. **필수입니다**.
IsolationType   | 문자열 |  Olation의 유형입니다. 허용되는 값은 '전체' 또는 '선택적'입니다.

**IsolationType은** 수행할 단리 유형을 제어하며 다음 중 하나일 수 있습니다.
- 전체 – 전체 고리
- 선택적 – 제한된 응용 프로그램 집합만 네트워크에 [](respond-machine-alerts.md#isolate-devices-from-the-network) 액세스하지 못하도록 제한합니다(자세한 내용은 네트워크에서 장치 격리 참조).


## <a name="response"></a>응답
성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.


## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/isolate
```

```json
{
  "Comment": "Isolate machine due to alert 1234",
  "IsolationType": "Full" 
}
```

- 장치를 고리에서 해제하려면 장치 해제를 [참조하세요.](unisolate-machine.md)
