---
title: 고급 헌팅 Microsoft 365 Defender 데이터 테이블
description: 고급 헌팅 스키마의 표에 대해 알아보고 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석,
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 데이터
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 4dcbb7051325483a220c39fdebaae53aba9c37f4
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59214632"
---
# <a name="understand-the-advanced-hunting-schema"></a>고급 헌팅 스키마 이해

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

고급 [헌팅](advanced-hunting-overview.md) 스마는 장치, 경고, ID 및 기타 엔터티 유형에 대한 이벤트 정보 또는 정보를 제공하는 여러 테이블로 구성됩니다. 여러 표를 포괄하는 쿼리를 효과적으로 작성하려면 고급 헌팅 스키마에서 표 및 열을 이해해야 합니다.

## <a name="get-schema-information-in-the-security-center"></a>보안 센터에서 스마마 정보 얻기
쿼리를 구성하는 동안 기본 제공된 Schema 참조를 사용하여 해당 schema의 각 테이블에 대한 다음 정보를 빠르게 얻을 수 있습니다.

- **테이블 설명**- 테이블에 포함된 데이터 형식 및 해당 데이터의 원본입니다.
- **열**- 표의 모든 열입니다.
- **동작 유형**- 테이블에서 지원하는 이벤트 유형을 나타내는 열의 `ActionType` 가능한 값입니다. 이 정보는 이벤트 정보가 포함된 표에만 제공됩니다.
- **예제 쿼리**- 테이블을 활용하는 방법을 특징으로 하는 쿼리 예제입니다.

### <a name="access-the-schema-reference"></a>Schema 참조 액세스
스마마 참조에 빠르게 액세스하려면  해당 Schema 표현에서 테이블 이름 옆에 있는 참조 보기 작업을 선택합니다. 또한 **Schema 참조를 선택하여** 테이블을 검색할 수도 있습니다.

![포털 내 Schema 참조에 액세스하는 방법을 보여주는 이미지입니다.](../../media/mtp-ah/ah-reference.png)

## <a name="learn-the-schema-tables"></a>Schema 테이블에 대해 자세히 알아보기
다음 참조는 스키마에서 모든 표를 나열합니다. 각 표 이름은 해당 표의 열 이름을 설명하는 페이지에 연결됩니다. 표 및 열 이름은 고급 헌팅 화면의 Schema 표현의 일부로 보안 센터에도 나열됩니다.

