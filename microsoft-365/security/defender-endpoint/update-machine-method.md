---
title: 컴퓨터 엔터티 API 업데이트
description: 이 API를 사용하여 컴퓨터 태그를 업데이트하는 방법을 학습합니다. 태그 및 devicevalue 속성을 업데이트할 수 있습니다.
keywords: api, 그래프 api, 지원되는 api, get, alert, information, id
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
ms.openlocfilehash: 12e4935c38a2c4748b05226237c5e31be756676c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60203990"
---
# <a name="update-machine"></a>컴퓨터 업데이트 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

기존 Machine의 속성을 [업데이트합니다.](machine.md)

업데이트할 수 있는 속성은 `machineTags` 및 `deviceValue` 입니다.

## <a name="limitations"></a>제한 사항

1. API에서 사용할 수 있는 컴퓨터를 업데이트할 수 있습니다. 
2. 업데이트 컴퓨터는 태그 컬렉션에 태그만 추가합니다. 태그가 있는 경우 태그는 본문의 tags 컬렉션에 포함되어야 합니다.
3. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.ReadWrite.All|'모든 컴퓨터의 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Machine.ReadWrite|'컴퓨터 정보 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
> - 사용자에게 최소한 '경고 조사'의 역할 권한이 필요합니다. 자세한 내용은 역할 만들기 [및 관리를 참조하세요.](user-roles.md)
> - 사용자는 장치 그룹 설정에 따라 경고와 연결된 장치에 액세스할 수 있습니다. 자세한 내용은 장치 그룹 [만들기 및 관리를 참조하세요.](machine-groups.md)

## <a name="http-request"></a>HTTP 요청

```http
PATCH /api/machines/{machineId}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.
Content-Type|String|application/json. **필수입니다**.

## <a name="request-body"></a>요청 본문

요청 본문에서 업데이트해야 하는 관련 필드의 값을 제공합니다.

요청 본문에 포함되지 않은 기존 속성은 이전 값을 유지 관리하거나 다른 속성 값의 변경 내용에 따라 다시 계산됩니다.

최상의 성능을 위해 변경되지 않은 기존 값을 포함하면 안 됩니다.

속성|유형|설명
:---|:---|:---
machineTags|문자열 컬렉션|컴퓨터 [태그](machine.md) 집합입니다.
deviceValue|Nullable Enum|디바이스의 [값입니다.](tvm-assign-device-value.md) 가능한 값은 '보통', '낮음' 및 '높음'입니다.

## <a name="response"></a>응답

성공하면 이 메서드는 200 OK를 [](machine.md) 반환하고 업데이트된 속성을 사용하여 응답 본문의 컴퓨터 엔터티를 반환합니다.

본문의 machine tags 컬렉션에 기존 컴퓨터 태그가 없는 경우 - 모든 태그를 요청 본문에 제공된 태그로 대체합니다.

지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
PATCH https://api.securitycenter.microsoft.com/api/machines/{machineId}
```

```json
{
    "deviceValue": "Normal",
    "machineTags": [
                     "Demo Device",
                     "Generic User Machine - Attack Source",
                     "Windows 10",
                     "Windows Insider - Fast"
    ]
}
```
