---
title: 고급 구하기 스키마의 DeviceRegistryEvents 테이블
description: 고급 구하기 스키마의 DeviceRegistryEvents 테이블에서 쿼리할 수 있는 레지스트리 이벤트에 대해 자세히 알아봅니다.
keywords: 고급 구하기, 위협 검색, 사이버 위협 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, registryevents, registry, DeviceRegistryEvents, key, subkey, 값
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
ms.openlocfilehash: 8cc9cbabe481826e2f67c1734c2bb4611297dfcb
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/22/2020
ms.locfileid: "48197028"
---
# <a name="deviceregistryevents"></a>DeviceRegistryEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 위협 방지

`DeviceRegistryEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 레지스트리 항목 만들기 및 수정에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지 원하는 이벤트 유형 (값)에 대 한 자세한 내용은 `ActionType` 보안 센터에서 사용할 수 있는 [기본 제공 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 사용 하십시오.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. 자세한 내용은 [portal 스키마 참조](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 를 참조 하세요. |
| `RegistryKey` | 문자열 | 기록 된 작업이 적용 된 레지스트리 키 |
| `RegistryValueType` | 문자열 | 기록 된 작업이 적용 된 레지스트리 값의 데이터 형식 (예: binary 또는 string)입니다. |
| `RegistryValueName` | 문자열 | 기록 된 작업이 적용 된 레지스트리 값의 이름입니다. |
| `RegistryValueData` | 문자열 | 기록 된 작업이 적용 된 레지스트리 값의 데이터입니다. |
| `PreviousRegistryValueName` | 문자열 | 수정 되기 전의 레지스트리 값의 원래 이름입니다. |
| `PreviousRegistryValueData` | 문자열 | 수정 되기 전의 레지스트리 값에 대 한 원본 데이터 |
| `InitiatingProcessAccountDomain` | 문자열 | 이벤트를 담당 하는 프로세스를 실행 한 계정의 도메인입니다. |
| `InitiatingProcessAccountName` | 문자열 | 이벤트를 담당 하는 프로세스를 실행 한 계정의 사용자 이름입니다. |
| `InitiatingProcessAccountSid` | 문자열 | 이벤트를 담당 하는 프로세스를 실행 한 계정의 SID (보안 식별자)입니다. |
| `InitiatingProcessSHA1` | 문자열 | 이벤트를 시작한 프로세스 (이미지 파일)의 SHA-1 |
| `InitiatingProcessSHA256` | 문자열 | 이벤트를 시작한 프로세스 (이미지 파일)의 SHA-256입니다. 일반적으로이 필드는 채워지지 않습니다. 가능한 경우 SHA1 열을 사용합니다. |
| `InitiatingProcessMD5` | 문자열 | 이벤트를 시작한 프로세스 (이미지 파일)의 MD5 해시 |
| `InitiatingProcessFileName` | 문자열 | 이벤트를 시작한 프로세스의 이름입니다. |
| `InitiatingProcessId` | int | 이벤트를 시작한 프로세스의 PID (프로세스 ID) |
| `InitiatingProcessCommandLine` | 문자열 | 이벤트를 시작한 프로세스를 실행 하는 데 사용 되는 명령줄입니다. |
| `InitiatingProcessCreationTime` | datetime | 이벤트를 시작한 프로세스를 시작한 날짜 및 시간입니다. |
| `InitiatingProcessFolderPath` | 문자열 | 이벤트를 시작한 프로세스 (이미지 파일)가 들어 있는 폴더 |
| `InitiatingProcessParentId` | int | 이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 PID (프로세스 ID)입니다. |
| `InitiatingProcessParentFileName` | 문자열 | 이벤트를 담당 하는 프로세스를 생성 한 상위 프로세스의 이름입니다. |
| `InitiatingProcessParentCreationTime` | datetime | 이벤트를 담당 하는 프로세스의 부모를 시작한 날짜 및 시간입니다. |
| `InitiatingProcessIntegrityLevel` | 문자열 | 이벤트를 시작한 프로세스의 무결성 수준입니다. Windows에서는 인터넷 다운로드에서 시작 된 경우와 같이 특정 특성에 따라 프로세스에 무결성 수준을 할당 합니다. 이러한 무결성 수준은 리소스에 대 한 사용 권한에 영향을 줍니다. |
| `InitiatingProcessTokenElevation` | 문자열 | 이벤트를 시작한 프로세스에 UAC (사용자 액세스 제어) 권한 상승이 적용 되었는지 여부를 나타내는 토큰 유형입니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유 이벤트를 식별 하려면이 열을 장치 이름 및 타임 스탬프 열과 함께 사용 해야 합니다. |
| `AppGuardContainerId` | 문자열 | 응용 프로그램 가드가 브라우저 활동을 격리 하는 데 사용 하는 가상화 된 컨테이너의 식별자입니다. |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [기기, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
