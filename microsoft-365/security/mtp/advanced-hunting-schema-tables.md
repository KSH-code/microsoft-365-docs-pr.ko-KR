---
title: Microsoft Threat Protection 고급 헌팅 스키마의 데이터 표
description: 고급 헌팅 스키마의 표에 대해 알아보고 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석,
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, data
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 308337f806d54f1beb7ae6112b2ed883707d4513
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 08/12/2020
ms.locfileid: "46649298"
---
# <a name="understand-the-advanced-hunting-schema"></a>고급 헌팅 스키마 이해

**적용 대상:**
- Microsoft Threat Protection

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

[고급 구하기](advanced-hunting-overview.md) 스키마는 이벤트 정보나 장치, 경고, id 및 기타 엔터티 유형에 대 한 정보를 제공 하는 여러 테이블로 구성 됩니다. 여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.

## <a name="get-schema-information-in-the-security-center"></a>보안 센터에서 스키마 정보 가져오기
쿼리를 구성 하는 동안 기본 제공 스키마 참조를 사용 하 여 스키마의 각 테이블에 대 한 다음 정보를 빠르게 확인할 수 있습니다.

- **테이블 설명** — 테이블에 포함 된 데이터 형식 및 해당 데이터의 원본
- **열** -테이블의 모든 열입니다.
- **작업 유형** - `ActionType` 표에서 지원 되는 이벤트 유형을 나타내는 열의 가능한 값입니다. 이는 이벤트 정보가 포함 된 테이블에 대해서만 제공 됩니다.
- **예제 쿼리** -테이블을 사용 하는 방법을 설명 하는 쿼리를 예로 들 수 있습니다.

### <a name="access-the-schema-reference"></a>스키마 참조 액세스
스키마 참조에 빠르게 액세스 하려면 스키마 표현의 테이블 이름 옆에 있는 **참조 보기** 작업을 선택 합니다. **스키마 참조** 를 선택 하 여 테이블을 검색할 수도 있습니다.   

![포털에서 스키마 참조에 액세스 하는 방법을 보여 주는 이미지 ](../../media/mtp-ah/ah-reference.png) 

## <a name="schema-tables"></a>스키마 표
다음 참조는 스키마에서 모든 표를 나열합니다. 각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다. 표 및 열 이름은 고급 헌팅 화면에서 스키마 표현의 일부로 보안 센터에도 나열됩니다.

| 테이블 이름 | 설명 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 알림과 연결 된 파일, IP 주소, Url, 사용자 또는 장치 |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 심각도 정보 및 위협 분류를 포함 하 여 Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security 및 Azure ATP의 알림  |
| **[AppFileEvents](advanced-hunting-appfileevents-table.md)** | 클라우드 앱 및 서비스의 파일 관련 활동 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender Antivirus 및 익스플로잇 보호와 같은 보안 컨트롤에서 트리거되는 이벤트를 포함한 여러 이벤트 유형 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | 끝점의 인증서 확인 이벤트에서 가져온 서명 된 파일의 인증서 정보 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 파일 생성, 수정 및 기타 파일 시스템 이벤트 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 로딩 이벤트 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 컴퓨터 정보(OS 정보 포함) |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 장치에 대 한 로그인 및 기타 인증 이벤트 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 네트워크 연결 및 관련 이벤트 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 연결된 네트워크 및 도메인뿐만 아니라 어댑터, IP 및 MAC 주소를 비롯한 컴퓨터의 네트워크 속성 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 프로세스 생성 및 관련 이벤트 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 레지스트리 항목 생성 및 수정 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함  |
| **[DeviceTvmSoftwareInventoryVulnerabilities](advanced-hunting-devicetvmsoftwareinventoryvulnerabilities-table.md)** | 이러한 소프트웨어 제품의 알려진 모든 취약점과 함께 장치의 소프트웨어 인벤터리 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 전자 메일에 첨부 된 파일에 대 한 정보 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | 전자 메일 배달 및 차단 이벤트를 비롯 한 Microsoft 365 전자 메일 이벤트 |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365이 전자 메일을 받는 사람 사서함으로 배달 한 후 배달 후 발생 하는 보안 이벤트 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 전자 메일의 Url에 대 한 정보 |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory를 비롯 한 다양 한 원본의 계정 정보 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory 및 Microsoft online services의 인증 이벤트 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | Active Directory 개체에 대해 수행 되는 쿼리 작업 (예: 사용자, 그룹, 장치 및 도메인) |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 id 간 헌트](advanced-hunting-query-emails-devices.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
