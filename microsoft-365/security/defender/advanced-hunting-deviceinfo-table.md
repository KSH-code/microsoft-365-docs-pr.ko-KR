---
title: 고급 헌팅Chema의 DeviceInfo 테이블
description: 고급 헌팅 schema의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 컴퓨터 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, machineinfo, DeviceInfo, 장치, 컴퓨터, OS, 플랫폼, 사용자
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
ms.openlocfilehash: 25cf4f098d1dd58e86583be17ccbd371a16b128d
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/02/2021
ms.locfileid: "60643182"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender
- 끝점용 Microsoft Defender



고급 `DeviceInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 비롯한 조직의 장치에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 시스템의 고유 식별자 |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `ClientVersion` | 문자열 | 기기에서 실행되는 끝점 에이전트 또는 센서의 버전 |
| `PublicIP` | 문자열 | 등록된 컴퓨터에 의해 끝점용 Microsoft Defender 서비스에 연결하는 데 사용되는 공용 IP 주소입니다. 컴퓨터 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다. |
| `OSArchitecture` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 아키텍처 |
| `OSPlatform` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 11, Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSBuild` | 문자열 | 시스템에서 실행되는 운영 체제의 빌드 버전 |
| `IsAzureADJoined` | 부울 | 컴퓨터의 가입 여부를 나타내는 부울 표시기입니다Azure Active Directory |
| `AadObjectId` | 문자열 | Azure AD에서 디바이스의 고유 식별자 |
| `LoggedOnUsers` | 문자열 | 이벤트 당시 컴퓨터에 로그온한 모든 사용자 목록(JSON 배열 형식)입니다. |
| `RegistryDeviceTag` | 문자열 | 레지스트리를 통해 추가된 컴퓨터 태그 |
| `OSVersion` | 문자열 | 컴퓨터에서 실행 중인 운영 체제 버전 |
| `MachineGroup` | 문자열 | 컴퓨터의 컴퓨터 그룹입니다. 이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다. |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |
| `OnboardingStatus` | 문자열 | 디바이스가 현재 Microsoft Defender For Endpoint에 온보딩 상태인지 또는 디바이스가 지원되지 않는지 여부를 나타냅니다. |
|`AdditionalFields` | 문자열 | JSON 배열 형식의 이벤트에 대한 추가 정보 |
|`DeviceCategory` | 문자열 | 끝점, 네트워크 장치, IoT, 알 수 없음 범주의 특정 장치 유형을 그룹화하는 더 광범위한 분류 |
|`DeviceType` | 문자열 | 네트워크 장치, Workstation, 서버, 모바일, 게임 콘솔 또는 프린터와 같은 용도 및 기능을 기반으로 하는 장치 유형 |
|`DeviceSubType` | 문자열 | 특정 유형의 장치에 대한 추가 수정자(예: 모바일 장치는 태블릿 또는 스마트폰일 수 있습니다)입니다. |
|`Model` | 문자열 | 공급업체 또는 제조업체의 모델 이름 또는 제품 번호 |
|`Vendor` | 문자열 | 제품 공급업체 또는 제조업체의 이름 |
|`OSDistribution` | 문자열 | Linux 플랫폼용 Ubuntu 또는 RedHat와 같은 OS 플랫폼 배포 |
|`OSVersionInfo` | 문자열 | 인기 있는 이름, 코드 이름 또는 버전 번호와 같은 OS 버전에 대한 추가 정보 |
|`MergedDeviceIds` | 문자열 | 동일한 장치에 할당된 이전 장치 ID |
|`MergedToDeviceId` | 문자열 | 장치에 할당된 최신 장치 ID입니다. |

이 표에서는 장치의 주기적인 보고서 또는 신호인 하트비트 기반 장치 `DeviceInfo` 정보를 제공합니다. 15분마다 장치는 처럼 자주 변경되는 특성을 포함하는 부분 하트비트를 `LoggedOnUsers` 전송합니다. 하루 중 한 번 장치의 특성을 포함하는 전체 하트비트가 전송됩니다.

다음 샘플 쿼리를 사용하여 장치의 최신 상태를 얻을 수 있습니다.

```kusto
// Get latest information on user/device
DeviceInfo
| where DeviceName == "example" and isnotempty(OSPlatform)
| summarize arg_max(Timestamp, *) by DeviceId 
```

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
