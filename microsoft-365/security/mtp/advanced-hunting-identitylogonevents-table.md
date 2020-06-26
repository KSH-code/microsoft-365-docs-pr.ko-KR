---
title: 고급 구하기 스키마의 IdentityLogonEvents 테이블
description: 고급 구하기 스키마의 IdentityLogonEvents 테이블에서 Active Directory가 기록한 인증 이벤트에 대해 자세히 알아보기
keywords: 고급 구하기, 위협 검색, 사이버 threat 사냥, microsoft threat protection, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스키마 참조, kusto, table, column, IdentityLogonEvents, Azure AD, Active Directory, Azure ATP, id
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
ms.openlocfilehash: 17e12e9095219b7ad7923f7b5664946fff6ce724
ms.sourcegitcommit: ab10c042e5e9c6a7b2afef930ab0d247a6aa275d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/26/2020
ms.locfileid: "44899378"
---
# <a name="identitylogonevents"></a>IdentityLogonEvents

**적용 대상:**
- Microsoft 위협 방지

`IdentityLogonEvents` [고급 구하기](advanced-hunting-overview.md) 스키마의 표에는 Azure Active Directory 및 기타 Microsoft 클라우드 앱 및 서비스에 의해 기록 되는 인증 작업에 대 한 정보가 포함 되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `ActionType` | 문자열 | 이벤트를 트리거한 작업의 유형입니다. |
| `LogonType` | 문자열 | 로그온 세션의 유형 (특히 다음과 같습니다.<br><br> - **대화형** -사용자가 로컬 키보드 및 화면을 사용 하 여 컴퓨터와 물리적으로 상호 작용 합니다.<br><br> - **RDP (원격 대화형) 로그온** -사용자가 원격 데스크톱, 터미널 서비스, 원격 지원 또는 기타 RDP 클라이언트를 사용 하 여 원격으로 컴퓨터와 상호 작용 합니다.<br><br> - PsExec를 사용 하 여 컴퓨터에 액세스 하거나 프린터 및 공유 폴더와 같은 컴퓨터의 공유 리소스에 액세스 하는 경우 **네트워크** 세션이 시작 됨<br><br> - 예약 된 작업에 의해 시작 되는 **일괄** 세션<br><br> - **서비스** 시작 시 서비스에 의해 시작 된 세션 |
| `Application` | 문자열 | 기록 된 작업을 수행한 응용 프로그램 |
| `Protocol` | 문자열 | 통신 중에 사용 되는 프로토콜 |
| `AccountName` | 문자열 | 계정의 사용자 이름입니다. |
| `AccountDomain` | 문자열 | 계정의 도메인 |
| `AccountUpn` | 문자열 | 계정의 UPN (사용자 계정 이름) |
| `AccountSid` | 문자열 | 계정의 SID (보안 식별자) |
| `AccountObjectId` | 문자열 | Azure AD의 계정에 대 한 고유 식별자입니다. |
| `AccountDisplayName` | 문자열 | 주소록에 표시 되는 계정 사용자의 이름입니다. 일반적으로 주어진 이름이 나 이름, 중간 시작, 성 또는 성의 조합입니다. |
| `DeviceName` | 문자열 | 컴퓨터의 FQDN(정규화된 도메인 이름) |
| `DeviceType` | 문자열 | 장치 유형 |
| `OSPlatform` | 문자열 | 컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 10 및 Windows 7과 같이 동일한 제품군 내의 변형을 포함하여 특정 운영 체제를 나타냅니다. |
| `IPAddress` | 문자열 | 끝점에 할당 되 고 관련 네트워크 통신 중에 사용 되는 IP 주소 |
| `Location` | 문자열 | 이벤트와 관련 된 구/군/시, 국가 또는 기타 지리적 위치 |
| `Isp` | 문자열 | 끝점 IP 주소와 연결 된 ISP (인터넷 서비스 공급자) |

## <a name="related-topics"></a>관련 항목
- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [여러 장치 및 전자 메일에서 위협을 탐지](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
