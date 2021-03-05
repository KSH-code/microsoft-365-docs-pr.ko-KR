---
title: 고급 헌팅 스키마의 EmailEvents 표
description: 고급 헌팅 스위마의 EmailEvents 표에서 Microsoft 365 전자 메일과 관련된 이벤트에 대해 자세히 알아보기
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, schema reference, kusto, table, column, data type, description, EmailEvents, network message id, sender, recipient, attachment id, attachment name, malwaredict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: a0892e03e0ac4c6fc6bcda1b7b159ce403a7ce2e
ms.sourcegitcommit: a7d1b29a024b942c7d0d8f5fb9b5bb98a0036b68
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/05/2021
ms.locfileid: "50461623"
---
# <a name="emailevents"></a>EmailEvents

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**적용 대상:**

- Microsoft 365 Defender

고급 `EmailEvents` 헌팅 [schema의](advanced-hunting-overview.md) 표에는 Office 365용 Microsoft Defender에서 전자 메일 처리와 관련된 이벤트에 대한 정보가 포함되어 있습니다. 이 참조를 사용하여 이 표의 정보를 반환하는 쿼리를 생성합니다.

>[!TIP]
> 테이블에서 지원하는 이벤트 유형(값)에 대한 자세한 내용은 보안 센터에서 사용할 수 있는 기본 제공 `ActionType` [Schema 참조를](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) 사용합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](advanced-hunting-schema-tables.md)를 참조하세요.

