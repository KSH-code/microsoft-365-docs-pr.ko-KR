---
title: ID로 하나의 재구성 활동 얻기
description: 지정한 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, ID로 수정,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9d26c3db7f358bf13ed59e50617bf5f1a606e5ed
ms.sourcegitcommit: 3576c2fee77962b516236cb67dd3df847d61c527
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/28/2021
ms.locfileid: "53622931"
---
# <a name="get-one-remediation-activity-by-id"></a>ID로 하나의 재구성 활동 얻기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

지정한 수정 활동에 대한 정보를 반환합니다. 모든 재구성 활동 [](get-remediation-all-activities.md)"을(를) 반환하지만 지정된 수정 작업 중 하나에 대한 결과만 _반환합니다._

[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)

## <a name="list-a-specified-remediation-activity-for-id"></a>(id)에 대해 지정된 수정 활동 나열

**URL:** GET: /api/remediationTasks/ \{ id\}

## <a name="permissions"></a>사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|RemediationTask.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|RemediationTask.Read.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

## <a name="properties"></a>특성

속성(id)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
category|String|재구성 활동 범주(소프트웨어/보안 구성)|소프트웨어
completerEmail|String|누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.|null
completerId|String|누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.|null
completionMethod|String|재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.|자동
createdOn|DateTime|이 수정 활동이 만들어진 시간|2021-01-12T18:54:11.5499478Z
설명|String|이 수정 활동에 대한 설명|장치에 영향을 주는 알려진 취약점을 완화하기 위해 Microsoft Silverlight를 이후 버전으로 업데이트합니다.
dueOn|DateTime|이 수정 활동에 대한 작성자가 설정한 기한|2021-01-13T00:00:00Z
fixedDevices||고정된 장치 수|2
id|String|이 수정 활동의 ID|097d9735-5479-4899-b1b7-77398899df92
nameId|String|관련 제품 이름|Microsoft Silverlight
priority|String|이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)|높음
productId|String|관련 제품 ID|microsoft-_-silverlight
productivityImpactRemediationType|String|사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다. 이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.|AllExposedAssets
rbacGroupNames|String|관련 장치 그룹 이름|[ "Windows Servers", "Windows 10" ]
recommendedProgram|String|업그레이드할 권장 프로그램|null
recommendedVendor|String|업그레이드할 권장 공급업체|null
recommendedVersion|String|업데이트/업그레이드에 권장되는 버전|null
relatedComponent|String|이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)|Microsoft Microsoft Silverlight
requesterEmail|String|작성자 전자 메일 주소|globaladmin@UserName.contoso.com
requesterId|String|Creator 개체 ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|String|이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)|null
scid|String|관련 보안 권장 정보의 SCID|null
status|String|재구성 활동 상태(활성/완료)|활성
statusLastModifiedOn|DateTime|상태 필드가 업데이트된 날짜|2021-01-12T18:54:11.5499487Z
targetDevices|Long|이 수정을 적용할 수 있는 노출된 장치 수|43
title|String|이 수정 활동의 제목입니다.|Microsoft Silverlight
type|String|수정 유형|업데이트
vendorId|String|관련 공급업체 이름|Microsoft

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c
```

### <a name="response-example"></a>응답 예제

```json
{ 
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks/$entity", 
    "id": "03942ef5-aecb-4c6e-b555-d6a97013844c", 
    "title": "Update Microsoft Silverlight", 
    "createdOn": "2021-02-10T13:20:36.4718166Z", 
    "requesterId": "65548a1d-efo0-4a7a-8d19-1b967b5c36f4", 
    "requesterEmail": "user1@contoso.com", 
    "status": "Active", 
    "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z", 
    "description": "Update Silverlight to a later version to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.  ", 
    "relatedComponent": "Microsoft Silverlight", 
    "targetDevices": 18511, 
    "rbacGroupNames": [ 
        "UnassignedGroup", 
        "hhh" 
    ], 
    "fixedDevices": 2866, 
    "requesterNotes": "test", 
    "dueOn": "2021-02-11T00:00:00Z", 
    "category": "Software", 
    "productivityImpactRemediationType": null, 
    "priority": "Medium", 
    "completionMethod": null, 
    "completerId": null, 
    "completerEmail": null, 
    "scid": null, 
    "type": "Update", 
    "productId": "microsoft-_-silverlight", 
    "vendorId": "microsoft", 
    "nameId": "silverlight", 
    "recommendedVersion": null, 
    "recommendedVendor": null, 
    "recommendedProgram": null 
} 
```

## <a name="see-also"></a>참고 항목

- [수정 방법 및 속성](get-remediation-methods-properties.md)
- [모든 수정 작업 나열s](get-remediation-all-activities.md)
- [한 번의 수정 작업이 있는 노출된 장치 목록](get-remediation-exposed-devices-activities.md)
- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
