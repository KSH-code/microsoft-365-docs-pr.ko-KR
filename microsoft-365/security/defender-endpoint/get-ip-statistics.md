---
title: IP 통계 API를 얻습니다.
description: 끝점용 Microsoft Defender를 사용하여 IP에 대한 최신 통계를 얻습니다.
keywords: api, 그래프 api, 지원되는 api, get, ip, 통계, 보전
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
ms.openlocfilehash: 6bcabc069bd79444802ca7487de93719cb2bee00
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221344"
---
# <a name="get-ip-statistics-api"></a>IP 통계 API를 얻습니다.

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명
지정한 IP에 대한 통계를 검색합니다.

## <a name="limitations"></a>제한 사항
1. 이 API에 대한 속도 제한은 분당 100통 및 시간당 1500통입니다.
2. Lookbackhours의 최대값은 720시간(30일)입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Ip.Read.All|'IP 주소 프로필 읽기'
위임(직장 또는 학교 계정)|Ip.Read.All|'IP 주소 프로필 읽기'

> [!NOTE]
> 사용자 자격 증명을 사용하여 토큰을 얻을 때:
> - 사용자에게 최소한 '데이터 보기' 역할 권한이 필요합니다(자세한 내용은 역할 [만들기](user-roles.md) 및 관리 참조).

## <a name="http-request"></a>HTTP 요청

```http
GET /api/ips/{ip}/stats
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|문자열|Bearer {token}. **필수입니다**.

## <a name="request-uri-parameters"></a>요청 URI 매개 변수

이름|유형|설명
:---|:---|:---
lookBackHours|Int32|통계를 얻기 위해 다시 검색하는 시간을 정의합니다. 기본값은 30일입니다. 선택 사항입니다.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공 및 ip가 있는 경우 - 본문에 통계 데이터가 있는 200 OK. IP가 유효하지만 존재하지 않습니다. organizationPrevalence 0, IP가 잘못되었습니다. HTTP 400.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/ips/10.209.67.177/stats?lookBackHours=48
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.InOrgIPStats",
    "ipAddress": "10.209.67.177",
    "organizationPrevalence": 63515,
    "orgFirstSeen": "2017-07-30T13:36:06Z",
    "orgLastSeen": "2017-08-29T13:32:59Z"
}
```

|이름|설명|
|---|---|
|조직 보전|이 IP에 대한 네트워크 연결을 연 장치의 고유한 수입니다.|
|처음으로 본 Org|조직에서 이 IP에 대한 첫 번째 연결입니다.|
|마지막으로 본 Org|조직에서 이 IP에 대한 마지막 연결입니다.|

> [!NOTE]
> 이 통계 정보는 지난 30일간의 데이터를 기반으로 합니다.
