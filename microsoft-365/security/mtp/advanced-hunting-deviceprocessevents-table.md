---
title: 고급 헌팅chema의 DeviceProcessEvents 테이블
description: 고급 헌팅 과정의 DeviceProcessEventstable에서 생성 이벤트 생성 또는 프로세스에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, processcreationevents, DeviceProcessEvents, process id, command line, DeviceProcessEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6f94b861aa73d01f9e906d41bc52a9724552cd33
ms.sourcegitcommit: 005028af7c5a6b2e95f17a0037958131484d9e73
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/08/2021
ms.locfileid: "50145514"
---
# <a name="deviceprocessevents"></a>DeviceProcessEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender



고급 `DeviceProcessEvents` 헌팅 [계획의](advanced-hunting-overview.md) 표에는 프로세스 만들기 및 관련 이벤트에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 [내 Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록된 작업이 적용된 파일이 들어 있는 폴더 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `MD5` | 문자열 | 기록된 작업이 적용된 파일의 MD5 해시입니다. |
| `ProcessId` | int | 새로 만든 프로세스의 PID(프로세스 ID)입니다. |
| `ProcessCommandLine` | 문자열 | 새 프로세스를 만드는 데 사용되는 명령줄 |
| `ProcessIntegrityLevel` | 문자열 | 새로 만든 프로세스의 무결성 수준입니다. Windows는 다운로드한 인터넷에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다. 이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치기 |
| `ProcessTokenElevation` | 문자열 | 새로 만든 프로세스에 적용되는 토큰 권한 상승 유형을 나타냅니다. 가능한 값: TokenElevationTypeLimited(제한), TokenElevationTypeDefault(표준) 및 TokenElevationTypeFull(상승) |
| `ProcessCreationTime` | datetime | 프로세스가 만들어진 날짜 및 시간 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `AccountObjectId` | 문자열 | Azure AD에서 계정의 고유 식별자 |
| `LogonId` | 문자열 | 로그온 세션의 식별자입니다. 이 식별자는 다시 시작 사이에만 동일한 컴퓨터의 고유 식별자입니다. |
| `InitiatingProcessAccountDomain` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다. |
| `InitiatingProcessAccountName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다. |
| `InitiatingProcessAccountSid` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다. |
| `InitiatingProcessAccountUpn` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 UPN(사용자 계정 이름) |
| `InitiatingProcessAccountObjectId` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 사용자 계정의 Azure AD 개체 ID입니다. |
| `InitiatingProcessLogonId` | 문자열 | 이벤트를 시작한 프로세스의 로그온 세션 식별자입니다. 이 식별자는 다시 시작 사이에만 동일한 컴퓨터의 고유합니다. |
| `InitiatingProcessIntegrityLevel` | 문자열 | 이벤트를 시작한 프로세스의 무결성 수준입니다. Windows는 인터넷 다운로드에서 시작된 경우와 같은 특정 특성을 기반으로 프로세스에 무결성 수준을 할당합니다. 이러한 무결성 수준은 리소스에 대한 사용 권한에 영향을 미치게 됩니다. |
| `InitiatingProcessTokenElevation` | 문자열 | 이벤트를 시작한 프로세스에 적용된 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식입니다. |
| `InitiatingProcessSHA1` | 문자열 | 이벤트를 시작한 프로세스의 SHA-1(이미지 파일) |
| `InitiatingProcessSHA256` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다. 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `InitiatingProcessMD5` | 문자열 | 이벤트를 시작한 프로세스의 MD5 해시(이미지 파일) |
| `InitiatingProcessFileName` | 문자열 | 이벤트를 시작한 프로세스의 이름입니다. |
| `InitiatingProcessFileSize` | long | 이벤트를 담당하는 프로세스를 시작한 파일의 크기입니다. |
| `InitiatingProcessId` | int | 이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessCommandLine` | 문자열 | 이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄 |
| `InitiatingProcessCreationTime` | datetime | 이벤트를 시작한 프로세스가 시작된 날짜 및 시간 |
| `InitiatingProcessFolderPath` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)가 들어 있는 폴더 |
| `InitiatingProcessParentId` | int | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessParentFileName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다. |
| `InitiatingProcessParentCreationTime` | datetime | 이벤트를 담당하는 프로세스의 상위 프로세스가 시작된 날짜 및 시간 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 타임스탬프 열과 함께 사용해야 합니다. |
| `AppGuardContainerId` | 문자열 | Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자 |
| `AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대한 추가 정보 |
| `FileSize` | long | 파일 크기(bytes)입니다. |

## <a name="related-topics"></a>관련 주제
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
