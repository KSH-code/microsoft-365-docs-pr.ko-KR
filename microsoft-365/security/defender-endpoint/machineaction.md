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
ms.openlocfilehash: da3722294957593fc9cb89abfaec13e45106eefc
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/24/2021
ms.locfileid: "51187388"
---
# <a name="machineaction-resource-type"></a>MachineAction 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 끝점용 Microsoft Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


- 자세한 내용은 응답 [작업을 참조하세요.](respond-machine-alerts.md) 

| 메서드                                                            | 반환 형식                        | 설명                                                 |
|:------------------------------------------------------------------|:-----------------------------------|:------------------------------------------------------------|
| [MachineActions 목록](get-machineactions-collection.md)           | [컴퓨터 작업](machineaction.md) | 컴퓨터 [작업 엔터티를](machineaction.md) 나열합니다.           |
| [MachineAction 사용](get-machineaction-object.md)                  | [컴퓨터 작업](machineaction.md) | 단일 컴퓨터 작업 [엔터티를](machineaction.md) 얻습니다.     |
| [조사 패키지 수집](collect-investigation-package.md) | [컴퓨터 작업](machineaction.md) | 컴퓨터 에서 조사 패키지를 [수집합니다.](machine.md) |
| [조사 패키지 SAS URI를 얻습니다.](get-package-sas-uri.md)       | [컴퓨터 작업](machineaction.md) | 조사 패키지 다운로드를 위한 URI를 다운로드합니다.          |
| [컴퓨터 격리](isolate-machine.md)                             | [컴퓨터 작업](machineaction.md) | 네트워크에서 [컴퓨터](machine.md) 격리.                 |
| [컴퓨터의 고리 해제](unisolate-machine.md)            | [컴퓨터 작업](machineaction.md) | [컴퓨터의](machine.md) 고리에서 해제합니다.               |
| [앱 실행 제한](restrict-code-execution.md)              | [컴퓨터 작업](machineaction.md) | 응용 프로그램 실행을 제한합니다.                             |
| [앱 제한 제거](unrestrict-code-execution.md)            | [컴퓨터 작업](machineaction.md) | 응용 프로그램 실행 제한을 제거합니다.                   |
| [바이러스 백신 검사 실행](run-av-scan.md)                              | [컴퓨터 작업](machineaction.md) | 해당되는 경우 Windows Defender 사용하여 AV 스캔을 실행합니다.    |
| [컴퓨터 오프보드](offboard-machine-api.md)                       | [컴퓨터 작업](machineaction.md) | [끝점용](machine.md) Microsoft Defender에서 컴퓨터 오프보드. |
| [파일 중지 및 검지](stop-and-quarantine-file.md)           | [컴퓨터 작업](machineaction.md) | 컴퓨터의 파일 실행을 중지하고 삭제합니다.        |

<br>

## <a name="properties"></a>속성

| 속성            | 유형           | 설명                                                                                                                                                                                                    |
|:--------------------|:---------------|:---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| ID                  | Guid           | [Machine Action 엔터티의 ID입니다.](machineaction.md)                                                                                                                                                     |
| type                | Enum           | 작업의 유형입니다. 가능한 값은 "RunAntiVirusScan", "Offboard", "CollectInvestigationPackage", "Isolate", "Unisolate", "StopAndQuarantineFile", "RestrictCodeExecution" 및 "UnrestrictCodeExecution"입니다. |
| scope               | 문자열         | 작업의 범위입니다. 바이러스 백신 검사의 경우 "전체" 또는 "선택적" 및 "빠른" 또는 "전체"입니다.                                                                                                   |
| requestor           | 문자열         | 작업을 실행한 사람의 ID입니다.                                                                                                                                                               |
| requestorComment    | 문자열         | 작업을 실행할 때 작성된 설명입니다.                                                                                                                                                              |
| status              | Enum           | 명령의 현재 상태입니다. 가능한 값은 "보류 중", "InProgress", "Succeeded", "Failed", "TimeOut" 및 "Canceled"입니다.                                                                                 |
| machineId           | 문자열         | 작업이 실행된 컴퓨터의 ID입니다. [](machine.md)                                                                                                                                              |
| machineId           | 문자열         | 작업이 [실행된](machine.md) 컴퓨터의 이름입니다.                                                                                                                                            |
| creationDateTimeUtc | DateTimeOffset | 작업을 만든 날짜 및 시간입니다.                                                                                                                                                                 |
| lastUpdateTimeUtc   | DateTimeOffset | 작업 상태가 업데이트된 마지막 날짜 및 시간입니다.                                                                                                                                                     |
| relatedFileInfo     | 클래스          | 두 속성이 들어 있습니다. string , Enum 값으로 ```fileIdentifier``` ```fileIdentifierType``` "Sha1", "Sha256" 및 "Md5"를 지정합니다.                                                                         |


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
