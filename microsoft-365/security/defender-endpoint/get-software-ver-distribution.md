---
title: 소프트웨어 버전 배포 목록
description: 조직의 소프트웨어 버전 배포 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, 다운로드, 소프트웨어 버전 배포, 끝점 tvm api용 Microsoft Defender
search.product: eADQiWindows 10XVcnh
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 7d0e38789cfc576c0c3f1a8be352796e674ac13a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/08/2021
ms.locfileid: "52845010"
---
# <a name="list-software-version-distribution"></a>소프트웨어 버전 배포 목록 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

조직의 소프트웨어 버전 배포 목록을 검색합니다. 

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 | Software.Read.All | '위협 및 취약성 관리 소프트웨어 정보 읽기'
위임(직장 또는 학교 계정) | Software.Read | '위협 및 취약성 관리 소프트웨어 정보 읽기'

## <a name="http-request"></a>HTTP 요청
```
GET /api/Software/{Id}/distributions
```

## <a name="request-headers"></a>요청 헤더

| 이름        | 유형 | 설명
|:--------------|:-------|:--------------|
| 권한 부여 | String | Bearer {token}. **필수 .**

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공하면 이 메서드는 본문에 소프트웨어 배포 데이터 목록이 있는 200 OK를 반환합니다. 


## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/distributions
```

**응답**

다음은 응답의 예입니다.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Distributions",
    "value": [
        {
            "version": "11.0.17134.1039",
            "installations": 1,
            "vulnerabilities": 11
        },
        {
            "version": "11.0.18363.535",
            "installations": 750,
            "vulnerabilities": 0
        }
        ...
    ]
}
```

## <a name="related-topics"></a>관련 항목
- [위험 기반 위협 & 관리](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [위협 & 소프트웨어 인벤토리](/microsoft-365/security/defender-endpoint/tvm-software-inventory)
