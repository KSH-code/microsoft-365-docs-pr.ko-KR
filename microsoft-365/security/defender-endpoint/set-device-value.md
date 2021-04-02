---
title: 장치 값 설정 API
description: Microsoft Defender for Endpoint API를 사용하여 디바이스의 값을 지정하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 태그, 컴퓨터 태그
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 76df62243db837ec91819497980ff1de2295e3b6
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498313"
---
# <a name="set-device-value-api"></a>장치 값 설정 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명

특정 컴퓨터의 장치 값을 [설정합니다.](machine.md)<br>
자세한 [내용은 장치 값](tvm-assign-device-value.md) 할당을 참조하세요.

## <a name="limitations"></a>제한 사항

1. 구성된 보존 기간에 따라 마지막으로 본 장치에 게시할 수 있습니다.

2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |    사용 권한    |    사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |    Machine.ReadWrite.All |    '모든 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정) | Machine.ReadWrite | '컴퓨터 정보 읽기 및 쓰기'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
>- 사용자에게 최소한 '보안 설정 관리'의 역할 권한이 필요합니다. 자세한 내용은 [역할 만들기](user-roles.md) 및 관리를 참조하세요.
>- 사용자는 컴퓨터 그룹 설정에 따라 컴퓨터 액세스 권한이 필요합니다(자세한 내용은 컴퓨터 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
POST https://api.securitycenter.microsoft.com/api/machines/{machineId}/setDeviceValue
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.
Content-Type | 문자열 | application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에 다음 매개 변수를 사용하여 JSON 개체를 제공합니다.

매개 변수 |    유형    | 설명
:---|:---|:---
DeviceValue |    Enum |    장치 값입니다. 허용되는 값은 '보통', '낮음' 및 '높음'입니다. **필수입니다**.

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 200 - 확인 응답 코드와 업데이트된 Machine을 반환합니다.

## <a name="example"></a>예제

**요청**

다음은 컴퓨터 태그를 추가하는 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/setDeviceValue
```

```json
{
  "DeviceValue" : "High"
}
```