| 열 이름 | 데이터 형식 | 설명 |
|-------------|-----------|-------------|
| `Timestamp` | datetime | 이벤트가 기록된 날짜와 시간 |
| `NetworkMessageId` | 문자열 | Microsoft 365에서 생성되는 전자 메일의 고유 식별자 |
| `InternetMessageId` | 문자열 | 보내는 전자 메일 시스템에서 설정한 전자 메일의 공개 식별자 |
| `SenderMailFromAddress` | 문자열 | 보낸 사람 머리글의 보낸 사람 전자 메일 주소(봉투의 보낸 사람 또는 반송 경로 주소라고도 함) |
| `SenderFromAddress` | 문자열 | 전자 메일 클라이언트의 전자 메일 수신자에게 표시되는 FROM 머리글의 발신자 전자 메일 주소  |
| `SenderDisplayName` | 문자열 | 주소장에 표시되는 보낸 사람 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 이니셜 및 성 또는 성의 조합입니다. |
| `SenderObjectId` | 문자열 |Azure AD에서 보낸 사람 계정의 고유 식별자 |
| `SenderMailFromDomain` | 문자열 | 보낸 사람 머리글의 보낸 사람 도메인(봉투의 보낸 사람 또는 반송 경로 주소라고도 함) |
| `SenderFromDomain` | 문자열 | 전자 메일 클라이언트의 전자 메일 수신자에게 표시되는 FROM 머리글의 발신자 도메인 |
| `SenderIPv4` | 문자열 | 메시지를 전달한 마지막 검색 메일 서버의 IPv4 주소 |
| `SenderIPv6` | 문자열 | 메시지를 전달한 마지막 검색 메일 서버의 IPv6 주소 |
| `RecipientEmailAddress` | 문자열 | 받는 사람의 전자 메일 주소 또는 메일 그룹 확장 후 받는 사람의 전자 메일 주소 |
| `RecipientObjectId` | 문자열 | Azure AD에서 전자 메일 받는 사람의 고유 식별자 |
| `Subject` | 문자열 | 전자 메일 제목 |
| `EmailClusterId` | 문자열 | 콘텐츠의 휴리스틱 분석을 기반으로 클러스터된 비슷한 전자 메일 그룹의 식별자 |
| `EmailDirection` | 문자열 | 사용자 네트워크와 관련된 전자 메일의 방향: 인바운드, 아웃 바운드, 조직 내 |
| `DeliveryAction` | 문자열 | 전자 메일 전송 작업: 전달됨, 정크 메일함으로 전송됨, 차단됨 또는 대체됨 |
| `DeliveryLocation` | 문자열 | 전자 메일이 전송된 위치: 받은 편지함/폴더, 온-프레미스/외부, 정크, 격리, 실패, 중단, 삭제된 항목 |
| `ThreatTypes` | 문자열 | 전자 메일에 맬웨어, 피싱 또는 기타 위협이 포함되어 있는지 여부에 대한 전자 메일 필터링 스택의 판정 |
| `ThreatNames` | 문자열 |맬웨어 또는 기타 위협이 발견된 검색 이름 |
| `DetectionMethods` | 문자열 | 전자 메일에 있는 맬웨어, 피싱 또는 기타 위협을 감지하는 데 사용되는 방법 |
| `ConfidenceLevel` | 문자열 | 스팸 또는 피싱 판정의 신뢰 수준 목록입니다. 스팸의 경우 이 열은 전자 메일을 건너뛴 경우(-1), 스팸이 아닌 것으로 확인(0,1), 보통 신뢰도(5,6) 또는 스팸 지수(9)로 확인되었음을 나타내는 SCL(스팸 지수)을 보여줍니다. 피싱의 경우 이 열에는 신뢰 수준이 "높음" 또는 "낮음"인지 표시됩니다. |
| `EmailAction` | 문자열 | 필터 판정, 정책 및 사용자 작업에 기반하여 전자 메일에 대해 수행된 마지막 작업: 메시지를 정크 메일 폴더로 이동, X 머리글을 추가, 제목을 수정, 메시지를 리디렉션, 메시지를 삭제, 검역소로 전송, 작업 없음, Bcc 메시지 |
| `EmailActionPolicy` | 문자열 | 적용된 작업 정책: 스팸 방지 높은 신뢰감, 스팸 방지, 스팸 방지 대량 메일, 스팸 방지 피싱, 피싱 방지 도메인 가장, 피싱 방지 사용자 가장, 피싱 방지 스푸핑, 피싱 방지 그래프 가장, 멜웨어 방지, 안전 첨부 파일, 엔터프라이즈 전송 규칙(ETR) |
| `EmailActionPolicyGuid` | 문자열 | 마지막 메일 작업을 결정한 정책의 고유 식별자 |
| `AttachmentCount` | int | 전자 메일의 첨부 파일 수 |
| `UrlCount` | int | 전자 메일에 포함된 URL의 수 |
| `EmailLanguage` | 문자열 | 검색된 전자 메일 콘텐츠의 언어 |
| `Connectors` | 문자열 | 조직 메일 흐름 및 전자 메일 라우팅 방법을 정의하는 사용자 지정 지침 |
| `OrgLevelAction` | 문자열 | 조직 수준에서 정의된 정책에 대한 일치에 대한 응답으로 전자 메일에 수행된 작업 |
| `OrgLevelPolicy` | 문자열 | 전자 메일에 수행된 작업을 트리거한 조직 정책 |
| `UserLevelAction` | 문자열 | 받는 사람이 정의한 사서함 정책에 대한 일치에 대한 응답으로 전자 메일에 대해 수행된 작업 |
| `UserLevelPolicy` | 문자열 | 전자 메일에 수행된 작업을 트리거한 최종 사용자 사서함 정책 |
| `ReportId` | long | 반복 카운터를 기반으로 하는 이벤트 식별자입니다. 고유한 이벤트를 식별하려면 이 열을 DeviceName 및 Timestamp 열과 함께 사용해야 합니다. |

## <a name="related-topics"></a>관련 항목

- [고급 헌팅 개요](advanced-hunting-overview.md)
- [쿼리 언어 배우기](advanced-hunting-query-language.md)
- [공유 쿼리 사용](advanced-hunting-shared-queries.md)
- [장치, 전자 메일, 앱 및 ID를 검색합니다.](advanced-hunting-query-emails-devices.md)
- [스키마의 이해](advanced-hunting-schema-tables.md)
- [쿼리 모범 사례 적용](advanced-hunting-best-practices.md)
