---
title: 장치당 소프트웨어 인벤토리 평가 내보내기
description: DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.
keywords: api, api, 내보내기 평가, 장치 평가당, 취약성 평가 보고서, 장치 취약점 평가, 장치 취약성 보고서, 보안 구성 평가, 보안 구성 보고서, 소프트웨어 취약점 평가, 소프트웨어 취약성 보고서, 컴퓨터의 취약점 보고서,
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 77d0bfb569837a508221d78d811c985153533ed7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60152229"
---
# <a name="export-software-inventory-assessment-per-device"></a>장치당 소프트웨어 인벤토리 평가 내보내기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다. 데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.

- [소프트웨어 인벤토리 평가 **JSON 응답 내보내기**](#1-export-software-inventory-assessment-json-response) API는 Json 응답으로 조직의 모든 데이터를 끌어 습니다. 이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.

- [파일을 통해 소프트웨어 인벤토리 **평가 내보내기**](#2-export-software-inventory-assessment-via-files)  이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.
  - API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.
  - 다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.

_Json_ 응답 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터가 포함되지 않습니다.  기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.

> [!NOTE]
> 다른 설명이 없는 한 나열된 **** 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 **** **_참조)입니다._**

## <a name="1-export-software-inventory-assessment-json-response"></a>1. 소프트웨어 인벤토리 평가 내보내기(JSON 응답)

### <a name="11-api-method-description"></a>1.1 API 메서드 설명

이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.

#### <a name="limitations"></a>제한 사항

- 최대 페이지 크기는 200,000개입니다.
- 이 API에 대한 속도 제한은 분당 30개 호출과 시간당 1,000개 호출입니다.

### <a name="12-permissions"></a>1.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Software.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Software.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

### <a name="13-url"></a>1.3 URL

```http
GET /api/machines/SoftwareInventoryByMachine
```

### <a name="14-parameters"></a>1.4 매개 변수

- pageSize(기본값 = 50,000): 응답 결과 수입니다.
- $top: 반환할 결과 수(@odata.nextLink를 반환하지 않습니다. 따라서 모든 데이터를 끌어오지 않습니다.

### <a name="15-properties"></a>1.5 속성

> [!NOTE]
>
> - 각 레코드는 약 0.5KB의 데이터입니다. 올바른 pageSize 매개 변수를 선택할 때 이 문제를 고려해야 합니다.
> - 다음 표에 정의된 속성은 속성 ID에 따라 사전순으로 나열됩니다. 이 API를 실행하면 결과 출력이 이 표에 나열된 순서대로 반환되지 않을 수도 있습니다.
> - 응답에 일부 추가 열이 반환될 수 있습니다. 이러한 열은 임시로 제거될 수 있습니다. 문서화한 열만 사용하시기 바랍니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.|9eaf3a8b5962e0e6b1af9ec756664a9b823df2d1
장치 이름|문자열|장치의 FQDN(FQDN)입니다.|johnlaptop.europe.contoso.com
DiskPaths|Array[string]|제품이 장치에 설치되어 있는 디스크 증거입니다.|[ "C: \\ Program Files (x86) \\ Microsoft \\ Silverlight \\ Application \\silverlight.exe" ]
EndOfSupportDate|문자열|이 소프트웨어에 대한 지원이 종료되는 날짜입니다.|2020-12-30
EndOfSupportStatus|문자열|지원 종료 상태입니다. None, EOS 버전, 예정된 EOS 버전, EOS 소프트웨어, 예정된 EOS 소프트웨어 등 가능한 값을 포함할 수 있습니다.|예정된 EOS
Id|문자열|레코드의 고유 식별자입니다.|123ABG55_573AG&mnp!
NumberOfWeaknesses|int|이 장치에서 이 소프트웨어의 약점 수|3 
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.|Windows 10
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.|서버
RegistryPaths|Array[string]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.|[ "HKEY_LOCAL_MACHINE \\ SOFTWARE \\ WOW6432Node \\ Microsoft Windows \\ \\ CurrentVersion \\ Uninstall \\ Microsoft Silverlight" ]
SoftwareFirstSeenTimestamp|문자열|디바이스에서 이 소프트웨어를 처음 볼 수 있습니다.|2019-04-07 02:06:47
SoftwareName|문자열|소프트웨어 제품의 이름입니다.|Silverlight
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.|microsoft
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.|81.0.4044.138
|

### <a name="16-examples"></a>1.6 예제

#### <a name="161-request-example"></a>1.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pageSize=5  &sinceTime=2021-05-19T18%3A35%3A49.924Z
```

#### <a name="162-response-example"></a>1.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#Collection(contoso.windowsDefenderATP.api.AssetSoftware)",
    "value": [
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "windows_10",
            "softwareVersion": "10.0.17763.1637",
            "numberOfWeaknesses": 58,
            "diskPaths": [],
            "registryPaths": [],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "Upcoming EOS Version",
            "endOfSupportDate": "2021-05-11T00:00:00+00:00"
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": ".net_framework",
            "softwareVersion": "4.0.0.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "SOFTWARE\\Microsoft\\NET Framework Setup\\NDP\\v4.0\\Client\\Install"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eed80d086e79bdfa178eadfa25e8de9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.7.214.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f68765ddaf71234bde6bd733d6a9c59ad4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2be2f5ea3142726e63f16a.DomainPII_21eeb80d086e79dbfa178aedfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "configuration_manager",
            "softwareVersion": "5.0.8634.1000",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\{B7D3A842-E826-4542-B39B-1D883264B279}"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        },
        {
            "deviceId": "00044f38765bbaf712342dbe6db733b6a9c59ab4",
            "rbacGroupName": "hhh",
            "deviceName": "ComputerPII_18993b45912eeb224b2de2f5ea3142726e63f16a.DomainPII_21eeb80d086e79bdfa178eadfa25e8be9acfa346.corp.contoso.com",
            "osPlatform": "Windows10",
            "softwareVendor": "microsoft",
            "softwareName": "system_center_2012_endpoint_protection",
            "softwareVersion": "4.10.209.0",
            "numberOfWeaknesses": 0,
            "diskPaths": [],
            "registryPaths": [
                "HKEY_LOCAL_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Uninstall\\Microsoft Security Client"
            ],
            "softwareFirstSeenTimestamp": "2020-12-30 11:07:15",
            "endOfSupportStatus": "None",
            "endOfSupportDate": null
        }
    ],
    "@odata.nextLink": "https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryByMachine?pagesize=5&$skiptoken=eyJFeHBvcnREZWZpbml0aW9uIjp7IlRpbWVQYXRoIjoiMjAyMS0wMS0yNS8wMjAwLyJ9LCJFeHBvcnRGaWxlSW5kZXgiOjAsIkxpbmVTdG9wcGVkQXQiOjV9"
}
```

## <a name="2-export-software-inventory-assessment-via-files"></a>2. 파일로 소프트웨어 인벤토리 평가 내보내기

### <a name="21-api-method-description"></a>2.1 API 메서드 설명

이 API 응답에는 장치당 설치된 소프트웨어의 모든 데이터가 포함되어 있습니다. DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다.

#### <a name="211-limitations"></a>2.1.1 제한 사항

이 API의 속도 제한은 분당 5통, 시간당 20통입니다.

### <a name="22-permissions"></a>2.2 사용 권한

이 API를 호출하려면 다음 권한 중 하나가 필요합니다. 사용 권한을 선택하는 방법을 포함하여 자세한 내용은 [Use Microsoft Defender for Endpoint API for details을 참조합니다.](apis-intro.md)

사용 권한 유형|사용 권한|사용 권한 표시 이름
---|---|---
응용 프로그램|Software.Read.All|\'위협 및 취약성 관리 취약성 정보 읽기\'
위임(직장 또는 학교 계정)|Software.Read|\'위협 및 취약성 관리 취약성 정보 읽기\'

### <a name="23-url"></a>2.3 URL

```http
GET /api/machines/SoftwareInventoryExport
```

### <a name="parameters"></a>매개 변수

- sasValidHours: 다운로드 URL이 유효한 시간(최대 24시간)

### <a name="25-properties"></a>2.5 속성

> [!NOTE]
>
> - 파일은 여러 줄 JSON & 압축된 파일입니다.
> - 다운로드 URL은 3시간 동안만 유효합니다. 그렇지 않으면 매개 변수를 사용할 수 있습니다.
> - 데이터의 최대 다운로드 속도를 위해 데이터가 있는 동일한 Azure 지역에서 다운로드하는지 확인하면 됩니다.

<br>

****

속성(ID)|데이터 형식|설명|반환된 값의 예
:---|:---|:---|:---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록|"[Https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...1", "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export...2"]
GeneratedTime|문자열|내보내기 생성 시간입니다.|2021-05-20T08:00:00Z
|

### <a name="26-examples"></a>2.6 예제

#### <a name="261-request-example"></a>2.6.1 요청 예제

```http
GET https://api.securitycenter.microsoft.com/api/machines/SoftwareInventoryExport
```

#### <a name="262-response-example"></a>2.6.2 응답 예제

```json
{
    "@odata.context": "https://api.securitycenter.microsoft.com/api/$metadata#microsoft.windowsDefenderATP.api.ExportFilesResponse",
    "exportFiles": [
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00393-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c000.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=...",
        "https://tvmexportstrstgeus.blob.core.windows.net/tvm-export/2021-01-11/1101/SoftwareInventory/json/OrgId=12345678-195f-4223-9c7a-99fb420fd000/part-00394-e423630d-4c69-4490-8769-a4f5468c4f25.c001.json.gz?sv=2019-12-12&st=2021-01-11T11%3A55%3A51Z&se=2021-01-11T14%3A55%3A51Z&sr=b&sp=r&sig=..."
    ],
    "generatedTime": "2021-01-11T11:01:00Z"
}
```

## <a name="see-also"></a>참고 항목

- [장치당 평가 방법 및 속성 내보내기](get-assessment-methods-properties.md)
- [장치당 보안 구성 평가 내보내기](get-assessment-secure-config.md)
- [장치당 소프트웨어 취약점 평가 내보내기](get-assessment-software-vulnerabilities.md)

기타 관련

- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
