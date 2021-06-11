---
title: 장치에서 라이브 응답 명령 실행
description: 디바이스에서 일련의 라이브 응답 명령을 실행하는 방법을 확인합니다.
keywords: api, 그래프 api, 지원되는 api, 라이브러리에 업로드
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 2a7daf18b1a1d791e7b92ded0a6b839bba1fd4c2
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/10/2021
ms.locfileid: "52879703"
---
#  <a name="run-live-response-commands-on-a-device"></a>장치에서 라이브 응답 명령 실행

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2146631)


[!include[Prerelease information](../../includes/prerelease.md)]

>끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

디바이스에서 일련의 라이브 응답 명령 실행

## <a name="limitations"></a>제한 사항

1.  이 API에 대한 속도 제한은 분당 10통입니다(추가 요청은 HTTP 429로 응답).

2.  25개 세션을 동시 실행합니다(제한 제한을 초과하는 요청은 "429 - 요청 수가 너무 많음" 응답이 수신됩니다).

3.  머신을 사용할 수 없는 경우 세션은 최대 3일 동안 대기됩니다.

4.  RunScript 명령 시간 제한은 10분 후입니다.

5.  라이브 응답 명령이 실패하면 모든 후속 작업이 실행되지 않습니다.

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [시작을 참조합니다.](apis-intro.md)

| 사용 권한 유형                    | 사용 권한           | 사용 권한 표시 이름                   |
|------------------------------------|----------------------|-------------------------------------------|
| 응용 프로그램                        | Machine.LiveResponse | 특정 컴퓨터의 실시간 응답 실행 |
| 위임(직장 또는 학교 계정) | Machine.LiveResponse | 특정 컴퓨터의 실시간 응답 실행 |

## <a name="http-request"></a>HTTP 요청

```HTTP
POST
https://api.securitycenter.microsoft.com/API/machines/{machine_id}/runliveresponse
```

## <a name="request-headers"></a>요청 헤더

| 이름      | 유형 | 설명                 |
|---------------|----------|---------------------------------|
| 권한 부여 | String   | Bearer\<token>\. 필수 특성입니다.   |
| Content-Type  | 문자열   | application/json. 필수 특성입니다. |

## <a name="request-body"></a>요청 본문

| 매개 변수 | 유형 | 설명                                                        |
|---------------|----------|------------------------------------------------------------------------|
| Comment       | String   | 작업과 연결되는 설명입니다.                                 |
| 명령      | 배열    | 실행할 명령입니다. 허용되는 값은 PutFile, RunScript, GetFile입니다. |

명령:

| 명령 유형 | 매개 변수                                                                          | 설명                                                                                                                      |
|------------------|-----------------------------------------------------------------------------------------|--------------------------------------------------------------------------------------------------------------------------------------|
| PutFile      | 키: FileName  <br><br>  값: \<file name\>                                                                          | 라이브러리에서 장치로 파일을 넣습니다. 파일은 작업 폴더에 저장되고 장치가 기본적으로 다시 시작될 때 삭제됩니다.
| RunScript    | 키: ScriptName<br>값: \<Script from library\> <br><br> 키: Args  <br> 값: \<Script arguments\>                          | 디바이스의 라이브러리에서 스크립트를 실행합니다.    <br><br>  Args 매개 변수는 스크립트로 전달됩니다. <br><br> 10분 후의 시간 제한입니다.     
| GetFile      | 키: Path <br> 값: \<File path\>                                                        | 장치에서 파일을 수집합니다. 참고: 경로의 백슬래시를 이스케이프해야 합니다.                                                                      |

## <a name="response"></a>응답

-   성공하면 이 메서드는 200, 확인을 반환합니다.
    작업 엔터티. 지정한 ID가 있는 머신을 찾을 수 없는 경우 - 404 찾을 수 없습니다.

## <a name="example"></a>예시

**요청**

다음은 요청의 예입니다.

```HTTP

POST
https://api.securitycenter.microsoft.com/api/machines/1e5bc9d7e413ddd7902c2932e418702b84d0cc07/runliveresponse

```
**JSON**

```JSON
{
   "Commands":[
      {
         "type":"RunScript",
         "params":[
            {
               "key":"ScriptName",
               "value":"minidump.ps1"
            },
            {
               "key":"Args",
               "value":"OfficeClickToRun"
            }

         ]
      },
      {
         "type":"GetFile",
         "params":[
            {
               "key":"Path",
               "value":"C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
            }
         ]
      }
   ],
   "Comment":"Testing Live Response API"
}
```

**응답**

다음은 응답의 예입니다.

```HTTP
HTTP/1.1 200 Ok
```

콘텐츠 형식: application/json

```JSON
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#MachineActions/$entity",
    "id": "{machine_action_id}",
    "type": "LiveResponse",
    "requestor": "analyst@microsoft.com",
    "requestorComment": "Testing Live Response API",
    "status": "Pending",
    "machineId": "{machine_id}",
    "computerDnsName": "hostname",
    "creationDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "lastUpdateDateTimeUtc": "2021-02-04T15:36:52.7788848Z",
    "errorHResult": 0,
    "commands": [
        {
            "index": 0,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "RunScript",
                "params": [
                    {
                        "key": "ScriptName",
                        "value": "minidump.ps1"
                    },{
                        "key": "Args",
                        "value": "OfficeClickToRun"
                    }
                ]
            }
        }, {
            "index": 1,
            "startTime": null,
            "endTime": null,
            "commandStatus": "Created",
            "errors": [],
            "command": {
                "type": "GetFile",
                "params": [{
                        "key": "Path", "value": "C:\\windows\\TEMP\\OfficeClickToRun.dmp.zip"
                    }
                ]
            }
        }
    ]
}


```

## <a name="related-topics"></a>관련 항목
- [컴퓨터 작업 API를 얻습니다.](get-machineaction-object.md)
- [라이브 응답 결과 얻기](get-live-response-result.md)
- [컴퓨터 작업 취소](cancel-machine-action.md)
