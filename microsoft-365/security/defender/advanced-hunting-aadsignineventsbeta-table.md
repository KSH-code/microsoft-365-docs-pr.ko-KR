---
title: 고급 헌팅 스위마의 AADSignInEventsBeta 테이블
description: 고급 헌팅 Azure Active Directory 로그인 이벤트 테이블과 관련된 정보에 대해 자세히 알아보시고
keywords: 고급 헌팅, 위협 헌팅, 사이버 위협 헌팅, Microsoft 365 Defender, microsoft 365, m365, 검색, 쿼리, 원격 분석, schema 참조, kusto, 표, 열, 데이터 형식, 설명, 파일, IP 주소, 장치, 컴퓨터, 사용자, 계정, ID, AAD
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: d5e5ee451920f996dd3cc710cd6a0dbe9aaf3c50
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202682"
---
# <a name="aadsignineventsbeta"></a>AADSignInEventsBeta

**적용 대상:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 이 표는 현재 베타 버전이며 AAD(로그인 이벤트)를 Azure Active Directory 수 있도록 `AADSignInEventsBeta` 단기적으로 제공됩니다. 결국 모든 로그인 Schema 정보를 테이블로 `IdentityLogonEvents` 이동하게 됩니다.

고급 헌팅chema의 표에는 대화형 Azure Active Directory 비대화형 로그인에 대한 정보가 `AADSignInEventsBeta` 포함되어 있습니다. 자세한 내용은 Azure Active Directory 활동 보고서의 로그인 - 미리 [보기를 통해 자세히 알아보실 수 있습니다.](/azure/active-directory/reports-monitoring/concept-all-sign-ins)

이 참조를 사용하여 표의 정보를 반환하는 쿼리를 생성합니다. 고급 헌팅 스키마의 다른 표에 대한 자세한 내용은 [고급 헌팅 참조](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-reference)를 참조하세요.

<br>

****

