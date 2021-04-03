---
title: 고급 헌팅Chema의 DeviceInfo 테이블
description: 고급 헌팅 schema의 DeviceInfo 표에서 OS, 컴퓨터 이름 및 기타 장치 정보에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, deviceinfo, 장치, OS, 플랫폼, 사용자, DeviceInfo
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
ms.openlocfilehash: e6a11af94a5d2b2099d14b660cf65c846532ebd1
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500828"
---
# <a name="deviceinfo"></a>DeviceInfo

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**적용 대상:**
- [엔드포인트용 Microsoft Defender](https://go.microsoft.com/fwlink/p/?linkid=2154037)


>Endpoint용 Defender를 경험하고 싶나요? [무료 평가판에 등록합니다.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

고급 `DeviceInfo` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 OS 버전, 활성 사용자 및 컴퓨터 이름을 포함하여 조직의 장치에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스마의 다른 표에 대한 자세한 내용은 고급 헌팅 스마 [참조 를 참조하세요.](advanced-hunting-schema-reference.md)

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `DeviceId` | 문자열 | 서비스에서 디바이스의 고유 식별자 |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `ClientVersion` | 문자열 | 디바이스에서 실행되는 끝점 에이전트 또는 센서의 버전 |
| `PublicIP` | 문자열 | 등록된 장치에서 끝점용 Defender 서비스에 연결하는 데 사용하는 공용 IP 주소입니다. 장치 자체의 IP 주소, NAT 장치 또는 프록시일 수 있습니다. |
| `OSArchitecture` | 문자열 | 장치에서 실행되는 운영 체제의 아키텍처 |
| `OSPlatform` | 문자열 | 디바이스에서 실행되는 운영 체제의 플랫폼입니다. 이는 Windows 10 및 Windows 7과 같은 동일한 패밀리 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `OSBuild` | 문자열 | 디바이스에서 실행되는 운영 체제의 빌드 버전 |
| `IsAzureADJoined` | 부울 | 디바이스가 Azure Active Directory에 가입된지 여부를 나타내는 부울 표시기입니다. |
| `LoggedOnUsers` | 문자열 | 이벤트 당시 디바이스에 로그온된 모든 사용자 목록(JSON 배열 형식)입니다. |
| `RegistryDeviceTag` | 문자열 | 레지스트리를 통해 추가된 장치 태그 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |
| `OSVersion` | 문자열 | 장치에서 실행되는 운영 체제 버전 |
| `MachineGroup` | 문자열 | 컴퓨터의 컴퓨터 그룹입니다. 이 그룹은 역할 기반 액세스 제어에서 컴퓨터 액세스 확인에 사용됩니다. |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [스키마의 이해](advanced-hunting-schema-reference.md)