| 테이블 이름 | 설명 |
|------------|-------------|
| **[AlertEvidence](advanced-hunting-alertevidence-table.md)** | 경고와 연결된 파일, IP 주소, URL, 사용자 또는 장치 |
| **[AlertInfo](advanced-hunting-alertinfo-table.md)** | 심각도 정보 및 위협 분류를 포함하여 Microsoft Defender for endpoint, Office 365, Microsoft Cloud App Security 및 ID에 대한 Microsoft Defender의 경고  |
| **[CloudAppEvents](advanced-hunting-cloudappevents-table.md)** | Office 365 및 기타 클라우드 앱과 서비스의 계정 및 개체 관련 이벤트 |
| **[DeviceEvents](advanced-hunting-deviceevents-table.md)** | Windows Defender 바이러스 백신 및 익스플로잇 보호와 같은 보안 컨트롤에서 트리거되는 이벤트를 포함한 여러 이벤트 유형 |
| **[DeviceFileCertificateInfo](advanced-hunting-DeviceFileCertificateInfo-table.md)** | 엔드포인트의 인증서 확인 이벤트에서 얻은 서명된 파일의 인증서 정보 |
| **[DeviceFileEvents](advanced-hunting-devicefileevents-table.md)** | 파일 생성, 수정 및 기타 파일 시스템 이벤트 |
| **[DeviceImageLoadEvents](advanced-hunting-deviceimageloadevents-table.md)** | DLL 로딩 이벤트 |
| **[DeviceInfo](advanced-hunting-deviceinfo-table.md)** | 컴퓨터 정보(OS 정보 포함) |
| **[DeviceLogonEvents](advanced-hunting-devicelogonevents-table.md)** | 장치의 로그인 및 기타 인증 이벤트 |
| **[DeviceNetworkEvents](advanced-hunting-devicenetworkevents-table.md)** | 네트워크 연결 및 관련 이벤트 |
| **[DeviceNetworkInfo](advanced-hunting-devicenetworkinfo-table.md)** | 연결된 네트워크 및 도메인뿐만 아니라 물리적 어댑터, IP 및 MAC 주소를 비롯한 장치의 네트워크 속성 |
| **[DeviceProcessEvents](advanced-hunting-deviceprocessevents-table.md)** | 프로세스 생성 및 관련 이벤트 |
| **[DeviceRegistryEvents](advanced-hunting-deviceregistryevents-table.md)** | 레지스트리 항목 생성 및 수정 |
| **[DeviceTvmSecureConfigurationAssessment](advanced-hunting-devicetvmsecureconfigurationassessment-table.md)** | 장치에서 다양한 보안 구성의 상태를 나타내는 위협 및 취약성 관리 평가 이벤트 |
| **[DeviceTvmSecureConfigurationAssessmentKB](advanced-hunting-devicetvmsecureconfigurationassessmentkb-table.md)** | 위협 및 취약성 관리에서 장치를 평가하기 위해 사용하는 다양한 보안 구성에 대한 기술 자료. 다양한 표준과 벤치 마크에 대한 매핑 포함  |
| **[DeviceTvmSoftwareInventory](advanced-hunting-devicetvmsoftwareinventory-table.md)** | 버전 정보 및 지원 종료 상태를 포함하여 장치에 설치된 소프트웨어 인벤토리 |
| **[DeviceTvmSoftwareVulnerabilities](advanced-hunting-devicetvmsoftwarevulnerabilities-table.md)** | 장치에서 발견되는 소프트웨어 취약점 및 각 취약점을 해결하기 위한 사용 가능한 보안 업데이트 목록 |
| **[DeviceTvmSoftwareVulnerabilitiesKB](advanced-hunting-devicetvmsoftwarevulnerabilitieskb-table.md)** | 익스플로잇 코드를 공개적으로 사용할 수 있는지를 포함하여 공개적으로 보고된 취약성에 대한 기술 자료 |
| **[EmailAttachmentInfo](advanced-hunting-emailattachmentinfo-table.md)** | 전자 메일에 첨부된 파일에 대한 정보 |
| **[EmailEvents](advanced-hunting-emailevents-table.md)** | 전자 메일 배달과 차단 이벤트를 포함한 Microsoft 365 전자 메일 이벤트 |
| **[EmailPostDeliveryEvents](advanced-hunting-emailpostdeliveryevents-table.md)** | Microsoft 365가 받는 사람 사서함에 전자 메일을 배달하고 나서 배달 후 발생하는 보안 이벤트 |
| **[EmailUrlInfo](advanced-hunting-emailurlinfo-table.md)** | 전자 메일의 URL에 대한 정보 |
| **[IdentityDirectoryEvents](advanced-hunting-identitydirectoryevents-table.md)** | Active Directory(AD)를 실행하는 온-프레미스 도메인 컨트롤러와 관련된 이벤트. 이 표에서는 도메인 컨트롤러의 다양한 ID 관련 이벤트 및 시스템 이벤트를 다룹니다. |
| **[IdentityInfo](advanced-hunting-identityinfo-table.md)** | Azure Active Directory를 비롯한 다양한 원본의 계정 정보 |
| **[IdentityLogonEvents](advanced-hunting-identitylogonevents-table.md)** | Active Directory 및 Microsoft 온라인 서비스의 인증 이벤트 |
| **[IdentityQueryEvents](advanced-hunting-identityqueryevents-table.md)** | 사용자, 그룹, 장치 및 도메인과 같은 Active Directory 개체에 대한 쿼리 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [쿼리 결과로 작업](advanced-hunting-query-results.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
