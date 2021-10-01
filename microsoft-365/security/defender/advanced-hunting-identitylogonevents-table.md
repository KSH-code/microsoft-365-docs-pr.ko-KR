---
title: 고급 헌팅Chema의 IdentityLogonEvents 테이블
description: 고급 헌팅 구조의 IdentityLogonEvents 표에서 Active Directory에서 기록하는 인증 이벤트에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, IdentityLogonEvents, Azure AD, Active Directory, ID용 Microsoft Defender, ID
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
ms.openlocfilehash: 8894e30f013e89110478000372c2b24c44c1f183
ms.sourcegitcommit: e5de03d4bd669945fec0d25a3f5eae56f86c9dcc
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/01/2021
ms.locfileid: "60042713"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**적용 대상:**
- Microsoft 365 Defender

고급 헌팅 계획의 표에는 ID에 대한 Microsoft Defender에서 캡처한 사내 Active Directory를 통한 인증 활동 및 사용자 계정에서 캡처한 Microsoft 온라인 서비스와 관련된 인증 활동에 대한 `IdentityLogonEvents` Microsoft Cloud App Security. [](advanced-hunting-overview.md) 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` Schema 참조를 사용합니다.

>[!NOTE]
>이 표에서는 Azure Active Directory(Azure AD) 로그온 활동, 특히 ActiveSync 및 기타 레거시 프로토콜을 Cloud App Security 대화형 로그인 및 인증 활동에 대해 설명합니다. 이 표에서 사용할 수 없는 비대화형 로그온은 Azure AD 감사 로그에서 볼 수 있습니다. [자세한 내용은 Cloud App Security 연결 Microsoft 365](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security)

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 활동의 유형입니다. 자세한 내용은 포털 내 [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 참조합니다. |
| `Application` | 문자열 | 기록된 작업을 수행한 응용 프로그램 |
| `LogonType` | 문자열 | 로그온 세션의 유형, 특히 다음과 같습니다.<br><br> - **대화형** - 사용자가 로컬 키보드 및 화면을 사용하여 컴퓨터와 물리적으로 상호 작용합니다.<br><br> - **RDP(원격 대화형) 로그널** - 사용자가 원격 데스크톱, 터미널 서비스, 원격 지원 또는 기타 RDP 클라이언트를 사용하여 원격으로 컴퓨터와 상호 작용합니다.<br><br> - **네트워크** - PsExec을 사용하여 컴퓨터 액세스 또는 컴퓨터의 공유 리소스(예: 프린터 및 공유 폴더)에 액세스할 때 시작된 세션<br><br> - **Batch** - 예약된 작업으로 시작된 세션<br><br> - **서비스** - 서비스가 시작할 때 시작된 세션 |
| `Protocol` | 문자열 | 사용된 네트워크 프로토콜 |
| `FailureReason` | 문자열 | 기록된 작업이 실패한 이유를 설명하는 정보 |
| `AccountName` | 문자열 | 계정의 사용자 이름 |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN(사용자 계정 이름) |
| `AccountSid` | 문자열 | 계정의 SID(보안 식별자)입니다. |
| `AccountObjectId` | 문자열 | Azure AD에서 계정의 고유 식별자 |
| `AccountDisplayName` | 문자열 | 주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 장치의 FQDN(FQDN) |
| `DeviceType` | 문자열 | 디바이스 유형 |
| `OSPlatform` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 11, Windows, Windows 10 및 Windows 7과 같은 특정 운영 체제를 나타냅니다. |
| `IPAddress` | 문자열 | 끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소 |
| `Port` | 문자열 | 통신 중에 사용되는 TCP 포트 |
| `DestinationDeviceName` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 이름입니다. |
| `DestinationIPAddress` | 문자열 | 기록된 작업을 처리한 서버 응용 프로그램을 실행하는 장치의 IP 주소 |
| `DestinationPort` | 문자열 | 관련 네트워크 통신의 대상 포트 |
| `TargetDeviceName` | 문자열 | 기록된 작업이 적용된 장치의 FQDN(FQDN) |
| `TargetAccountDisplayName` | 문자열 | 기록된 작업이 적용된 계정의 표시 이름 |
| `Location` | 문자열 | 이벤트와 관련된 도시, 국가 또는 기타 지리적 위치 |
| `Isp` | 문자열 | 끝점 IP 주소와 연결된 ISP(인터넷 서비스 공급자) |
| `ReportId` | long | 이벤트의 고유 식별자 |
| `AdditionalFields` | 문자열 | 엔터티 또는 이벤트에 대한 추가 정보 |

## <a name="related-topics"></a>관련 항목
- [지능형 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)