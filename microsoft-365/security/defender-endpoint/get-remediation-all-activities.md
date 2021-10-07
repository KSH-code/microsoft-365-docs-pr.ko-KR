---
title: 모든 수정 작업 나열s
description: 모든 수정 활동에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 모든 수정,
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-jweston
author: jweston-1
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 9f7e82d3ac4dce15f444f416e7dfb154188c093f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190524"
---
# <a name="list-all-remediation-activities"></a>모든 수정 작업 나열s

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

모든 수정 활동에 대한 정보를 반환합니다.

[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)

**URL:** GET: /api/remediationTasks
<br>[OData V4 쿼리를 지원합니다.](https://www.odata.org/documentation/)
<br>OData 지원 연산자:
<br>```$filter``` on:  ```createdon``` 및 ```status``` 속성.
<br>```$top``` 는 최대값 10,000입니다.
<br>```$skip```.
<br>[끝점용 Microsoft Defender를 사용하여 OData 쿼리의 예를 참조합니다.](exposed-apis-odata-samples.md)

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|RemediationTasks.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|RemediationTask.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

## <a name="properties"></a>속성

속성(id)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
category|String|재구성 활동 범주(소프트웨어/보안 구성)|소프트웨어
completerEmail|String|누군가가 수정 작업을 수동으로 완료한 경우 이 열에 전자 메일이 포함되어 있습니다.|null
completerId|String|누군가가 수정 작업을 수동으로 완료한 경우 이 열에는 해당 개체 ID가 포함되어 있습니다.|null
completionMethod|String|재구성 활동은 "자동으로"(모든 장치가 패치된 경우) 또는 "완료된 것으로 표시"를 선택한 사람이 "수동으로" 완료할 수 있습니다.|자동
createdOn|날짜/시간|이 수정 활동이 만들어진 시간|2021-01-12T18:54:11.5499478Z
설명|String|이 수정 활동에 대한 설명|장치에 영향을 주는 알려진 취약점을 완화하기 위해 Microsoft Silverlight를 이후 버전으로 업데이트합니다.
dueOn|날짜/시간|이 수정 활동에 대한 작성자가 설정한 기한|2021-01-13T00:00:00Z
fixedDevices|.|고정된 장치 수|2
id|String|이 수정 활동의 ID|097d9735-5479-4899-b1b7-77398899df92
nameId|String|관련 제품 이름|Microsoft Silverlight
priority|String|이 수정 활동의 작성자 집합 우선 순위(높음\중간\낮음)|높음
productId|String|관련 제품 ID|microsoft-_-silverlight
productivityImpactRemediationType|String|사용자 영향이 없는 장치에만 몇 가지 구성 변경을 요청할 수 있습니다. 이 값은 "노출된 모든 장치" 또는 "사용자 영향이 없는 장치만" 선택을 나타냅니다.|AllExposedAssets
rbacGroupNames|String|관련 장치 그룹 이름|[ "Windows Servers", "Windows 10" ]
recommendedProgram|String|업그레이드할 권장 프로그램|null
recommendedVendor|String|업그레이드할 권장 공급업체|null
recommendedVersion|String|업데이트/업그레이드에 권장되는 버전|null
relatedComponent|String|이 수정 작업의 관련 구성 요소(보안 권장에 대한 관련 구성 요소와 유사)|Microsoft Silverlight
requesterEmail|String|작성자 전자 메일 주소|globaladmin@UserName.contoso.com
requesterId|String|Creator 개체 ID|r647211f-2e16-43f2-a480-16ar3a2a796r
requesterNotes|String|이 수정 활동에 대해 작성자가 추가한 메모(무료 텍스트)|null
scid|String|관련 보안 권장 정보의 SCID|null
status|String|재구성 활동 상태(활성/완료)|활성
statusLastModifiedOn|날짜/시간|상태 필드가 업데이트된 날짜|2021-01-12T18:54:11.5499487Z
targetDevices|Long|이 수정을 적용할 수 있는 노출된 장치 수|43
title|String|이 수정 활동의 제목입니다.|Microsoft Silverlight 업데이트
type|String|수정 유형|업데이트
vendorId|String|관련 공급업체 이름|Microsoft

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/
```

### <a name="response-example"></a>응답 예제

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#RemediationTasks",
    "value": [
        {
            "id": "03942ef5-aewb-4w6e-b555-d6a97013844w",
            "title": "Update Microsoft Silverlight",
            "createdOn": "2021-02-10T13:20:36.4718166Z",
            "requesterId": "65548a1d-ef00-4a7a-8d19-1b967b5c36f4",
            "requesterEmail": "user1@contoso.com",
            "status": "Active",
            "statusLastModifiedOn": "2021-02-10T13:20:36.4719698Z",
            "description": "Update Silverlight to a later version  to mitigate 55 known vulnerabilities affecting your devices. Doing so can help lessen the security risk to your organization due to versions which have reached their end-of-support.",
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
    ]
}
```

## <a name="see-also"></a>참고 항목

- [수정 방법 및 속성](get-remediation-methods-properties.md)
- [ID로 수정 작업 1개 가져오기](get-remediation-one-activity.md)
- [한 번의 수정 작업이 있는 노출된 장치 목록](get-remediation-exposed-devices-activities.md)
- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
