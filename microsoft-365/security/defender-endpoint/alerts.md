---
title: 알림 표시 API
description: 끝점용 Microsoft Defender의 경고 리소스 유형의 메서드 및 속성에 대해 자세히 알아보습니다.
keywords: api, 그래프 api, 지원되는 api, get, alerts, recent
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
ms.openlocfilehash: 5d7fe37cfb4dc923bd7ddc73db9ff8443bca0a0a
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59187595"
---
# <a name="alert-resource-type"></a>경고 리소스 유형

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/?linkid=2154037)

- 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="methods"></a>메서드

<br>

****

|방법|반환 형식|설명|
|---|---|---|
|[알림 표시](get-alert-info-by-id.md)|[경고](alerts.md)|단일 경고 [개체를](alerts.md) 얻습니다.|
|[경고 목록](get-alerts.md)|[경고](alerts.md) 컬렉션|경고 [컬렉션을 나열합니다.](alerts.md)|
|[업데이트 경고](update-alert.md)|[경고](alerts.md)|특정 경고를 [업데이트합니다.](alerts.md)|
|[일괄 업데이트 경고](batch-update-alerts.md)||경고 일괄 [업데이트](alerts.md).|
|[경고 만들기](create-alert-by-reference.md)|[경고](alerts.md)|고급 헌팅에서 얻은 이벤트 데이터를 기반으로 [경고를 생성합니다.](run-advanced-query-api.md)|
|[관련 도메인 목록](get-alert-related-domain-info.md)|도메인 컬렉션|경고와 연결된 URL을 나열합니다.|
|[관련 파일 목록](get-alert-related-files-info.md)|[파일](files.md) 모음|경고와 [](files.md) 연결된 파일 엔터티를 [나열합니다.](alerts.md)|
|[관련 IPS 목록](get-alert-related-ip-info.md)|IP 컬렉션|경고와 연결된 IPS를 나열합니다.|
|[관련 컴퓨터 얻기](get-alert-related-machine-info.md)|[컴퓨터](machine.md)|[경고와](machine.md) 연결된 [컴퓨터입니다.](alerts.md)|
|[관련 사용자 얻기](get-alert-related-user-info.md)|[사용자](user.md)|[경고와](user.md) 연결된 [사용자입니다.](alerts.md)|
|

## <a name="properties"></a>속성

<br>

****

|속성|유형|설명|
|---|---|---|
|id|String|경고 ID입니다.|
|제목|문자열|경고 제목.|
|설명|String|경고 설명.|
|alertCreationTime|Nullable DateTimeOffset|경고가 만들어진 날짜 및 시간(UTC)입니다.|
|lastEventTime|Nullable DateTimeOffset|동일한 장치에서 경고를 트리거한 이벤트의 마지막 발생입니다.|
|firstEventTime|Nullable DateTimeOffset|해당 디바이스에서 경고를 트리거한 이벤트의 첫 번째 발생입니다.|
|lastUpdateTime|Nullable DateTimeOffset|경고가 마지막으로 업데이트된 날짜 및 시간(UTC)입니다.|
|resolvedTime|Nullable DateTimeOffset|경고 상태가 '해결'으로 변경된 날짜 및 시간입니다.|
|incidentId|Nullable Long|경고의 [인시던트](view-incidents-queue.md) ID입니다.|
|investigationId|Nullable Long|[경고와](automated-investigations.md) 관련된 조사 ID입니다.|
|investigationState|Nullable Enum|조사의 현재 [상태입니다.](automated-investigations.md) 가능한 값은 '알 수 없음', 'Terminated', 'SuccessfullyRemediated', 'Benign', 'Failed', 'PartiallyRemediated', 'Running', 'PendingApproval', 'PendingResource', 'PartiallyInvestigated', 'TerminatedByUser', 'TerminatedBySystem', 'Queued', 'InnerFailure', 'PreexistingAlert', 'UnsupportedOs', 'UnsupportedAlertType', 'SuppressedAlert'.|
|assignedTo|String|경고의 소유자입니다.|
|rbacGroupName|String|RBAC 장치 그룹 이름입니다.|
|mitreTechniques|String|Mitre Enterprise 기술 ID입니다.|
|relatedUser|String|특정 경고와 관련된 사용자 세부 정보입니다.|
|심각도|Enum|경고의 심각도입니다. 가능한 값은 'UnSpecified', 'Informational', 'Low', 'Medium' 및 'High'입니다.|
|status|Enum|경고의 현재 상태를 지정합니다. 가능한 값은 '알 수 없음', '신규', 'InProgress' 및 'Resolved'입니다.|
|classification|Nullable Enum|경고 사양입니다. 가능한 값은 '알 수 없음', 'FalsePositive', 'TruePositive'입니다.|
|determination|Nullable Enum|경고 결정 가능한 값은 'NotAvailable', 'Apt', 'Malware', 'SecurityPersonnel', 'SecurityTesting', 'UnwantedSoftware', 'Other'입니다.|
|category|문자열|경고 범주입니다.|
|detectionSource|문자열|검색 원본.|
|threatFamilyName|문자열|위협 패밀리.|
|threatName|String|위협 이름입니다.|
|machineId|문자열|경고와 [연결된](machine.md) 컴퓨터 엔터티의 ID입니다.|
|computerDnsName|String|[컴퓨터의](machine.md) 정식 이름입니다.|
|aadTenantId|String|Azure Active Directory ID입니다.|
|detectorId|String|경고를 트리거한 감지기 ID입니다.|
|설명|경고 설명 목록|Alert Comment 개체에는 주석 문자열, createdBy 문자열 및 createTime 날짜 시간이 포함되어 있습니다.|
|증거|경고 증거 목록|경고와 관련된 증거입니다. 아래 예제를 참조하세요.|
|

