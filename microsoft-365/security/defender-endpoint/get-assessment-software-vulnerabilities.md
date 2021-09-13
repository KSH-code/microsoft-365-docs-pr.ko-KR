---
title: 장치당 소프트웨어 취약점 평가 내보내기
description: API 응답은 장치당 있으며 노출된 장치에 설치된 취약한 소프트웨어와 이러한 소프트웨어 제품의 알려진 취약점을 포함 합니다. 이 표에는 운영 체제 정보, CVE ID 및 취약성 심각도 정보가 포함되어 있습니다.
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
ms.openlocfilehash: c9964ce7abdae004b33fb7317740b30b46b72d95
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185796"
---
# <a name="export-software-vulnerabilities-assessment-per-device"></a>장치당 소프트웨어 취약점 평가 내보내기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

장치 기준에 따라 알려진 모든 소프트웨어 취약성 및 모든 장치에 대한 세부 정보를 반환합니다.

다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다. 데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.

1. [소프트웨어 취약성 평가 **JSON 응답 내보내기**](#1-export-software-vulnerabilities-assessment-json-response)  API는 Json 응답으로 조직의 모든 데이터를 끌어 습니다. 이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.

2. [파일을 통해 소프트웨어 **취약성 평가 내보내기**](#2-export-software-vulnerabilities-assessment-via-files) 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 100 K 장치가 넘는 대규모 조직에서는 Via-files를 권장합니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.
   - API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.
   - 다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.

3. [델타 내보내기 소프트웨어 취약성 평가 **JSON 응답**](#3-delta-export-software-vulnerabilities-assessment-json-response)  DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId 및 EventTimestamp의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.
API는 Json 응답으로 조직의 데이터를 끌어 습니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.

   장치로 조직의 소프트웨어 취약점 평가에 대한 전체 스냅숏을 얻는 데 사용되는 전체 "소프트웨어 취약점 평가(JSON 응답)"와 달리 델타 내보내기 API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다. 매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다. 델타 내보내기 JSON 응답 API 호출을 사용하여 "고정된 취약성 수"과 같은 다양한 KPI를 계산할 수도 있습니다. 또는 "조직에 추가된 새 취약성의 수가 몇 개인가요?"

   소프트웨어 취약성에 대한 델타 내보내기 JSON 응답 API 호출은 대상 날짜 범위에 대한 데이터만 반환하기 때문에 전체 _내보내기로 간주되지 않습니다._

_Json_ 응답 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터가 포함되지 않습니다.  기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.

> [!NOTE]
> 다른 설명이 없는 한 나열된 **** 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 **** **_참조)입니다._**

## <a name="1-export-software-vulnerabilities-assessment-json-response"></a>1. 소프트웨어 취약점 평가 내보내기(JSON 응답)

### <a name="11-api-method-description"></a>1.1 API 메서드 설명

이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.

#### <a name="111-limitations"></a>1.1.1 제한 사항

- 최대 페이지 크기는 200,000개입니다.
- 이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.

### <a name="12-permissions"></a>1.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Vulnerability.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Vulnerability.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesByMachine
```

### <a name="14-parameters"></a>1.4 매개 변수

- pageSize(기본값 = 50,000): 응답 결과 수입니다.
- $top: 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.

### <a name="15-properties"></a>1.5 속성

> [!NOTE]
>
> - 각 레코드는 약 1 KB의 데이터입니다. 올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.
> - 응답에 일부 추가 열이 반환될 수 있습니다. 이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.
> - 다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다. 이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
CveId|문자열|CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.|CVE-2020-15992
CvssScore|문자열|CVE의 CVSS 점수입니다.|6.2
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
장치 이름|문자열|장치의 FQDN(FQDN)입니다.|johnlaptop.europe.contoso.com
DiskPaths|배열 \[ 문자열\]|제품이 장치에 설치되어 있는 디스크 증거입니다.|[ "C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe" ]
ExploitabilityLevel|문자열|이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)|ExploitIsInKit
FirstSeenTimestamp|문자열|이 제품의 CVE가 디바이스에 처음 표시됩니다.|2020-11-03 10:13:34.8476880
Id|문자열|레코드의 고유 식별자입니다.|123ABG55_573AG&mnp!
LastSeenTimestamp|문자열|디바이스에서 CVE를 마지막으로 본 시간입니다.|2020-11-03 10:13:34.8476880
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이 속성은 Windows 10 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 Windows 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.|Windows 10
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.|서버
RecommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.|va-_-microsoft-_-silverlight
RecommendedSecurityUpdate(선택 사항)|문자열|소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.|2020년 4월 보안 업데이트
RecommendedSecurityUpdateId(선택 사항)|문자열|해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자|4550961
RegistryPaths|배열 \[ 문자열\]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\MicrosoftSilverlight" ]
SoftwareName|문자열|소프트웨어 제품의 이름입니다.|chrome
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.|google
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.|81.0.4044.138
VulnerabilitySeverityLevel|문자열|CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.|보통
|

### <a name="16-examples"></a>1.6 예제

#### <a name="161-request-example"></a>1.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pageSize=5
```

#### <a name="162-response-example"></a>1.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.AssetVulnerability)",
    "value": [
        {
            "id": "00044f612345baf759462dbe6db733b6a9c59ab4_edge_10.0.17763.1637__",
            "deviceId": "00044f612345daf756462bde6bd733b9a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d089e79bdfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "edge",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-edge"
        },
        {
            "id": "00044f912345baf756462bde6db733b9a9c56ad4_.net_framework_4.0.0.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eeb80b086e79bdfa178eabfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-.net_framework"
        },
        {
            "id": "00044f912345baf756462dbe6db733d6a9c59ab4_system_center_2012_endpoint_protection_4.10.209.0__",
            "deviceId": "00044f912345daf756462bde6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eed224b2be2f5ea3142726e63f16a.DomainPII_21eed80b089e79bdfa178eadfa25e8be6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-system_center_2012_endpoint_protection"
        },
        {
            "id": "00044f612345bdaf759462dbe6bd733b6a9c59ab4_onedrive_20.245.1206.2__",
            "deviceId": "00044f91234daf759492dbe6bd733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_189663d45612eed224b2be2f5ea3142729e63f16a.DomainPII_21eed80b086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.245.1206.2",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2944539346-1310925172-2349113062-1001\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-30 13:18:33",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive"
        },
        {
            "id": "00044f912345daf759462bde6db733b6a9c56ab4_windows_10_10.0.17763.1637__",
            "deviceId": "00044f912345daf756462dbe6db733d6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18663b45912eeb224d2be2f5ea3142729e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8de6acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.17763.1637",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [],
            "lastSeenTimestamp": "2020-12-30 14:17:26",
            "firstSeenTimestamp": "2020-12-30 11:07:15",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-windows_10"
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilitiesByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-vulnerabilities-assessment-via-files"></a>2. 파일로 소프트웨어 취약점 평가 내보내기

### <a name="21-api-method-description"></a>2.1 API 메서드 설명

이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CVEID의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.

#### <a name="212-limitations"></a>2.1.2 제한 사항

이 API의 속도 제한은 분당 5통, 시간당 20통입니다.

### <a name="22-permissions"></a>2.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API(끝점 API용 Microsoft Defender](apis-intro.md)사용)를 참조합니다.

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Vulnerability.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Vulnerability.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareVulnerabilitiesExport
```

### <a name="24-parameters"></a>2.4 매개 변수

- sasValidHours: 다운로드 URL이 유효한 시간(최대 24시간)입니다.

### <a name="25-properties"></a>2.5 속성

> [!NOTE]
>
> - 파일은 여러 & Json 형식의 gzip 압축 파일 형식입니다.
> - 다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.
> - 데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.
>
> - 각 레코드는 약 1KB의 데이터입니다. 올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.
> - 응답에 일부 추가 열이 반환될 수 있습니다. 이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.|["https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|문자열|내보내기 생성 시간입니다.|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 예제

#### <a name="261-request-example"></a>2.6.1 요청 예제

```http
GET https://api-us.securitycenter.contoso.com/api/machines/SoftwareVulnerabilitiesExport
```

#### <a name="262-response-example"></a>2.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/VaExport/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-bcc26c4f-e531-48db-9892-c93ac5d72d5c.c002.json.gz?sv=2019-12-12&st=2021-01-11T11%3A35%3A13Z&se=2021-01-11T14%3A35%3A13Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="3-delta-export-software-vulnerabilities-assessment-json-response"></a>3. 델타 수출 소프트웨어 취약점 평가(JSON 응답)

### <a name="31-api-method-description"></a>3.1 API 메서드 설명

DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. API는 Json 응답으로 조직의 데이터를 끌어 습니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다. 전체 소프트웨어 취약점 평가(JSON 응답)(장치로 조직에 대한 소프트웨어 취약점 평가의 전체 스냅숏을 얻는 데 사용)와 달리 델타 내보내기 JSON 응답 API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다. 매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다. 델타 내보내기 JSON 응답 API 호출을 사용하여 "고정된 취약성 수"과 같은 다양한 KPI를 계산할 수도 있습니다. 또는 "조직에 추가된 새 취약성의 수가 몇 개인가요?"

> [!NOTE]
> 적어도 일주일에 한 번씩 장치 API 호출에 의해 전체 내보내기 소프트웨어 취약성 평가를 사용하는 것이 좋습니다. 이러한 추가 내보내기 소프트웨어 취약성은 장치(델타) API 호출에 따라 변경됩니다. 다른 평가 JSON 응답 API와 달리 "델타 내보내기"는 전체 내보내기되지 않습니다. 델타 내보내기에는 선택한 날짜와 현재 날짜 사이에 변경된 내용만 포함됩니다("델타" API 호출).

#### <a name="311-limitations"></a>3.1.1 제한 사항

- 최대 페이지 크기는 200,000개입니다.
- sinceTime 매개 변수의 최대 길이는 14일입니다.
- 이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.

### <a name="32-permissions"></a>3.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Vulnerability.Read.All|'위협 및 취약성 관리 취약성 정보 읽기'
위임(직장 또는 학교 계정)|Vulnerability.Read|'위협 및 취약성 관리 취약성 정보 읽기'

### <a name="33-url"></a>3.3 URL

```http
GET /api/machines/SoftwareVulnerabilityChangesByMachine
```

### <a name="34-parameters"></a>3.4 매개 변수

- sinceTime(필수): 선택한 시간과 현재 사이의 데이터입니다.
- pageSize(기본값 = 50,000): 응답의 결과 수입니다.
- $top: 반환할 결과 수입니다(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.

### <a name="35-properties"></a>3.5 속성

반환된 각 레코드에는 장치 API에 대한 전체 내보내기 소프트웨어 취약성 평가의 모든 데이터와 _**EventTimestamp**_ 및 Status의 두 개의 추가 필드가 _**포함되어 있습니다.**_

> [!NOTE]
>
> - 응답에 일부 추가 열이 반환될 수 있습니다. 이러한 열은 임시로 제거될 수 있으므로 문서화한 열만 사용하시기 바랍니다.
> - 다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다. 이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
CveId |문자열|CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.|CVE-2020-15992  
CvssScore|문자열|CVE의 CVSS 점수입니다.|6.2  
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1  
장치 이름|문자열|장치의 FQDN(FQDN)입니다.|johnlaptop.europe.contoso.com  
DiskPaths|Array[string]|제품이 장치에 설치되어 있는 디스크 증거입니다.|["C:\Program Files (x86)\Microsoft\Silverlight\Application\silverlight.exe"]  
EventTimestamp|String|이 델타 이벤트를 찾은 시간입니다.|2021-01-11T11:06:08.291Z
ExploitabilityLevel|문자열|이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)|ExploitIsInKit  
FirstSeenTimestamp|문자열|이 제품의 CVE가 디바이스에 처음 표시됩니다.|2020-11-03 10:13:34.8476880  
Id|문자열|레코드의 고유 식별자입니다.|123ABG55_573AG&mnp!  
LastSeenTimestamp|문자열|디바이스에서 CVE를 마지막으로 본 시간입니다.|2020-11-03 10:13:34.8476880  
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.|Windows 10  
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.|서버  
RecommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.|va-microsoft--silverlight  
RecommendedSecurityUpdate |문자열|소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.|2020년 4월 보안 업데이트  
RecommendedSecurityUpdateId |문자열|해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자|4550961  
RegistryPaths |Array[string]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.|[ "HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\Windows\CurrentVersion\Uninstall\Google Chrome" ]  
SoftwareName|문자열|소프트웨어 제품의 이름입니다.|chrome  
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.|google  
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.|81.0.4044.138  
상태|문자열|**새로 추가**   (장치에 도입된 새로운 취약성의 경우)  (1) **수정되었습니다(이** 취약점이 장치에 더 이상 존재하지 않는 경우, 즉   수정된 것입니다). (2)  **업데이트되었습니다.**   (장치의 취약점이 변경된 경우). 가능한 변경 내용은 CVSS 점수, 악용 가능성 수준, 심각도 수준, DiskPaths, RegistryPaths, RecommendedSecurityUpdate입니다. |고정
VulnerabilitySeverityLevel|문자열|CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.|보통
|

#### <a name="clarifications"></a>설명

- 소프트웨어가 버전 1.0에서 버전 2.0으로 업데이트된 경우 두 버전이 모두 CVE-A에 노출되면 2개의 개별 이벤트를 받게 됩니다.
   1. 고정: 버전 1.0의 CVE-A가 수정되었습니다.
   1. 신규: 버전 2.0의 CVE-A가 추가되었습니다.

- 버전 1.0이 있는 소프트웨어에서 특정 시간(예: 1월 10일)에 특정 취약성(예: CVE-A)이 처음 발견된 경우 며칠 후에 동일한 CVE-A에 노출된 버전 2.0으로 소프트웨어가 업데이트된 경우 다음 두 개의 분리된 이벤트를 받게 됩니다.
   1. 고정: CVE-X, FirstSeenTimestamp 1월 10일 버전 1,0.
   1. 신규: CVE-X, FirstSeenTimestamp 1월 10일 버전 2.0.

### <a name="36-examples"></a>3.6 예제

#### <a name="361-request-example"></a>3.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareVulnerabilityChangesByMachine?pageSize=5&sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="362-response-example"></a>3.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(microsoft.windowsDefenderATP.api.DeltaAssetVulnerability)",
    "value": [
        {
            "id": "008198251234544f7dfa715e278d4cec0c16c171_chrome_87.0.4280.88__",
            "deviceId": "008198251234544f7dfa715e278b4cec0c19c171",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_1c8fee370690ca24b6a0d3f34d193b0424943a8b8.DomainPII_0dc1aee0fa366d175e514bd91a9e7a5b2b07ee8e.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "87.0.4280.88",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Google Chrome"
            ],
            "lastSeenTimestamp": "2021-01-04 00:29:42",
            "firstSeenTimestamp": "2020-11-06 03:12:44",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "00e59c61234533860738ecf488eec8abf296e41e_onedrive_20.64.329.3__",
            "deviceId": "00e56c91234533860738ecf488eec8abf296e41e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_82c13a8ad8cf3dbaf7bf34fada9fa3aebc124116.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "onedrive",
            "softwareVersion": "20.64.329.3",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_USERS\\S-1-5-21-2127521184-1604012920-1887927527-24918864\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\OneDriveSetup.exe"
            ],
            "lastSeenTimestamp": "2020-12-11 19:49:48",
            "firstSeenTimestamp": "2020-12-07 18:25:47",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-onedrive",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "01aa8c73095bb12345918663f3f94ce322107d24_firefox_83.0.0.0_CVE-2020-26971_",
            "deviceId": "01aa8c73065bb12345918693f3f94ce322107d24",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_42684eb981bea2d670027e7ad2caafd3f2b381a3.DomainPII_21eed80b086e76dbfa178eabfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "mozilla",
            "softwareName": "firefox",
            "softwareVersion": "83.0.0.0",
            "cveId": "CVE-2020-26971",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "193220",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Mozilla Firefox\\firefox.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\WOW6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Mozilla Firefox 83.0 (x86 en-US)"
            ],
            "lastSeenTimestamp": "2021-01-05 17:04:30",
            "firstSeenTimestamp": "2020-05-06 12:42:19",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-mozilla-_-firefox",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "026f0fcb12345fbd2decd1a339702131422d362e_project_16.0.13701.20000__",
            "deviceId": "029f0fcb13245fbd2decd1a336702131422d392e",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_a5706750acba75f15d69cd17f4a7fcd268d6422c.DomainPII_f290e982685f7e8eee168b4332e0ae5d2a069cd6.corp.contoso.com",
            "osPlatform": "Windows10",
            "osVersion": "10.0.19042.685",
            "osArchitecture": "x64",
            "softwareVendor": "microsoft",
            "softwareName": "project",
            "softwareVersion": "16.0.13701.20000",
            "cveId": null,
            "vulnerabilitySeverityLevel": null,
            "recommendedSecurityUpdate": null,
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\ProjectProRetail - en-us"
            ],
            "lastSeenTimestamp": "2021-01-03 23:38:03",
            "firstSeenTimestamp": "2019-08-01 22:56:12",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-microsoft-_-project",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        },
        {
            "id": "038df381234510b357ac19d0113ef622e4e212b3_chrome_81.0.4044.138_CVE-2020-16011_",
            "deviceId": "038df381234510d357ac19b0113ef922e4e212b3",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_365f5c0bb7202c163937dad3d017969b2d760eb4.DomainPII_29596a43a2ef2bbfa00f6a16c0cb1d108bc63e32.DomainPII_3c5fefd2e6fda2f36257359404f6c1092aa6d4b8.net",
            "osPlatform": "Windows10",
            "osVersion": "10.0.18363.1256",
            "osArchitecture": "x64",
            "softwareVendor": "google",
            "softwareName": "chrome",
            "softwareVersion": "81.0.4044.138",
            "cveId": "CVE-2020-16011",
            "vulnerabilitySeverityLevel": "High",
            "recommendedSecurityUpdate": "ADV 200002",
            "recommendedSecurityUpdateId": null,
            "recommendedSecurityUpdateUrl": null,
            "diskPaths": [
                "C:\\Program Files (x86)\\Google\\Chrome\\Application\\chrome.exe"
            ],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{C4EBFDFD-0C55-3E5F-A919-E3C54949024A}"
            ],
            "lastSeenTimestamp": "2020-12-10 22:45:41",
            "firstSeenTimestamp": "2020-07-26 02:13:43",
            "exploitabilityLevel": "NoExploit",
            "recommendationReference": "va-_-google-_-chrome",
            "status": "Fixed",
            "eventTimestamp": "2021-01-11T11:06:08.291Z"
        }
    ],
    "@odata.nextLink": "https://wpatdadi-eus-stg.cloudapp.net/api/machines/SoftwareVulnerabilitiesTimeline?sincetime=2021-01-11&pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0xMS8xMTAxLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="see-also"></a>참고 항목

- [장치당 평가 방법 및 속성 내보내기](get-assessment-methods-properties.md)
- [장치당 보안 구성 평가 내보내기](get-assessment-secure-config.md)
- [장치당 소프트웨어 인벤토리 평가 내보내기](get-assessment-software-inventory.md)

기타 관련

- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
