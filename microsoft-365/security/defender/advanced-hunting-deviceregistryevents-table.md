---
title: 고급 헌팅 스위마의 DeviceRegistryEvents 테이블
description: 고급 헌팅 키의 DeviceRegistryEvents 테이블에서 쿼리할 수 있는 레지스트리 이벤트에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, registryevents, 레지스트리, DeviceRegistryEvents, 키, 하위 키, 값
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
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: a6d41489e84935e580a1f749e8dd891affa9c2a6
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60646910"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender

고급 `DeviceRegistryEvents` 헌팅 [키마의](advanced-hunting-overview.md) 표에는 레지스트리 항목 만들기 및 수정에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `RegistryKey` | 문자열 | 기록된 작업이 적용된 레지스트리 키 |
| `RegistryValueType` | 문자열 | 기록된 작업이 적용된 레지스트리 값의 데이터 형식(예: 이진 또는 문자열) |
| `RegistryValueName` | 문자열 | 기록된 작업이 적용된 레지스트리 값의 이름입니다. |
| `RegistryValueData` | 문자열 | 기록된 작업이 적용된 레지스트리 값의 데이터 |
| `PreviousRegistryKey` | 문자열 | 레지스트리 값을 수정하기 전의 원래 레지스트리 키 |
| `PreviousRegistryValueName` | 문자열 | 수정되기 전의 레지스트리 값의 원래 이름입니다. |
| `PreviousRegistryValueData` | 문자열 | 레지스트리 값을 수정하기 전의 원래 데이터 |
| `InitiatingProcessAccountDomain` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다. |
| `InitiatingProcessAccountName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다. |
| `InitiatingProcessAccountSid` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다. |
| `InitiatingProcessAccountUpn` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 UPN(사용자 계정 이름)입니다. |
| `InitiatingProcessAccountObjectId` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 사용자 계정의 Azure AD 개체 ID입니다. |
| `InitiatingProcessSHA1` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 SHA-1 |
| `InitiatingProcessSHA256` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다. 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `InitiatingProcessMD5` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다. |
| `InitiatingProcessFileName` | 문자열 | 이벤트를 시작한 프로세스의 이름입니다. |
| `InitiatingProcessFileSize` | long | 이벤트를 담당하는 프로세스를 시작한 파일의 크기입니다. |
| `InitiatingProcessVersionInfoCompanyName` | 문자열 | 이벤트를 담당하는 프로세스의 버전 정보(이미지 파일)의 회사 이름 |
| `InitiatingProcessVersionInfoProductName` | 문자열 | 이벤트를 담당하는 프로세스의 버전 정보(이미지 파일)의 제품 이름 |
|` InitiatingProcessVersionInfoProductVersion` | 문자열 | 이벤트를 담당하는 프로세스의 버전 정보(이미지 파일)의 제품 버전 |
|` InitiatingProcessVersionInfoInternalFileName` | 문자열 | 이벤트를 담당하는 프로세스의 버전 정보(이미지 파일)의 내부 파일 이름 |
| `InitiatingProcessVersionInfoOriginalFileName` | 문자열 | 이벤트를 담당하는 프로세스의 버전 정보(이미지 파일)의 원래 파일 이름입니다. |
| `InitiatingProcessVersionInfoFileDescription` | 문자열 | 이벤트를 담당하는 프로세스(이미지 파일)의 버전 정보 설명 |
| `InitiatingProcessId` | int | 이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessCommandLine` | 문자열 | 이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄 |
| `InitiatingProcessCreationTime` | datetime | 이벤트를 시작한 프로세스가 시작된 날짜 및 시간 |
| `InitiatingProcessFolderPath` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더 |
| `InitiatingProcessParentId` | int | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessParentFileName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다. |
| `InitiatingProcessParentCreationTime` | datetime | 이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다. |
| `InitiatingProcessIntegrityLevel` | 문자열 | 이벤트를 시작한 프로세스의 무결성 수준입니다. Windows 인터넷 다운로드에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다. 이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기 |
| `InitiatingProcessTokenElevation` | 문자열 | 이벤트를 시작한 프로세스에 적용되는 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |
| `AppGuardContainerId` | 문자열 | Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
