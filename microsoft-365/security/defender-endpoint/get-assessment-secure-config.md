---
title: 장치당 보안 구성 평가 내보내기
description: DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.
keywords: api, api, 내보내기 평가, 장치 평가당, 취약성 평가 보고서, 장치 취약점 평가, 장치 취약성 보고서, 보안 구성 평가, 보안 구성 보고서, 소프트웨어 취약점 평가, 소프트웨어 취약성 보고서, 컴퓨터의 취약점 보고서,
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 4d8010cafa9ea0195e4c77298bea2098eab5c594
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221524"
---
# <a name="export-secure-configuration-assessment-per-device"></a>장치당 보안 구성 평가 내보내기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

장치 기준에 따라 모든 구성 및 구성 상태를 반환합니다.

다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다. 데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.

- [보안 구성 평가 **JSON 응답 내보내기:**](#1-export-secure-configuration-assessment-json-response)API는 조직의 모든 데이터를 Json 응답으로 끌어 들입니다. 이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.

- 파일을 통해 보안 [구성 평가 ](#2-export-secure-configuration-assessment-via-files)내보내기: 이 API 솔루션을 사용하면 더 많은 양의 데이터를 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.

  - API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.

  - 다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.

_JSON_ 응답 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터가 포함되지 않습니다.  기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.

> [!NOTE]
> 다른 설명이 없는 한 나열된 **** 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 **** **_참조)입니다._**

## <a name="1-export-secure-configuration-assessment-json-response"></a>1. 보안 구성 평가 내보내기(JSON 응답)

### <a name="11-api-method-description"></a>1.1 API 메서드 설명

이 API 응답은 노출된 디바이스에 대한 보안 구성 평가를 포함하며 DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.

#### <a name="111-limitations"></a>1.1.1 제한 사항

- 최대 페이지 크기는 200,000개입니다.

- 이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.

### <a name="12-permissions"></a>1.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API](apis-intro.md) for details을 참조합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Vulnerability.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Vulnerability.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentByMachine
```

### <a name="14-parameters"></a>1.4 매개 변수

- pageSize \( default = 50,000 \) : 응답 결과 수입니다.
- \$top: 반환할 결과 \( 수가 \@ odata.nextLink를 반환하지 못하므로 모든 데이터를 끌어오지 \) 않습니다.

### <a name="15-properties"></a>1.5 속성

> [!NOTE]
>
> - 다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다. 이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.
> - 응답에 일부 추가 열이 반환될 수 있습니다. 이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
---|---|---|---
ConfigurationCategory|문자열|구성이 속해 있는 범주 또는 그룹(응용 프로그램, OS, 네트워크, 계정, 보안 제어)|보안 제어
ConfigurationId|문자열|특정 구성의 고유 식별자|scid-10000
ConfigurationImpact|문자열|구성의 등급이 전반적인 구성 점수에 미치는 영향(1-10)|9 
ConfigurationName|문자열|구성 이름을 표시합니다.|엔드포인트용 Microsoft Defender에 장치 온보딩
ConfigurationSubcategory|문자열|구성이 속한 하위 범주나 하위 그룹 대부분의 경우 이는 특정 기능이나 특징을 설명합니다.|장치 온보드
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
장치 이름|문자열|장치의 FQDN(FQDN)입니다.|johnlaptop.europe.contoso.com
IsApplicable|bool|구성 또는 정책을 적용할 수 있는지 여부를 나타냅니다.|true
IsCompliant|bool|구성 또는 정책이 올바르게 구성되어 있는지 여부|false
IsExpectedUserImpact|bool|구성을 적용할 경우 사용자에게 영향을 줄지 여부를 나타냅니다.|true
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.|Windows 10
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.|서버
RecommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.|sca-_-scid-20000
타임스탬프|문자열|장치에서 구성을 마지막으로 본 시간|2020-11-03 10:13:34.8476880
|

### <a name="16-examples"></a>1.6 예제

#### <a name="161-request-example"></a>1.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 응답 예제

```json
{
    "@odata.context": "api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetConfiguration)",
    "value": [
        {
            "deviceId": "00013ee62c6b12345b10214e1801b217b50ab455c293d",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_5d96860d69c73fdd06fc8d1679e1eb73eceb8330",
            "osPlatform": "Windows10",
            "osVersion": "NT kernel 6.x",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "0002a1be533813b9a8c6de739785365bce7910",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-20000",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Onboard Devices",
            "configurationImpact": 9,
            "isCompliant": false,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Onboard devices to Microsoft Defender for Endpoint",
            "recommendationReference": "sca-_-scid-20000"
        },
        {
            "deviceId": "0002a1de123456a8c06de736785395d4ce7610",
            "rbacGroupName": "hhh",
            "deviceName": null,
            "osPlatform": "Windows10",
            "osVersion": "10.0",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-10000",
            "configurationCategory": "Network",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Disable insecure administration protocol - Telnet",
            "recommendationReference": "sca-_-scid-10000"
        },
        {
            "deviceId": "00044f912345bdaf756492dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663d45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e76bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-39",
            "configurationCategory": "OS",
            "configurationSubcategory": "",
            "configurationImpact": 5,
            "isCompliant": true,
            "isApplicable": true,
            "isExpectedUserImpact": false,
            "configurationName": "Enable 'Domain member: Digitally sign secure channel data (when possible)'",
            "recommendationReference": "sca-_-scid-39"
        },
        {
            "deviceId": "00044f912345daf759462bde6bd733d6a9c56ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45612eeb224d2de2f5ea3142726e63f16a.DomainPII_21eed80d086e76dbfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "timestamp": "2021-01-11 09:47:58.854",
            "configurationId": "scid-6093",
            "configurationCategory": "Security controls",
            "configurationSubcategory": "Antivirus",
            "configurationImpact": 5,
            "isCompliant": false,
            "isApplicable": false,
            "isExpectedUserImpact": false,
            "configurationName": "Enable Microsoft Defender Antivirus real-time behavior monitoring for Linux",
            "recommendationReference": "sca-_-scid-6093"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-secure-configuration-assessment-via-files"></a>2. 파일로 보안 구성 평가 내보내기

### <a name="21-api-method-description"></a>2.1 API 메서드 설명

이 API 응답은 노출된 디바이스에 대한 보안 구성 평가를 포함하며 DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목을 반환합니다.

#### <a name="212-limitations"></a>2.1.2 제한 사항

이 API의 속도 제한은 분당 5통, 시간당 20통입니다.

### <a name="22-permissions"></a>2.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Vulnerability.Read.All|\'"위협 및 취약성 관리" 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Vulnerability.Read|\'"위협 및 취약성 관리" 취약성 정보 읽기\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SecureConfigurationsAssessmentExport
```

### <a name="parameters"></a>매개 변수

- sasValidHours: 다운로드 URL이 유효한 시간(최대 24시간)입니다.

### <a name="25-properties"></a>2.5 속성

> [!NOTE]
>
> - 파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.
> - 다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.
> - 데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
---|---|---|---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록|["Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|문자열|내보내기 생성 시간입니다.|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 예제

#### <a name="261-request-example"></a>2.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SecureConfigurationsAssessmentExport
```

#### <a name="262-response-example"></a>2.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#contoso.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/ScaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>참고 항목

- [장치당 평가 방법 및 속성 내보내기](get-assessment-methods-properties.md)
- [장치당 소프트웨어 인벤토리 평가 내보내기](get-assessment-software-inventory.md)
- [장치당 소프트웨어 취약점 평가 내보내기](get-assessment-software-vulnerabilities.md)

기타 관련

- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
