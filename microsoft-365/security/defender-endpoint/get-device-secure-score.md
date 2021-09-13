---
title: 장치 보안 점수 가져오기
description: 조직 장치 보안 점수를 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: dansimp
ms.author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 0a875e6dcbe41237d86cd1e0003e8d9f6549e18f
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221491"
---
# <a name="get-device-secure-score"></a>장치 보안 점수 가져오기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

장치에 [대한 Microsoft 보안 점수를 검색합니다.](tvm-microsoft-secure-score-devices.md) 장치에 대한 Microsoft 보안 점수가 높을수록 끝점이 사이버 보안 위협 공격으로부터 더 탄력적입니다.

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|Score.Read.All|'위협 및 취약성 관리 점수 읽기'
위임(직장 또는 학교 계정)|Score.Read|'위협 및 취약성 관리 점수 읽기'

## <a name="http-request"></a>HTTP 요청

```http
GET /api/configurationScore
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
:---|:---|:---
권한 부여|문자열|Bearer {token}. **필수입니다**.

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 응답 본문에 장치 보안 점수 데이터를 사용하여 200 OK를 반환합니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/configurationScore
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

> [!NOTE]
> 여기에 표시된 응답 목록은 표시가 까다로우면 자르기될 수 있습니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#ConfigurationScore/$entity",
    "time": "2019-12-03T09:15:58.1665846Z",
    "score": 340
}
```

## <a name="see-also"></a>참고 항목

- [끝점용 Microsoft Defender를 사용하여 OData 쿼리](exposed-apis-odata-samples.md)
