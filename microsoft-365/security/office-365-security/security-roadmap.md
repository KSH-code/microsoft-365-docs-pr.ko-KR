---
title: Microsoft 365 보안 로드맵 - 최상위 우선 순위
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/08/2018
audience: Admin
ms.topic: conceptual
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MET150
ms.assetid: 28c86a1c-e4dd-4aad-a2a6-c768a21cb352
description: Microsoft 365 환경을 보호하기 위한 보안 기능을 구현하기 위한 Microsoft 사이버 보안 팀의 주요 권장 사항
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a7d376eb7266975dc7582b83bfd4fa5e930ccea4
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288172"
---
# <a name="security-roadmap---top-priorities-for-the-first-30-days-90-days-and-beyond"></a>보안 로드맵 - 처음 30일, 90일 및 그 이상에 대한 최상위 우선 순위

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


이 문서에는 Microsoft 365 환경을 보호하기 위한 보안 기능을 구현하기 위한 Microsoft 사이버 보안 팀의 주요 권장 사항이 포함되어 있습니다. 이 문서는 사이버 보안 pro와 같은 Microsoft 365 보안과 같은 Microsoft Ignite 세션에서 조정됩니다. 처음 [30일, 90일](https://www.youtube.com/watch?v=luignzNyR-o)및 그 이상에 대한 최고 우선 순위입니다. 이 세션은 엔터프라이즈 사이버 보안 설계자인 Mark Simos와 Matt Kemelhar가 개발하고 발표했습니다.

이 문서의 내용

- [로드맵 결과](security-roadmap.md#Roadmap)
- [30일 - 강력한 빠른 사용](security-roadmap.md#Thirdaydays)
- [90일 - 향상된 보호](security-roadmap.md#Ninetydays)
- [이후](security-roadmap.md#Beyond)

## <a name="roadmap-outcomes"></a>로드맵 결과
<a name="Roadmap"> </a>

이러한 로드맵 권장 사항은 다음 목표를 통해 논리적 순서로 세 단계로 구성됩니다.

****

|시간 프레임|결과|
|---|---|
|30일|신속한 구성: <ul><li>기본 관리자 보호.</li><li>로깅 및 분석.</li><li>기본 ID 보호.</li></ul> <p> 테넌트 구성. <p> 관련자를 준비합니다.|
|90일|고급 보호: <ul><li>관리자 계정.</li><li>데이터 및 사용자 계정.</li></ul> <p> 규정 준수, 위협 및 사용자 요구에 대한 가시성 <p> 기본 정책 및 보호를 조정하고 구현합니다.|
|이후|주요 정책 및 컨트롤을 조정하고 구체화합니다. <p> 보호를 On-프레미스 종속성으로 확장합니다. <p> 비즈니스 및 보안 프로세스(법적, 내부자 위협 등)와 통합합니다.|
|

## <a name="30-days--powerful-quick-wins"></a>30일 - 강력한 빠른 사용
<a name="Thirdaydays"> </a>

이러한 태스크는 빠르게 완료될 수 있으며 사용자에게 많은 영향을 미치지 않습니다.

****

|영역|작업|
|---|---|
|보안 관리|<ul><li>보안 점수를 확인하고 현재 점수()를 기록해 <https://securescore.office.com> 넣습니다.</li><li>Office 365에 대한 감사 로깅을 켜야 합니다. 감사 [로그 검색을 참조합니다.](../../compliance/search-the-audit-log-in-security-and-compliance.md)</li><li>[보안 강화를 위해 Microsoft 365를 구성합니다.](tenant-wide-setup-for-increased-security.md)</li><li>Microsoft 365 보안 센터 및 Cloud App Security에서 대시보드 및 보고서를 정기적으로 검토합니다.</li></ul>|
|위협 방지|[Microsoft 365를 Microsoft Cloud App Security에](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 연결하여 이상 동작에 대한 기본 위협 감지 정책을 사용하여 모니터링을 시작하세요. 이상 검색에 대한 기준을 작성하는 데 7일이 소요됩니다. <p>  관리자 계정에 대한 보호를 구현합니다.<ul><li>관리자 활동에 전용 관리자 계정을 사용하세요.</li><li>관리자 계정에 대해 MFA(다단계 인증)를 적용합니다.</li><li>관리자 [활동에는 보안이 높은 Windows 10](https://docs.microsoft.com/windows-hardware/design/device-experiences/oem-highly-secure) 장치를 사용합니다.</li></ul>|
|ID 및 액세스 관리|<ul><li>[Azure Active Directory ID 보호를 사용하도록 설정.](https://docs.microsoft.com/azure/active-directory/active-directory-identityprotection-enable)</li><li>페더임 ID 환경의 경우 계정 보안(암호 길이, 기간, 복잡성 등)을 적용합니다.</li></ul>|
|정보 보호|정보 보호 권장 사항 예제를 검토합니다. 정보 보호를 위해서는 조직 전체의 조율이 필요합니다. 다음 리소스를 사용해서 시작하세요.<ul><li>[GDPR에 대한 Office 365 정보 보호](https://aka.ms/o365gdpr)</li><li>[3계층 보호로 Teams](../../solutions/configure-teams-three-tiers-protection.md) 구성(공유, 분류, 데이터 손실 방지 및 Azure Information Protection 포함)</li></ul>|
|

## <a name="90-days--enhanced-protections"></a>90일 - 향상된 보호
<a name="Ninetydays"> </a>

이러한 태스크는 계획하고 구현하는 데 다소 시간이 소요되지만 보안 태세를 갖추는 데 큰 도움이 됩니다.

****

|영역|작업 |
|---|---|
|보안 관리|<ul><li>보안 점수에서 작업 환경에 권장되는 작업()을 확인 <https://securescore.office.com> 합니다.</li><li>Microsoft 365 보안 센터, Cloud App Security 및 SIEM 도구에서 대시보드 및 보고서를 정기적으로 검토합니다.</li><li>소프트웨어 업데이트를 찾아 구현합니다.</li><li>공격 시뮬레이터(Office 365 위협 인텔리전스에 포함)를 사용하여 [](attack-simulator.md) 스피어 피싱, 암호 분사 및 무차별 암호 대시 공격에 대한 공격 [시뮬레이션을 실시합니다.](office-365-ti.md)</li><li>Cloud App Security(조사 탭)에서 기본 제공 보고서를 검토하여 공유 위험을 찾아 봐야 합니다.</li><li>준수 [관리자를](../../compliance/compliance-manager.md) 확인하여 조직에 적용되는 규정(예: GDPR, NIST 800-171)에 대한 상태를 검토합니다.</li></ul>|
|위협 방지|관리자 계정에 대한 향상된 보호를 구현합니다. <ul><li>관리자 활동에 대해 PAW(Privileged [Access Workstations)를](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) 구성합니다.</li><li>[Azure AD Privileged Identity Management를 구성합니다.](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)</li><li>Office 365, Cloud App Security 및 AD FS를 비롯한 기타 서비스에서 로깅 데이터를 수집하도록 SIEM(보안 정보 및 이벤트 관리) 도구를 구성합니다. 감사 로그는 90일 동안만 데이터를 저장합니다. SIEM 도구에서 이 데이터를 캡처하면 데이터를 더 오랫동안 저장할 수 있습니다.</li></ul>|
|ID 및 액세스 관리|<ul><li>모든 사용자에 대해 MFA를 사용하도록 설정하고 적용합니다.</li><li>조건부 액세스 [및 관련 정책 집합을 구현합니다.](microsoft-365-policies-configurations.md)</li></ul>|
|정보 보호| 정보 보호 정책을 조정하고 구현합니다. 이러한 리소스에는 예제가 포함됩니다. <ul><li>[GDPR에 대한 Office 365 정보 보호](https://aka.ms/o365gdpr)</li><li>[세 가지 보호 계층으로 Teams 구성](../../solutions/configure-teams-three-tiers-protection.md)</li></ul> <p> Cloud App Security 대신 Microsoft 365에 저장된 데이터에 대해 Microsoft 365의 데이터 손실 방지 정책 및 모니터링 도구를 사용합니다. <p> Microsoft 365와 함께 Cloud App Security를 사용하여 고급 경고 기능(데이터 손실 방지 외)을 사용할 수 있습니다.|
|

## <a name="beyond"></a>이후
<a name="Beyond"> </a>

이러한 조치는 이전 작업을 구축하는 중요한 보안 조치입니다.

****

|영역|작업 |
|---|---|
|보안 관리|<ul><li>보안 점수()를 사용하여 다음 작업을 계속 <https://securescore.office.com> 계획합니다.</li><li>Microsoft 365 보안 센터, Cloud App Security 및 SIEM 도구에서 대시보드 및 보고서를 정기적으로 검토합니다.</li><li>소프트웨어 업데이트를 계속 찾아 구현합니다.</li><li>eDiscovery를 법적 및 위협 대응 프로세스에 통합합니다.</li></ul>|
|위협 방지|<ul><li>ID [구성 요소에](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access) 대해 AD, AD FS(Secure Privileged Access)를 구현합니다.</li><li>Cloud App Security를 사용하여 내부자 위협을 모니터링합니다.</li><li>Cloud App Security를 사용하여 섀도 IT SaaS 사용을 검색합니다.</li></ul>|
|ID 및 액세스 관리|<ul><li>정책 및 운영 프로세스를 구체화합니다.</li><li>Azure AD ID 보호를 사용하여 내부자 위협을 식별합니다.</li></ul>|
|정보 보호|정보 보호 정책을 구체화합니다. <ul><li>Microsoft 365 및 Office 365 민감도 레이블 및 DLP(데이터 손실 방지) 또는 Azure Information Protection</li><li>Cloud App Security 정책 및 경고.</li></ul>|
|

또한 참조: 페티야 및 [WannaCrypt와](https://cloudblogs.microsoft.com/microsoftsecure/2018/02/21/how-to-mitigate-rapid-cyberattacks-such-as-petya-and-wannacrypt/)같은 신속한 사이버 공격을 완화하는 방법
