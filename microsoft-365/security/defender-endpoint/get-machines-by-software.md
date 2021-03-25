---
title: 소프트웨어로 장치 나열
description: 이 소프트웨어가 설치된 장치 목록을 검색합니다.
keywords: api, 그래프 api, 지원되는 api, get, 목록 장치, 장치 목록, 소프트웨어로 장치 목록, mdatp tvm api
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
ms.openlocfilehash: 78cccee6380f0c403aab21eac4f07b64b8f8d510
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51200392"
---
# <a name="list-devices-by-software"></a>소프트웨어로 장치 나열

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

이 소프트웨어가 설치된 장치 참조 목록을 검색합니다.

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형 |   사용 권한  |   사용 권한 표시 이름
:---|:---|:---
응용 프로그램 | Software.Read.All | '위협 및 취약성 관리 소프트웨어 정보 읽기'
위임(직장 또는 학교 계정) | Software.Read | '위협 및 취약성 관리 소프트웨어 정보 읽기'

## <a name="http-request"></a>HTTP 요청
```
GET /api/Software/{Id}/machineReferences 
```

## <a name="request-headers"></a>요청 헤더

| 이름        | 유형 | 설명
|:--------------|:-------|:--------------|
| 권한 부여 | 문자열 | Bearer {token}. **필수 .**

## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공하면 이 메서드는 200 OK와 소프트웨어가 본문에 설치된 장치 목록을 반환합니다. 


## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```
GET https://api.securitycenter.microsoft.com/api/Software/microsoft-_-edge/machineReferences
```

**응답**

다음은 응답의 예입니다.

```json

{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "7c7e1896fa39efb0a32a2cf421d837af1b9bf762",
            "computerDnsName": "dave_desktop",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        },
        {
            "id": "7d5cc2e7c305e4a0a290392abf6707f9888fda0d",
            "computerDnsName": "jane_PC",
            "osPlatform": "Windows10",
            "rbacGroupName": "GroupTwo"
        }
        ...
    ]
}
```

## <a name="related-topics"></a>관련 항목
- [위험 기반 위협 & 관리](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)
- [위협 & 소프트웨어 인벤토리](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/tvm-software-inventory)
