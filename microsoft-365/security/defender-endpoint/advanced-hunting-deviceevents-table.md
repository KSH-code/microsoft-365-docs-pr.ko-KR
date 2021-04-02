---
title: 고급 헌팅chema의 DeviceEvents 테이블
description: 고급 헌팅스키마의 기타 장치 이벤트(DeviceEvents) 표에서 바이러스 백신, 방화벽 및 기타 이벤트 유형에 대해 자세히 알아보시다.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 보안 이벤트, 바이러스 백신, 방화벽, exploit guard, MiscEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1e67da3a5d93c5e8c86afd755c882f3f0459aab0
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51499195"
---
# <a name="deviceevents"></a>DeviceEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


> Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

고급 헌팅 계획의 기타 장치 이벤트 또는 표에는 Microsoft Defender 바이러스 백신 및 악용 방지와 같은 보안 제어에 의해 트리거되는 이벤트를 비롯한 다양한 이벤트 유형에 대한 정보가 포함되어 `DeviceEvents` 있습니다. [](advanced-hunting-overview.md) 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동 유형 |
| `FileName` | 문자열 | 기록된 조치가 적용된 파일의 이름 |
| `FolderPath` | 문자열 | 기록된 작업이 적용된 파일이 들어 있는 폴더 |
| `SHA1` | 문자열 | 기록된 조치가 적용된 파일의 SHA-1 |
| `SHA256` | 문자열 | 기록된 조치가 적용된 파일의 SHA-256 이 필드는 일반적으로 채워지지 않습니다. 사용 가능한 경우 SHA1 열을 사용 |
| `MD5` | 문자열 | 기록된 작업이 적용된 파일의 MD5 해시입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountName` |문자열 | 계정의 사용자 이름 |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `RemoteUrl` | 문자열 | 연결된 URL 또는 FQDN(정규화된 도메인 이름) |
| `RemoteDeviceName` | 문자열 | 영향을 받는 디바이스에서 원격 작업을 수행한 장치의 이름입니다. 보고되는 이벤트에 따라 이 이름은 FQDN(정식 도메인 이름), NetBIOS 이름 또는 도메인 정보가 없는 호스트 이름일 수 있습니다. |
| `ProcessId` | int | 새로 만든 프로세스의 PID(프로세스 ID)입니다. |
| `ProcessCommandLine` | 문자열 | 새 프로세스를 만드는 데 사용되는 명령줄 |
| `ProcessCreationTime` | datetime | 프로세스가 만들어진 날짜 및 시간 |
| `ProcessTokenElevation` | 문자열 | 새로 만든 프로세스에 적용된 UAC(사용자 액세스 제어) 권한 상승의 유무를 나타내는 토큰 형식 |
| `LogonId` | 문자열 | 로그온 세션의 식별자입니다. 이 식별자는 다시 시작 사이에 동일한 장치에서만 고유합니다. |
| `RegistryKey` | 문자열 | 기록된 작업이 적용된 레지스트리 키 |
| `RegistryValueName` | 문자열 | 기록된 작업이 적용된 레지스트리 값의 이름입니다. |
| `RegistryValueData` | 문자열 | 기록된 작업이 적용된 레지스트리 값의 데이터 |
| `RemoteIP` | 문자열 | 연결된 IP 주소 |
| `RemotePort` | int | 연결되고 있는 원격 장치의 TCP 포트 |
| `LocalIP` | 문자열 | 통신 중에 사용되는 로컬 장치에 할당된 IP 주소 |
| `LocalPort` | int | 통신 중에 사용되는 로컬 장치의 TCP 포트 |
| `FileOriginUrl` | 문자열 | 파일을 다운로드한 URL |
| `FileOriginIP` | 문자열 | 파일을 다운로드한 IP 주소 |
| `AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대한 추가 정보 |
| `InitiatingProcessSHA1` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 SHA-1 |
| `InitiatingProcessSHA256` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 SHA-256입니다. 이 필드는 일반적으로 채워지지 않습니다. 사용 가능한 경우 SHA1 열을 사용 |
| `InitiatingProcessFileName` | 문자열 | 이벤트를 시작한 프로세스의 이름입니다. |
| `InitiatingProcessFolderPath` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)가 포함된 폴더 |
| `InitiatingProcessId` | int | 이벤트를 시작한 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessCommandLine` | 문자열 | 이벤트를 시작한 프로세스를 실행하는 데 사용되는 명령줄 |
| `InitiatingProcessCreationTime` | datetime | 이벤트를 시작한 프로세스가 시작된 날짜 및 시간 |
| `InitiatingProcessParentId` | int | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 PID(프로세스 ID)입니다. |
| `InitiatingProcessParentFileName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 상위 프로세스의 이름입니다. |
| `InitiatingProcessParentCreationTime` | datetime | 이벤트를 담당하는 프로세스의 부모가 시작된 날짜 및 시간입니다. |
| `InitiatingProcessMD5` | 문자열 | 이벤트를 시작한 프로세스(이미지 파일)의 MD5 해시입니다. |
| `InitiatingProcessAccountDomain` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 도메인입니다. |
| `InitiatingProcessAccountName` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 사용자 이름입니다. |
| `InitiatingProcessAccountSid` | 문자열 | 이벤트를 담당하는 프로세스를 시작한 계정의 SID(보안 식별자)입니다. |
| `InitiatingProcessLogonId` | 문자열 | 이벤트를 시작한 프로세스의 로그온 세션 식별자입니다. 이 식별자는 다시 시작 사이에 동일한 장치에서만 고유합니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 및 열과 `DeviceName` 함께 `Timestamp` 사용해야 합니다. |
| `AppGuardContainerId` | 문자열 | Application Guard에서 브라우저 활동을 격리하기 위해 사용하는 가상화된 컨테이너의 식별자 |


## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