|열 이름|데이터 형식|설명|
|---|---|---|
|`Timestamp`|datetime|레코드 생성 날짜 및 시간|
|`Application`|문자열|기록된 작업을 수행한 응용 프로그램|
|`ApplicationId`|문자열|응용 프로그램의 고유 식별자|
|`LogonType`|문자열|로그온 세션 유형, 특히 RDP(대화형, 원격 대화형), 네트워크, 일괄 처리 및 서비스|
|`ErrorCode`|int|로그인 오류가 발생하는 경우 오류 코드가 들어 있습니다. 특정 오류 코드에 대한 설명을 찾으면 을 <https://aka.ms/AADsigninsErrorCodes> 방문하세요.|
|`CorrelationId`|문자열|로그인 이벤트의 고유 식별자|
|`SessionId`|문자열|방문 또는 세션 기간 동안 웹 사이트 서버에 의해 사용자에게 할당된 고유 번호|
|`AccountDisplayName`|문자열|주소부에 표시된 계정 사용자의 이름입니다. 일반적으로 지정한 이름이나 이름, 중간 이니셜 및 성 또는 성의 조합입니다.|
|`AccountObjectId`|문자열|Azure AD에서 계정의 고유 식별자|
|`AccountUpn`|문자열|계정의 UPN(사용자 계정 이름)|
|`IsExternalUser`|int|로그인한 사용자가 외부에 있는지 나타냅니다. 가능한 값: -1(설정되지 않은 값), 0(외부 값), 1(외부)|
|`IsGuestUser`|부울|로그인한 사용자가 테넌트의 게스트인지 여부를 나타냅니다.|
|`AlternateSignInName`|문자열|Azure AD에 로그인하는 사용자의 UPN(사내 사용자 계정 이름)|
|`LastPasswordChangeTimestamp`|datetime|마지막으로 로그인한 사용자가 암호를 변경한 날짜 및 시간|
|`ResourceDisplayName`|문자열|액세스한 리소스의 표시 이름|
|`ResourceId`|문자열|액세스한 리소스의 고유 식별자|
|`ResourceTenantId`|문자열|액세스한 리소스의 테넌트의 고유 식별자입니다.|
|`DeviceName`|문자열|컴퓨터의 FQDN(정규화된 도메인 이름)|
|`AadDeviceId`|문자열|Azure AD에서 디바이스의 고유 식별자|
|`OSPlatform`|문자열|컴퓨터에서 실행 중인 운영 체제의 플랫폼 이는 Windows 11, Windows, Windows 10 및 Windows 7과 같은 특정 운영 체제를 나타냅니다.|
|`DeviceTrustType`|문자열|로그인한 장치의 트러스트 유형을 나타냅니다. 관리되는 장치 시나리오의 경우만 해당합니다. 가능한 값은 Workplace, AzureAd 및 ServerAd입니다.|
|`IsManaged`|int|로그인을 시작한 장치가 관리되는 장치(1)인지 아니면 관리되는 장치(0)가 아닌지 나타냅니다.|
|`IsCompliant`|int|로그인을 시작한 장치가 호환(1) 또는 비호응(0)하는지 나타냅니다.|
|`AuthenticationProcessingDetails`|문자열|인증 프로세서에 대한 세부 정보|
|`AuthenticationRequirement`|문자열|로그인에 필요한 인증 유형입니다. 가능한 값: multiFactorAuthentication(MFA 필요) 및 singleFactorAuthentication(MFA가 필요 없음)|
|`TokenIssuerType`|int|토큰 발급자에 Azure Active Directory (0) 또는 Active Directory Federation Services (1)|
|`RiskLevelAggregated`|int|로그인 중 집계된 위험 수준입니다. 가능한 값: 0(집계된 위험 수준이 설정되지 않은 경우), 1(없음), 10(낮음), 50(중간) 또는 100(높음)입니다.|
|`RiskDetails`|int|로그인한 사용자의 위험 상태 세부 정보|
|`RiskState`|int|위험한 사용자 상태를 나타냅니다. 가능한 값: 0(없음), 1(안전 확인), 2(수정), 3(해지), 4(위험) 또는 5(손상된 것으로 확인)|
|`UserAgent`|문자열|웹 브라우저 또는 기타 클라이언트 응용 프로그램의 사용자 에이전트 정보|
|`ClientAppUsed`|문자열|사용된 클라이언트 앱을 나타냅니다.|
|`Browser`|문자열|로그인하는 데 사용되는 브라우저 버전에 대한 세부 정보|
|`ConditionalAccessPolicies`|문자열|로그인 이벤트에 적용된 조건부 액세스 정책의 세부 정보|
|`ConditionalAccessStatus`|int|로그인에 적용된 조건부 액세스 정책의 상태입니다. 가능한 값은 0(정책 적용), 1(정책 적용 시도 실패) 또는 2(정책이 적용되지 않은 경우)입니다.|
|`IPAddress`|문자열|끝점에 할당되어 관련 네트워크 통신 중에 사용되는 IP 주소|
|`Country`|문자열|클라이언트 IP 주소가 지리적으로 위치가 지정되는 국가를 나타내는 두 글자 코드|
|`State`|문자열|로그인이 발생한 위치(사용 가능한 경우)|
|`City`|문자열|계정 사용자가 있는 구|
|`Latitude`|문자열|로그인 위치의 북-남 좌표|
|`Longitude`|문자열|로그인 위치의 동쪽에서 서 좌표까지|
|`NetworkLocationDetails`|문자열|로그인 이벤트의 인증 프로세서의 네트워크 위치 세부 정보|
|`RequestId`|문자열|요청의 고유 식별자|
|`ReportId`|문자열|이벤트의 고유 식별자|

## <a name="related-articles"></a>관련 문서

- [AADSpnSignInEventsBeta](./advanced-hunting-aadspnsignineventsbeta-table.md)
- [지능형 헌팅 개요](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)
- [쿼리 언어 배우기](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-query-language)
- [스키마의 이해](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-schema-reference)
