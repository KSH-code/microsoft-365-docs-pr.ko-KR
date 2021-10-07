---
title: 장치당 평가 방법 및 속성 내보내기
description: "\"데이터 원본\" 데이터를 끌어오는 위협 및 취약성 관리 정보를 제공합니다. 다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다. 일반적으로 각 API 호출에는 조직의 디바이스에 대한 필요합니다."
keywords: api, api, 내보내기 평가, 장치 평가당, 컴퓨터 평가, 취약성 평가 보고서, 장치 취약점 평가, 장치 취약점 보고서, 보안 구성 평가, 보안 구성 보고서, 소프트웨어 취약점 평가, 소프트웨어 취약성 보고서, 컴퓨터의 취약점 보고서,
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
ms.openlocfilehash: a5870f91bd154ddf344c7914c44c96e438fc9f99
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211192"
---
# <a name="export-assessment-methods-and-properties-per-device"></a>장치당 평가 방법 및 속성 내보내기

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**

- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 엔드포인트용 Microsoft Defender를 경험하고 싶으신가요? [무료 평가판을 신청하세요.](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

## <a name="api-description"></a>API 설명

장치 기준에 따라 위협 및 취약성 관리 끌어오는 API에 대한 메서드 및 속성 세부 정보를 제공합니다. 다양한 형식의 데이터를 얻기 위해 다른 API 호출이 있습니다. 일반적으로 각 API 호출에는 조직의 디바이스에 대한 필요합니다.

> [!NOTE]
> 다른 설명이 없는 한 나열된 **** 모든 내보내기 평가 방법은 전체 내보내기 및 장치(장치당 **** **_참조)입니다._**

평가 내보내기 API를 사용하여 다양한 유형의 정보를 검색(내보내기)할 수 있습니다.

- [1. 보안 구성 평가 내보내기](#1-export-secure-configurations-assessment)
- [2. 소프트웨어 인벤토리 평가 내보내기](#2-export-software-inventory-assessment)
- [3. 소프트웨어 취약성 평가 내보내기](#3-export-software-vulnerabilities-assessment)

내보내기 정보 유형에 해당하는 API는 1, 2 및 3 섹션에 설명되어 있습니다.

각 메서드에 대해 서로 다른 형식의 데이터를 얻을 수 있는 다른 API 호출이 있습니다. 데이터 양은 매우 크기 때문에 다음 두 가지 방법으로 데이터를 검색할 수 있습니다.

- **JSON 응답**  API는 조직의 모든 데이터를 JSON 응답으로 끌어들입니다. 이 방법은 _100 K_ 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적이기 때문에 응답의 odata.nextLink 필드를 사용하여 다음 결과를 \@ 내보일 수 있습니다.

- **파일을 통해** 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다.
  - API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.
  - 다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.

_JSON_ 응답 또는 파일을 통해 수집되는 데이터는 현재 상태의 현재 스냅숏으로 기록 데이터가 포함되지 않습니다.  기록 데이터를 수집하려면 고객은 데이터를 자체 데이터 저장소에 저장해야 합니다.

## <a name="1-export-secure-configurations-assessment"></a>1. 보안 구성 평가 내보내기

장치 기준에 따라 모든 구성 및 구성 상태를 반환합니다.

### <a name="11-methods"></a>1.1 메서드

방법|데이터 형식|설명
:---|:---|:---
보안 구성 평가 **내보내기(JSON 응답)**|장치 컬렉션에 따라 보안 구성. 참조: [1.2 속성(JSON 응답)](#12-properties-json-response)|DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. API는 조직의 모든 데이터를 JSON 응답으로 끌어들입니다. 이 방법은 100 K 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.
파일로 보안 **구성 평가 내보내기**|장치 컬렉션에 따라 보안 구성. 참조: [1.3 속성(파일을 통해)](#13-properties-via-files)|DeviceId, ConfigurationId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다. <ol><li>API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</li><li>다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</li></ol>

### <a name="12-properties-json-response"></a>1.2 속성(JSON 응답)

속성(ID)|데이터 형식|설명
:---|:---|:---
configurationCategory|문자열|구성이 속하는 범주 또는 그룹화: 응용 프로그램, OS, 네트워크, 계정, 보안 제어.
configurationId|문자열|특정 구성의 고유 식별자입니다.
configurationImpact|문자열|구성이 전체 구성 점수에 미치는 영향(1~10)입니다.
configurationName|문자열|구성의 표시 이름입니다.
configurationSubcategory|문자열|구성이 속한 하위 범주나 하위 그룹 대부분의 경우 이는 특정 기능이나 특징을 설명합니다.
deviceId|문자열|서비스에서 장치의 고유 식별자입니다.
deviceName|문자열|장치의 FQDN(FQDN)입니다.
isApplicable|bool|구성 또는 정책을 적용할 수 있는지 여부를 나타냅니다.
isCompliant|bool|구성 또는 정책이 제대로 구성되었는지 여부를 나타냅니다.
isExpectedUserImpact|bool|구성을 적용할 경우 사용자 영향이 있는지 여부를 나타냅니다.
osPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 TVM 지원 운영 체제 및 플랫폼을 참조하세요.
osVersion|문자열|장치에서 실행되는 운영 체제의 특정 버전입니다.
rbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.
rbacGroupId|문자열|RBAC(역할 기반 액세스 제어) 그룹 ID입니다.
recommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.
타임스탬프|문자열|장치에서 구성을 마지막으로 확인한 시간입니다.

### <a name="13-properties-via-files"></a>1.3 속성(파일을 통해)

속성(ID)|데이터 형식|설명
:---|:---|:---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.
GeneratedTime|문자열|내보내기 생성 시간입니다.

## <a name="2-export-software-inventory-assessment"></a>2. 소프트웨어 인벤토리 평가 내보내기

설치된 모든 소프트웨어 및 각 디바이스의 세부 정보를 반환합니다.

### <a name="21-methods"></a>2.1 메서드

방법|데이터 형식|설명
:---|:---|:---
소프트웨어 인벤토리 평가 **내보내기(JSON 응답)**|장치 모음의 소프트웨어 인벤토리입니다. 참조: [2.2 속성(JSON 응답)](#22-properties-json-response)|DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. API는 조직의 모든 데이터를 JSON 응답으로 끌어들입니다. 이 방법은 100 K 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.
파일로 소프트웨어 인벤토리 **평가 내보내기**|장치 파일로 소프트웨어 인벤토리. 참조: [2.3 속성(파일을 통해)](#23-properties-via-files)|DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다. <ol><li>API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 다운로드합니다.</li><li>다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</li></ol>

### <a name="22-properties-json-response"></a>2.2 속성(JSON 응답)

속성(ID)|데이터 형식|설명
:---|:---|:---
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.
장치 이름|문자열|장치의 FQDN(FQDN)입니다.
DiskPaths|Array[string]|제품이 장치에 설치되어 있는 디스크 증거입니다.
EndOfSupportDate|문자열|이 소프트웨어에 대한 지원이 종료되는 날짜입니다.
EndOfSupportStatus|문자열|지원 종료 상태입니다. None, EOS 버전, 예정된 EOS 버전, EOS 소프트웨어, 예정된 EOS 소프트웨어 등 가능한 값을 포함할 수 있습니다.
NumberOfWeaknesses|int|이 장치에서 이 소프트웨어에 대한 약점 수입니다.
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.
rbacGroupId|문자열|RBAC(역할 기반 액세스 제어) 그룹 ID입니다.
RegistryPaths|Array[string]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.
SoftwareFirstSeenTimestamp|문자열|디바이스에서 이 소프트웨어를 처음 볼 수 있습니다.
SoftwareName|문자열|소프트웨어 제품의 이름입니다.
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.

### <a name="23-properties-via-files"></a>2.3 속성(파일을 통해)

속성(ID)|데이터 형식|설명
:---|:---|:---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.
GeneratedTime|문자열|내보내기 생성 시간입니다.

## <a name="3-export-software-vulnerabilities-assessment"></a>3. 소프트웨어 취약성 평가 내보내기

장치에 알려진 모든 취약성 및 모든 장치에 대한 세부 정보를 반환합니다.

### <a name="31-methods"></a>3.1 메서드

방법|데이터 형식|설명
:---|:---|:---
소프트웨어 취약점 평가 **내보내기(JSON 응답)**|조사 컬렉션 참조: [3.2 속성(JSON 응답)](#32-properties-json-response)|DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. API는 조직의 모든 데이터를 JSON 응답으로 끌어들입니다. 이 방법은 100 K 장치 미만의 소규모 조직에 가장 적합한 방법입니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다.
파일로 소프트웨어 취약점 평가 **내보내기**|조사 엔터티 참조: [3.3 속성(파일을 통해)](#33-properties-via-files)|DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. 이 API 솔루션을 사용하면 더 많은 양의 데이터를 더 빠르고 안정적으로 끌어 올 수 있습니다. 따라서 100 K 장치가 넘는 대규모 조직에 권장됩니다. 이 API는 조직의 모든 데이터를 다운로드 파일로 끌어들입니다. 응답에는 응답에서 모든 데이터를 다운로드하는 URL이 Azure Storage. 이 API를 사용하면 다음과 같이 모든 데이터를 Azure Storage 수 있습니다. <ol><li>API를 호출하여 모든 조직 데이터와 함께 다운로드 URL 목록을 얻습니다.</li><li>다운로드 URL을 사용하여 모든 파일을 다운로드하고 원하는 데이터를 처리합니다.</li></ol>
**델타 내보내기** 소프트웨어 취약점 **평가(JSON 응답)**|조사 컬렉션 참조: [3.4 속성 델타 내보내기(JSON 응답)](#34-properties-delta-export-json-response)|DeviceId, SoftwareVendor, SoftwareName, SoftwareVersion, CveId 및 EventTimestamp의 모든 고유 조합에 대한 항목이 있는 테이블을 반환합니다. <p> API는 JSON 응답으로 조직의 데이터를 끌어 습니다. 응답이 단계적으로 진행되어 응답의 @odata.nextLink 필드를 사용하여 다음 결과를 내보일 수 있습니다. 장치로 조직의 소프트웨어 취약점 평가에 대한 전체 스냅숏을 얻는 데 사용되는 전체 소프트웨어 취약점 평가(JSON 응답)와 달리 델타 내보내기 API 호출은 선택한 날짜와 현재 날짜("델타" API 호출) 사이에 수행된 변경 내용만 페치하는 데 사용됩니다. 매월 많은 양의 데이터를 사용하여 전체 내보내기 대신 신규, 고정 및 업데이트된 취약성에 대한 특정 정보만 얻을 수 있습니다. 델타 내보내기 API 호출을 사용하여 "고정된 취약성 수"과 같은 다양한 KPI를 계산할 수도 있습니다. 또는 "조직에 추가된 새 취약성의 수가 몇 개인가요?" <p> 소프트웨어 취약성에 대한 델타 내보내기 API 호출은 대상 날짜 범위에 대한 데이터만 반환하기 때문에 전체 _내보내기로 간주되지 않습니다._

### <a name="32-properties-json-response"></a>3.2 속성(JSON 응답)

속성(ID)|데이터 형식|설명
:---|:---|:---
CveId|문자열|CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.
CvssScore|문자열|CVE의 CVSS 점수입니다.
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.
장치 이름|문자열|장치의 FQDN(FQDN)입니다.
DiskPaths|배열 \[ 문자열\]|제품이 장치에 설치되어 있는 디스크 증거입니다.
ExploitabilityLevel|문자열|이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|문자열|이 제품의 CVE가 디바이스에 처음 표시됩니다.
Id|문자열|레코드의 고유 식별자입니다.
LastSeenTimestamp|문자열|디바이스에서 CVE를 마지막으로 본 시간입니다.
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.
rbacGroupId|문자열|RBAC(역할 기반 액세스 제어) 그룹 ID입니다.
RecommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.
RecommendedSecurityUpdate|문자열|소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.
RecommendedSecurityUpdateId|문자열|해당 지침 또는 KB(기술 자료) 문서의 해당 보안 업데이트 또는 식별자 식별자입니다.
레지스트리 경로 배열 \[ 문자열\]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.
SoftwareName|문자열|소프트웨어 제품의 이름입니다.
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.
VulnerabilitySeverityLevel|문자열|CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.

### <a name="33-properties-via-files"></a>3.3 속성(파일을 통해)

속성(ID)|데이터 형식|설명
:---|:---|:---
파일 내보내기|array \[ string\]|조직의 현재 스냅숏을 저장하는 파일의 다운로드 URL 목록입니다.
GeneratedTime|문자열|내보내기 생성 시간입니다.

### <a name="34-properties-delta-export-json-response"></a>3.4 속성(델타 내보내기 JSON 응답)

속성(ID)|데이터 형식|설명
:---|:---|:---
CveId |문자열|CVE(Common Vulnerabilities and Exposures) 시스템의 보안 취약성에 할당된 고유 식별자입니다.
CvssScore|문자열|CVE의 CVSS 점수입니다.
DeviceId|문자열|서비스에서 장치의 고유 식별자입니다.
장치 이름|문자열|장치의 FQDN(FQDN)입니다.
DiskPaths|Array[string]|제품이 장치에 설치되어 있는 디스크 증거입니다.
EventTimestamp|String|이 델타 이벤트를 찾은 시간입니다.
ExploitabilityLevel|문자열|이 취약성의 악용성 수준(NoExploit, ExploitIsPublic, ExploitIsVerified, ExploitIsInKit)
FirstSeenTimestamp|문자열|이 제품의 CVE가 디바이스에 처음 표시됩니다.
Id|문자열|레코드의 고유 식별자입니다.  
LastSeenTimestamp|문자열|디바이스에서 CVE를 마지막으로 본 시간입니다.
OSPlatform|문자열|디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. 자세한 내용은 tvm 지원 운영 체제 및 플랫폼을 참조하세요.
RbacGroupName|문자열|RBAC(역할 기반 액세스 제어) 그룹입니다. 이 장치가 RBAC 그룹에 할당되지 않은 경우 값은 "지정되지 않았습니다."가 됩니다. 조직에 RBAC 그룹이 없는 경우 값은 "없음"이 됩니다.
RecommendationReference|문자열|이 소프트웨어와 관련된 권장 ID에 대한 참조입니다.
RecommendedSecurityUpdate |문자열|소프트웨어 공급업체가 취약점을 해결하기 위해 제공한 보안 업데이트의 이름 또는 설명입니다.
RecommendedSecurityUpdateId |문자열|해당 지침 또는 기술 자료(KB) 문서의 해당 보안 업데이트 또는 식별자 식별자
RegistryPaths |Array[string]|제품이 장치에 설치되어 있는 레지스트리 증거입니다.
SoftwareName|문자열|소프트웨어 제품의 이름입니다.
SoftwareVendor|문자열|소프트웨어 공급업체의 이름입니다.
SoftwareVersion|문자열|소프트웨어 제품의 버전 번호입니다.
상태|String|**새로 추가**   (장치에 도입된 새로운 취약성의 경우).  **고정**   (디바이스에 더 이상 존재하지 않는 취약성의 경우, 즉 수정된 것입니다). **업데이트되었습니다.**   (변경된 장치의 취약성에 대한 경우). 가능한 변경 내용은 CVSS 점수, 악용 가능성 수준, 심각도 수준, DiskPaths, RegistryPaths, RecommendedSecurityUpdate입니다.
VulnerabilitySeverityLevel|문자열|CVSS 점수 및 위협 환경의 영향을 미치는 동적 요인에 따라 보안 취약성에 할당된 심각도 수준입니다.

## <a name="see-also"></a>참고 항목

- [장치당 보안 구성 평가 내보내기](get-assessment-secure-config.md)
- [장치당 소프트웨어 인벤토리 평가 내보내기](get-assessment-software-inventory.md)
- [장치당 소프트웨어 취약점 평가 내보내기](get-assessment-software-vulnerabilities.md)

기타 관련

- [위험 기반 위협 & 취약성 관리](next-gen-threat-and-vuln-mgt.md)
- [조직의 취약성](tvm-weaknesses.md)
