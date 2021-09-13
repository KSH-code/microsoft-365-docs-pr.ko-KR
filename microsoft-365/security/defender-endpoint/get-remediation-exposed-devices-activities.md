---
title: 한 번의 수정 작업이 있는 노출된 장치 목록
description: 지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.
keywords: api, 수정, 수정 api, get, 수정 작업, 노출된 장치 수정
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
ms.openlocfilehash: 1ee64608e9ce6ce24dc40f1729303ef99b162cab
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59190992"
---
# <a name="list-exposed-devices-of-one-remediation-activity"></a>한 번의 수정 작업이 있는 노출된 장치 목록

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Prerelease information](../../includes/prerelease.md)]

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

## <a name="api-description"></a>API 설명

지정된 수정 작업에 대해 노출된 장치에 대한 정보를 반환합니다.

[재구성 활동에 대해 자세히 알아보시다.](tvm-remediation.md)

## <a name="list-exposed-devices-associated-with-a-remediation-task-id"></a>재구성 작업과 연결된 노출된 장치 나열(ID)

**URL:** GET: /api/remediationTasks/ \{ id \} /machineReferences

## <a name="permissions"></a>권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
:---|:---|:---
응용 프로그램|RemediationTasks.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|RemediationTask.Read.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

## <a name="properties-details"></a>속성 세부 정보

속성(id)|데이터 형식|설명|예제
:---|:---|:---|:---
id|문자열|장치 ID|w2957837fwda8w9ae7f023dba081059dw8d94503
computerDnsName|문자열|장치 이름|PC-SRV2012R2Foo.UserNameVldNet.local
osPlatform|String|장치 운영 체제|WindowsServer2012R2
rbacGroupName|문자열|이 장치가 연결된 장치 그룹의 이름입니다.|서버

## <a name="example"></a>예제

### <a name="request-example"></a>요청 예제

```http
GET https://api-luna.securitycenter.windows.com/api/remediationtasks/03942ef5-aecb-4c6e-b555-d6a97013844c/machinereferences
```

### <a name="response-example"></a>응답 예제

```json
{
    "@odata.context": "https://wpatdadi-luna-stg.cloudapp.net/api/$metadata#MachineReferences",
    "value": [
        {
            "id": "3cb5df6bb3640a2d37ad09fcd357b182d684fafc",
            "computerDnsName": "ComputerPII_2ea21b2d97c9df23c143ad9e3e454cb674232529.DomainPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3d9b1ca53e8f077199c7dcbfc9dbfa78f9bf1918",
            "computerDnsName": "ComputerPII_001d606fc149567c192747f48fae304b43c0ddba.DomainxPII_21eed80b086e79bdfa178eabfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3db8b27e6172951d7ea2e2d75945abec56feaf82",
            "computerDnsName": "ComputerPII_ce60cfbjj4b82a091deb5eae560332bba99a9bd7.DomainPII_0bc1aee0fa396d175e514bd61a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "WindowsServer2016",
            "rbacGroupName": "UnassignedGroup",

        },
        {
            "id": "3bad326dcda5b53fab47408cd4a7080f3f3cc8ab",
            "computerDnsName": "ComputerPII_b6b35960dd6539d1d1cef5ada02e235e7b357408.DomainPII_21eed80b089e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "WindowsServer2012R2",
            "rbacGroupName": "UnassignedGroup",

        }
]
}
```

## <a name="see-also"></a>참고 항목

- [수정 방법 및 속성](get-remediation-methods-properties.md)
- [ID로 수정 작업 1개 가져오기](get-remediation-one-activity.md)
- [모든 수정 작업 나열s](get-remediation-all-activities.md)
- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