### <a name="response-example-for-getting-single-alert"></a>단일 경고를 표시하는 응답 예:

```http
GET https://api.securitycenter.microsoft.com/api/alerts/da637472900382838869_1364969609
```

```json
{
    "id": "da637472900382838869_1364969609",
    "incidentId": 1126093,
    "investigationId": null,
    "assignedTo": null,
    "severity": "Low",
    "status": "New",
    "classification": null,
    "determination": null,
    "investigationState": "Queued",
    "detectionSource": "WindowsDefenderAtp",
    "detectorId": "17e10bbc-3a68-474a-8aad-faef14d43952",
    "category": "Execution",
    "threatFamilyName": null,
    "title": "Low-reputation arbitrary code executed by signed executable",
    "description": "Binaries signed by Microsoft can be used to run low-reputation arbitrary code. This technique hides the execution of malicious code within a trusted process. As a result, the trusted process might exhibit suspicious behaviors, such as opening a listening port or connecting to a command-and-control (C&C) server.",
    "alertCreationTime": "2021-01-26T20:33:57.7220239Z",
    "firstEventTime": "2021-01-26T20:31:32.9562661Z",
    "lastEventTime": "2021-01-26T20:31:33.0577322Z",
    "lastUpdateTime": "2021-01-26T20:33:59.2Z",
    "resolvedTime": null,
    "machineId": "111e6dd8c833c8a052ea231ec1b19adaf497b625",
    "computerDnsName": "temp123.middleeast.corp.microsoft.com",
    "rbacGroupName": "A",
    "aadTenantId": "a839b112-1253-6432-9bf6-94542403f21c",
    "threatName": null,
    "mitreTechniques": [
        "T1064",
        "T1085",
        "T1220"
    ],
    "relatedUser": {
        "userName": "temp123",
        "domainName": "DOMAIN"
    },
    "comments": [
        {
            "comment": "test comment for docs",
            "createdBy": "secop123@contoso.com",
            "createdTime": "2021-01-26T01:00:37.8404534Z"
        }
    ],
    "evidence": [
        {
            "entityType": "User",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": null,
            "sha256": null,
            "fileName": null,
            "filePath": null,
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": "name",
            "domainName": "DOMAIN",
            "userSid": "S-1-5-21-11111607-1111760036-109187956-75141",
            "aadUserId": "11118379-2a59-1111-ac3c-a51eb4a3c627",
            "userPrincipalName": "temp123@microsoft.com",
            "detectionStatus": null
        },
        {
            "entityType": "Process",
            "evidenceCreationTime": "2021-01-26T20:33:58.6133333Z",
            "sha1": "ff836cfb1af40252bd2a2ea843032e99a5b262ed",
            "sha256": "a4752c71d81afd3d5865d24ddb11a6b0c615062fcc448d24050c2172d2cbccd6",
            "fileName": "rundll32.exe",
            "filePath": "C:\\Windows\\SysWOW64",
            "processId": 3276,
            "processCommandLine": "rundll32.exe  c:\\temp\\suspicious.dll,RepeatAfterMe",
            "processCreationTime": "2021-01-26T20:31:32.9581596Z",
            "parentProcessId": 8420,
            "parentProcessCreationTime": "2021-01-26T20:31:32.9004163Z",
            "parentProcessFileName": "rundll32.exe",
            "parentProcessFilePath": "C:\\Windows\\System32",
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        },
        {
            "entityType": "File",
            "evidenceCreationTime": "2021-01-26T20:33:58.42Z",
            "sha1": "8563f95b2f8a284fc99da44500cd51a77c1ff36c",
            "sha256": "dc0ade0c95d6db98882bc8fa6707e64353cd6f7767ff48d6a81a6c2aef21c608",
            "fileName": "suspicious.dll",
            "filePath": "c:\\temp",
            "processId": null,
            "processCommandLine": null,
            "processCreationTime": null,
            "parentProcessId": null,
            "parentProcessCreationTime": null,
            "parentProcessFileName": null,
            "parentProcessFilePath": null,
            "ipAddress": null,
            "url": null,
            "registryKey": null,
            "registryHive": null,
            "registryValueType": null,
            "registryValue": null,
            "accountName": null,
            "domainName": null,
            "userSid": null,
            "aadUserId": null,
            "userPrincipalName": null,
            "detectionStatus": "Detected"
        }
    ]
}
```
