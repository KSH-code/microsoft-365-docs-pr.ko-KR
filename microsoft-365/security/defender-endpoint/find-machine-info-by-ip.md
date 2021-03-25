---
title: 내부 IP API로 장치 정보 찾기
description: 이 API를 사용하여 내부 IP로 특정 타임스탬프를 중심으로 장치 항목을 찾는 데 관련된 호출을 만들 수 있습니다.
keywords: ip, api, 그래프 api, 지원되는 api, 장치 찾기, 장치 정보
search.product: eADQiWindows 10XVcnh
ms.prod: w10
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
ms.openlocfilehash: fa1973d1c53048b04c9135a72e55ec4759412b18
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51167142"
---
# <a name="find-device-information-by-internal-ip-api"></a>내부 IP API로 장치 정보 찾기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**적용 사항:** [끝점용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)

- 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

내부 IP로 디바이스를 검색합니다.

>[!NOTE]
>타임스탬프는 지난 30일 이내에 있어야 합니다.

## <a name="permissions"></a>사용 권한
이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [끝점 API에 Microsoft Defender 사용을 참조합니다.](apis-intro.md)

사용 권한 유형 | 사용 권한 | 사용 권한 표시 이름
:---|:---|:---
응용 프로그램 | Machine.Read.All | '모든 컴퓨터 프로필 읽기'
응용 프로그램 | Machine.ReadWrite.All | '모든 컴퓨터 정보 읽기 및 쓰기'

## <a name="http-request"></a>HTTP 요청
```
GET /api/machines/find(timestamp={time},key={IP})
```

## <a name="request-headers"></a>요청 헤더

이름 | 유형 | 설명
:---|:---|:---
권한 부여 | 문자열 | Bearer {token}. **필수입니다**.


## <a name="request-body"></a>요청 본문
비어 있음

## <a name="response"></a>응답
성공적이고 컴퓨터의 경우 - 200 OK.
찾을 수 있는 컴퓨터가 없는 경우 - 404 찾을 수 없습니다.


## <a name="example"></a>예제

**요청**

다음은 요청의 예입니다.

```
GET https://graph.microsoft.com/testwdatppreview/machines/find(timestamp=2018-06-19T10:00:00Z,key='10.166.93.61')
Content-type: application/json
```

**응답**

다음은 응답의 예입니다.

응답은 타임스탬프 이전 및 이후 16분 이내에 이 IP 주소를 보고한 모든 장치의 목록을 반환합니다. 

```
HTTP/1.1 200 OK
Content-type: application/json
{
    "@odata.context": "https://graph.microsoft.com/testwdatppreview/$metadata#Machines",
    "value": [
        {
            "id": "04c99d46599f078f1c3da3783cf5b95f01ac61bb",
            "computerDnsName": "",
            "firstSeen": "2017-07-06T01:25:04.9480498Z",
            "osPlatform": "Windows10",
…
}
```
