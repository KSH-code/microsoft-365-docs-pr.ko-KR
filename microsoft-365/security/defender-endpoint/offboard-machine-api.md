---
title: 컴퓨터 오프보드 API
description: API를 사용하여 끝점용 Microsoft Defender의 디바이스 등록을 해제하는 방법을 학습합니다.
keywords: api, 그래프 api, 지원되는 api, 조사 패키지 수집
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
ms.openlocfilehash: 03a1ef11224021703a6f33f82fa2c4f135a317a7
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934180"
---
# <a name="offboard-machine-api"></a>컴퓨터 오프보드 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 



[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="api-description"></a>API 설명
Endpoint용 Defender에서 디바이스를 오프보드합니다.


## <a name="limitations"></a>제한 사항
 - 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.


[!include[Machine actions note](../../includes/machineactionsnote.md)]

>[!Note]
> 이 API는 Windows 10 버전 1703 이상 또는 Windows Server 2019 이상에서 지원됩니다. 이 API는 MacOS 또는 Linux 장치에서 지원되지 않습니다.

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 끝점 API에 [Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 |   Machine.Offboard |  '컴퓨터 오프보드'
위임(직장 또는 학교 계정) |    Machine.Offboard |  '컴퓨터 오프보드'

>[!Note]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>- 사용자에게 '전역 관리자' AD 역할이 필요합니다.
>- 사용자는 장치 그룹 설정에 따라 장치에 액세스할 수 있습니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청
```
POST https://api.securitycenter.microsoft.com/api/machines/{id}/offboard
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

## <a name="response"></a>응답
성공하면 이 메서드는 응답 본문에 201 - 생성된 응답 코드 및 [컴퓨터](machineaction.md) 작업을 반환합니다.


## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```http
POST https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/offboard
```

```json
{
  "Comment": "Offboard machine by automation"
}
```
