---
title: 고급 헌팅chema의 AADSpnSignInEventsBeta 테이블
description: Azure Active Directory 서비스 계정 및 관리되는 ID 로그인 이벤트 테이블과 관련된 정보에 대해 자세히 알아보십시오.
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 위협 방지, microsoft 365, mtp, m365, 검색, 쿼리, 원격 분석, 스마마 참조, kusto, 표, 열, 데이터 형식, 설명, AlertInfo, 경고, 엔터티, 증거, 파일, IP 주소, 장치, 컴퓨터, 사용자, 계정, ID, AAD
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
ms.openlocfilehash: 64f3e1d51f94c4cd2578a1d512115aa717c3eaa8
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071652"
---
# <a name="aadspnsignineventsbeta"></a>AADSpnSignInEventsBeta

**적용 대상:**

- Microsoft 365 Defender

>[!IMPORTANT]
> 이 표는 현재 베타 상태이며 AAD(Azure Active Directory) 서비스 사용자 및 관리되는 ID 로그인 이벤트를 검색할 수 있도록 단기적으로 `AADSpnSignInEventsBeta` 제공됩니다. 결국 모든 로그인 Schema 정보를 테이블로 `IdentityLogonEvents` 이동하게 됩니다.<br><br>
> Azure 보안 센터의 통합된 끝점용 Microsoft Defender 솔루션을 통해 Microsoft 365 Defender에 액세스할 수 있지만 Office용 Microsoft Defender, ID용 Microsoft Defender 또는 Microsoft Cloud App Security에 대한 라이선스가 없는 고객은 이 스마마를 볼 수 없습니다. 



고급 헌팅 schema의 표에는 Azure Active Directory 서비스 사용자 및 관리되는 ID 로그인에 대한 `AADSpnSignInEventsBeta` 정보가 포함되어 있습니다. Azure Active Directory 로그인 활동 보고서 - 미리 보기에서 다양한 종류의 로그인에 대해 자세히 [알아보십시오.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다.

고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)를 참조하세요.





| 열 이름     | 데이터 형식 | 설명   |
| ----- | ----- | ---- |
| `Timestamp` | datetime      | 레코드 생성 날짜 및 시간                                                                                                     |
| `Application`          | 문자열        | 기록된 작업을 수행한 응용 프로그램                                                                                                   |
| `ApplicationId`        | 문자열        | 응용 프로그램의 고유 식별자                                                                                                           |
| `IsManagedIdentity`    | 부울       | 관리되는 ID에서 로그인을 시작한지 여부를 나타냅니다.                                                                               |
| `ErrorCode`            | int        | 로그인 오류가 발생하는 경우 오류 코드가 들어 있습니다. 특정 오류 코드에 대한 설명을 찾으면 을 <https://aka.ms/AADsigninsErrorCodes> 방문하세요. |
| `CorrelationId`        | 문자열        | 로그인 이벤트의 고유 식별자                                                                                                          |
| `ServicePrincipalName` | 문자열        | 로그인을 시작한 서비스 사용자 이름입니다.                                                                                        |
| `ServicePrincipalId`   | 문자열        | 로그인을 시작한 서비스 계정의 고유 식별자입니다.                                                                           |
| `ResourceDisplayName`  | 문자열        | 액세스한 리소스의 표시 이름                                                                                                           |
| `ResourceId`           | 문자열        | 액세스한 리소스의 고유 식별자                                                                                                      |
| `ResourceTenantId`     | 문자열        | 액세스한 리소스의 테넌트의 고유 식별자입니다.                                                                                        |
| `IPAddress`            | 문자열        | 끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소                                                              |
| `Country`          | 문자열        | 클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드                                                                |
| `State`                | 문자열        | 로그인이 발생한 위치(사용 가능한 경우)                                                                                                  |
| `City`                 | 문자열        | 계정 사용자가 있는 구                                                                                                          |
| `Latitude`             | 문자열        | 로그인 위치의 북-남 좌표                                                                                          |
| `Longitude`            | 문자열        | 로그인 위치의 동쪽에서 서 좌표까지                                                                                            |
| `RequestId`            | 문자열        | 요청의 고유 식별자                                                                                                                |
|`ReportId` | 문자열 | 이벤트의 고유 식별자 | 

 

## <a name="related-articles"></a>관련 문서

-   [AADSignInEventsBeta](./advanced-hunting-aadsignineventsbeta-table.md)
-   [고급 헌팅 개요](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
-   [쿼리 언어 배우기](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
-   [스키마의 이해](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)