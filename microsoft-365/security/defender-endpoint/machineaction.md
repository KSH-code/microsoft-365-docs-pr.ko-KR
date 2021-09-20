---
title: machineAction 리소스 유형
description: 끝점용 Microsoft Defender의 MachineAction 리소스 유형의 메서드 및 속성에 대해 자세히 알아보습니다.
keywords: api, 지원되는 api, get, machineaction, recent
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
ms.openlocfilehash: 33df420b8b480b6957e2ec71b3bb5494f61fce63
ms.sourcegitcommit: 7be84e7940c63b4c958b9da875d323bead9aae95
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/20/2021
ms.locfileid: "59453619"
---
# <a name="machineaction-resource-type"></a>MachineAction 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 자세한 내용은 응답 [작업을 참조하세요.](respond-machine-alerts.md)

|방법|반환 형식|설명|
|---|---|---|
|[MachineActions 목록](get-machineactions-collection.md)|[컴퓨터 작업](machineaction.md)|컴퓨터 [작업 엔터티를](machineaction.md) 나열합니다.|
|[MachineAction 사용](get-machineaction-object.md)|[컴퓨터 작업](machineaction.md)|단일 컴퓨터 작업 [엔터티를](machineaction.md) 얻습니다.|
|[조사 패키지 수집](collect-investigation-package.md)|[컴퓨터 작업](machineaction.md)|컴퓨터 에서 조사 패키지를 [수집합니다.](machine.md)|
|[조사 패키지 SAS URI 가져오기](get-package-sas-uri.md)|[컴퓨터 작업](machineaction.md)|조사 패키지 다운로드를 위한 URI를 다운로드합니다.|
|[컴퓨터 격리](isolate-machine.md)|[컴퓨터 작업](machineaction.md)|네트워크에서 [컴퓨터](machine.md) 격리.|
|[컴퓨터 격리 해제](unisolate-machine.md)|[컴퓨터 작업](machineaction.md)|[컴퓨터의](machine.md) 고리에서 해제합니다.|
|[앱 실행 제한](restrict-code-execution.md)|[컴퓨터 작업](machineaction.md)|응용 프로그램 실행을 제한합니다.|
|[앱 제한 제거](unrestrict-code-execution.md)|[컴퓨터 작업](machineaction.md)|응용 프로그램 실행 제한을 제거합니다.|
|[바이러스 백신 검사 실행](run-av-scan.md)|[컴퓨터 작업](machineaction.md)|해당되는 경우 Windows Defender 사용하여 AV 스캔을 실행합니다.|
|[컴퓨터 오프보딩](offboard-machine-api.md)|[컴퓨터 작업](machineaction.md)|[끝점용](machine.md) Microsoft Defender에서 컴퓨터 오프보드.|
|[파일을 중지하고 격리](stop-and-quarantine-file.md)|[컴퓨터 작업](machineaction.md)|컴퓨터의 파일 실행을 중지하고 삭제합니다.|
|[실시간 응답 실행](run-live-response.md)|[컴퓨터 작업](machineaction.md)|디바이스에서 일련의 라이브 응답 명령 실행|
|[라이브 응답 결과 가져오기](get-live-response-result.md)|URL 엔터티|인덱스로 특정 라이브 응답 명령 결과 다운로드 링크를 검색합니다.|
|[컴퓨터 작업 취소](cancel-machine-action.md)|[컴퓨터 작업](machineaction.md)|활성 컴퓨터 작업을 취소합니다.|

<br>

## <a name="properties"></a>속성

|속성|유형|설명|
|---|---|---|
|ID|Guid|[Machine Action 엔터티의 ID입니다.](machineaction.md)|
|type|Enum|작업의 유형입니다. 가능한 값은 "RunAntiVirusScan", "Offboard", "Live Response", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" 및 "UnrestrictCodeExecution"입니다.|
|scope|문자열|작업의 범위입니다. 바이러스 백신 검사의 경우 "전체" 또는 "선택적" 및 "빠른" 또는 "전체"입니다.|
|requestor|String|작업을 실행한 사람의 ID입니다.|
|externalID|String|고객이 사용자 지정 상관 관계 요청에 제출할 수 있는 ID입니다.|
|requestSource|문자열|작업을 제출한 사용자/응용 프로그램의 이름입니다.|
| 명령|array|실행할 명령입니다. 허용되는 값은 PutFile, RunScript, GetFile입니다.|
|cancellationRequestor|String|작업을 취소한 사람의 ID입니다.|
|requestorComment|String|작업을 실행할 때 작성된 설명입니다.|
|cancellationComment|String|작업을 취소할 때 작성된 설명입니다.|
|status|Enum|명령의 현재 상태입니다. 가능한 값은 "Pending", "InProgress", "Succeeded", "Failed", "TimeOut" 및 "Cancelled"입니다.|
|machineId|String|작업이 실행된 컴퓨터의 ID입니다. [](machine.md)|
|computerDnsName|String|작업이 [실행된](machine.md) 컴퓨터의 이름입니다.|
|creationDateTimeUtc|DateTimeOffset|작업을 만든 날짜 및 시간입니다.|
|cancellationDateTimeUtc|DateTimeOffset|작업이 취소된 날짜 및 시간입니다.|
|lastUpdateDateTimeUtc|DateTimeOffset|작업 상태가 업데이트된 마지막 날짜 및 시간입니다.|
|title|String|컴퓨터 작업 제목입니다.|
|relatedFileInfo|클래스|두 속성이 들어 있습니다. string , Enum 값으로 `fileIdentifier` `fileIdentifierType` "Sha1", "Sha256" 및 "Md5"를 지정합니다.|

## <a name="json-representation"></a>Json 표현

```json
{
        "id": "5382f7ea-7557-4ab7-9782-d50480024a4e",
        "type": "Isolate",
        "scope": "Selective",
        "requestor": "Analyst@TestPrd.onmicrosoft.com",
        "requestorComment": "test for docs",
        "status": "Succeeded",
        "machineId": "7b1f4967d9728e5aa3c06a9e617a22a4a5a17378",
        "computerDnsName": "desktop-test",
        "creationDateTimeUtc": "2019-01-02T14:39:38.2262283Z",
        "lastUpdateDateTimeUtc": "2019-01-02T14:40:44.6596267Z",
        "relatedFileInfo": null
}
```
