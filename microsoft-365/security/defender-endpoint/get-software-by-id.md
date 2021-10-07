---
title: ID로 소프트웨어 다운로드
description: ID로 소프트웨어 세부 정보 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, software, Endpoint tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 098edd5b0857e7bd771be7d28fee965934b9bc67
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60205454"
---
# <a name="get-software-by-id"></a>ID로 소프트웨어 다운로드

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

ID로 소프트웨어 세부 정보를 검색합니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Software.Read.All|'위협 및 취약성 관리 소프트웨어 정보 읽기'
위임(직장 또는 학교 계정)|Software.Read|'위협 및 취약성 관리 소프트웨어 정보 읽기'

## <a name="http-request"></a>HTTP 요청

```http
GET /api/Software/{Id}
```

## <a name="request-headers"></a>요청 헤더

이름|유형|설명
---|---|---
권한 부여|String|Bearer {token}. **필수 .**

## <a name="request-body"></a>요청 본문

비어 있음

## <a name="response"></a>응답

성공하면 이 메서드는 본문에 지정된 소프트웨어 데이터를 사용하여 200 OK를 반환합니다.

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

다음은 요청의 예입니다.

```http
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge
```

### <a name="response-example"></a>응답 예제

다음은 응답의 예입니다.

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Software/$entity",
    "id": "microsoft-_-edge",
    "name": "edge",
    "vendor": "microsoft",
    "weaknesses": 467,
    "publicExploit": true,
    "activeAlert": false,
    "exposedMachines": 172,
    "impactScore": 2.39947438
}
```

## <a name="related-topics"></a>관련 항목

- [위험 기반 위협 & 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [위협 & 소프트웨어 인벤토리](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
