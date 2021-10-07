---
title: Microsoft 365 로드맵 - 최상위 우선 순위
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 08/20/2021
audience: Admin
ms.topic: conceptual
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: 보안 기능을 구현하여 보안 환경을 보호하기 위한 Microsoft 사이버 보안 팀의 Microsoft 365 권장 사항입니다.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7c3128482e9c8974ebb8938639ff3e27d400a418
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60176406"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>보안 로드맵 - 처음 30일, 90일 및 그 이상에 대한 최상위 우선 순위

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


이 문서에는 사용자 환경을 보호하기 위한 보안 기능을 구현하기 위한 Microsoft 사이버 보안 팀의 Microsoft 365 포함되어 있습니다. 이 문서는 사이버 보안 pro와 같은 보안 Microsoft 365: 처음 [30일, 90일](https://www.youtube.com/watch?v=luignzNyR-o)및 이후의 최상위 우선 순위와 같은 Microsoft Ignite 세션에서 조정됩니다. 이 세션은 사이버 보안 설계자인 Mark Simos와 Matt Kemelhar가 Enterprise 발표했습니다.

이 문서의 내용

- [로드맵 결과](security-roadmap.md#Roadmap)
- [30일 - 강력한 빠른 사용](security-roadmap.md#Thirdaydays)
- [90일 - 향상된 보호](security-roadmap.md#Ninetydays)
- [이후](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>로드맵 결과
<a name="Roadmap"> </a>

이러한 로드맵 권장 사항은 다음과 같은 목표를 가지는 논리적 순서로 세 단계로 구성됩니다.

****

|시간 프레임|성과|
|---|---|
|30일|신속한 구성: <ul><li>기본 관리자 보호.</li><li>로깅 및 분석.</li><li>기본 ID 보호.</li></ul> <p> 테넌트 구성. <p> 관련자를 준비합니다.|
|90일|고급 보호: <ul><li>관리자 계정.</li><li>데이터 및 사용자 계정.</li></ul> <p> 규정 준수, 위협 및 사용자 요구에 대한 가시성 <p> 기본 정책 및 보호를 조정하고 구현합니다.|
|이후|주요 정책 및 컨트롤을 조정하고 구체화합니다. <p> 보호를 사내 종속성으로 확장합니다. <p> 비즈니스 및 보안 프로세스(법률, 내부자 위협 등)와 통합합니다.|
|

## <a name="30-days--powerful-quick-wins"></a>30일 - 강력한 빠른 사용
<a name="Thirdaydays"> </a>

이러한 태스크는 빠르게 완료될 수 있으며 사용자에게 많은 영향을 미치지 않습니다.

****

|영역|작업|
|---|---|
|보안 관리|<ul><li>보안 점수를 확인하고 현재 점수()를 기록해 <https://security.microsoft.com/securescore> 넣습니다.</li><li>사용자에 대한 감사 로깅을 Office 365. 감사 [로그 검색을 참조합니다.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[보안 Microsoft 365 구성합니다.](tenant-wide-setup-for-increased-security.md)</li><li>Microsoft 365 Defender 포털에서 대시보드 및 보고서를 Cloud App Security.</li></ul>|
|위협 방지|[커넥트 Microsoft 365 Microsoft Cloud App Security](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 기본 위협 감지 정책을 사용하여 모니터링을 시작할 수 있습니다. 이상 검색을 위한 기준을 작성하는 데 7일이 소요됩니다. <p>  관리자 계정에 대한 보호를 구현합니다.<ul><li>관리자 활동에 전용 관리자 계정을 사용하세요.</li><li>관리자 계정에 대해 MFA(다단계 인증)를 적용합니다.</li><li>관리자 [활동에는 Windows 보안이](/windows-hardware/design/device-experiences/oem-highly-secure) 유지되는 디바이스를 사용합니다.</li></ul>|
|ID 및 액세스 관리|<ul><li>[ID Azure Active Directory 사용.](/azure/active-directory/active-directory-identityprotection-enable)</li><li>페더전된 ID 환경의 경우 계정 보안(암호 길이, 기간, 복잡성 등)을 적용합니다.</li></ul>|
|정보 보호|예제 정보 보호 권장 사항을 검토합니다. 정보 보호를 위해서는 조직 전체에서 조율해야 합니다. 다음 리소스를 사용해서 시작하세요.<ul><li>[GDPR에 대한 Office 365 정보 보호](/compliance/regulatory/gdpr)</li><li>[3계층](../../solutions/configure-teams-three-tiers-protection.md) Teams(공유, 분류, 데이터 손실 방지 및 Azure Information Protection 포함) 구성</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90일 - 향상된 보호
<a name="Ninetydays"> </a>

이러한 태스크는 계획하고 구현하는 데 다소 시간이 소요되지만 보안 태세를 갖추는 데 큰 도움이 됩니다.

****

|영역|작업|
|---|---|
|보안 관리|<ul><li>보안 점수를 확인하여 환경에 권장되는 작업()을 확인할 수 <https://security.microsoft.com/securescore> 있습니다.</li><li>Microsoft 365 Defender 포털, Cloud App Security SIEM 도구에서 대시보드 및 보고서를 정기적으로 검토합니다.</li><li>소프트웨어 업데이트를 찾아 구현합니다.</li><li>공격 시뮬레이션 교육(위협 인텔리전스에 포함)을 사용하여 스피어 [피싱,](office-365-ti.md)암호 분사 및 무차별 암호 대시(brute-force) 공격에 대한 공격 시뮬레이션을 Office 365 합니다. [](attack-simulation-training.md)</li><li>조사 탭의 Cloud App Security 기본 제공 보고서를 검토하여 공유 위험을 찾아야 합니다.</li><li>준수 [관리자를](../../compliance/compliance-manager.md) 확인하여 조직에 적용되는 규정의 상태(예: GDPR, NIST 800-171)를 검토합니다.</li></ul>|
|위협 방지|관리자 계정에 대한 향상된 보호를 구현합니다. <ul><li>관리자 활동에 대해 PAW(Privileged [Access Workstation)를](/security/compass/privileged-access-devices) 구성합니다.</li><li>[Azure AD Privileged Identity Management](/azure/active-directory/active-directory-privileged-identity-management-configure)구성합니다.</li><li>AD FS를 비롯한 Office 365, Cloud App Security 서비스에서 로깅 데이터를 수집하도록 SIEM(보안 정보 및 이벤트 관리) 도구를 구성합니다. 감사 로그는 90일 동안만 데이터를 저장합니다. SIEM 도구에서 이 데이터를 캡처하면 데이터를 더 오랫동안 저장할 수 있습니다.</li></ul>|
|ID 및 액세스 관리|<ul><li>모든 사용자에 대해 MFA를 사용하도록 설정하고 적용합니다.</li><li>조건부 액세스 [및 관련 정책 집합을 구현합니다.](microsoft-365-policies-configurations.md)</li></ul>|
|정보 보호| 정보 보호 정책을 조정하고 구현합니다. 이러한 리소스에는 예제가 포함됩니다. <ul><li>[GDPR에 대한 Office 365 정보 보호](/compliance/regulatory/gdpr)</li><li>[3 계층 보안으로 Teams 구성](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> 데이터 손실 방지 정책 및 모니터링 도구는 Microsoft 365 대신 Microsoft 365 데이터를 Cloud App Security. <p> 데이터 Cloud App Security 외의 Microsoft 365 기능을 사용할 수 있습니다.|
|

## <a name="beyond"></a>이후
<a name="Beyond"> </a>

이러한 조치는 이전 작업을 구축하는 중요한 보안 조치입니다.

****

|영역|작업|
|---|---|
|보안 관리|<ul><li>보안 점수( )를 사용하여 다음 작업을 계속 <https://security.microsoft.com/securescore> 계획합니다.</li><li>Microsoft 365 Defender 포털, Cloud App Security SIEM 도구에서 대시보드 및 보고서를 정기적으로 검토합니다.</li><li>소프트웨어 업데이트를 계속 찾아 구현합니다.</li><li>eDiscovery를 법적 및 위협 대응 프로세스에 통합합니다.</li></ul>|
|위협 방지|<ul><li>ID 구성 요소에 대한 [SPA(Secure Privileged](/windows-server/identity/securing-privileged-access/securing-privileged-access) Access)를 사내(AD, AD FS)에 구현합니다.</li><li>내부자 Cloud App Security 모니터링할 수 있습니다.</li><li>섀도 IT SaaS 사용을 검색하여 Cloud App Security.</li></ul>|
|ID 및 액세스 관리|<ul><li>정책 및 운영 프로세스를 구체화합니다.</li><li>Azure AD ID 보호를 사용하여 내부자 위협을 식별합니다.</li></ul>|
|정보 보호|정보 보호 정책을 구체화합니다. <ul><li>Microsoft 365 Office 365 및 DLP(데이터 손실 방지) 또는 Azure Information Protection에 대한 정보를 제공합니다.</li><li>Cloud App Security 및 경고를 생성합니다.</li></ul>|
|

또한 페티야 및 WannaCrypt와 같은 신속한 사이버 공격을 [완화하는 방법도 참조합니다.](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)
