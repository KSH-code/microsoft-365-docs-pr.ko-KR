---
title: 내부 IP API로 장치 찾기
description: 요청된 내부 IP가 제공된 타임스탬프 이전 및 이후 15분의 시간 범위에 있는 장치 찾기
keywords: api, 그래프 api, 지원되는 api, get, 장치, IP, 찾기, 장치 찾기, ip, ip
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
ms.openlocfilehash: c2b94dfee30e447aed553e2fdaca62af8ec82f8b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60157953"
---
# <a name="find-devices-by-internal-ip-api"></a>내부 IP API로 장치 찾기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

[요청된](machine.md) 내부 IP가 제공된 타임스탬프 이전 및 이후 15분의 시간 범위에 있는 컴퓨터를 찾을 수 있습니다.

## <a name="limitations"></a>제한 사항

1. 주어진 타임스탬프는 지난 30일 동안의 기간이 되어야 합니다.
2. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Machine.Read.All|'모든 컴퓨터 프로필 읽기'
응용 프로그램|Machine.ReadWrite.All|'모든 컴퓨터 정보 읽기 및 쓰기'
위임(직장 또는 학교 계정)|Machine.Read|'컴퓨터 정보 읽기'
위임(직장 또는 학교 계정)|Machine.ReadWrite|'컴퓨터 정보 읽기 및 쓰기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
>
> - 응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).
> - 응답에는 사용자가 장치 그룹 설정에 따라 액세스할 수 있는 장치만 포함됩니다(자세한 내용은 장치 그룹 만들기 및 [관리](machine-groups.md) 참조).

## <a name="http-request"></a>HTTP 요청

```http
GET /api/machines/findbyip(ip='{IP}',timestamp={TimeStamp})
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|String|Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공적이면 - 응답 본문에 컴퓨터 목록이 있는 200 OK.
타임스탬프가 지난 30일 ( 400 잘못된 요청)에 있지 않은 경우

## <a name="example"></a>예제

### <a name="request"></a>요청

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/machines/findbyip(ip='10.248.240.38',timestamp=2019-09-22T08:44:05Z)
```
