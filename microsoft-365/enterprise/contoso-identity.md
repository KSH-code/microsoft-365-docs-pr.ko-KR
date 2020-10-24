---
title: Contoso Corporation의 ID
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso가 IDaaS(Identity as a Service)를 활용하고 직원을 위해 클라우드 기반 인증을 제공하고, 파트너 및 고객을 위해 페더레이션 인증을 제공하는 방법을 알아봅니다.
ms.openlocfilehash: dea0f53ef1c3fdc2ea32256303c6120c614c904d
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754644"
---
# <a name="identity-for-the-contoso-corporation"></a>Contoso Corporation의 ID

Microsoft는 azure Active Directory (Azure AD)를 통해 클라우드 서비스에서 IDaaS (Identity as a Service)를 제공 합니다. Microsoft 365 for enterprise를 채택 하기 위해 Contoso IDaaS 솔루션은 온-프레미스 id 공급자를 사용 하 고 기존의 신뢰할 수 있는 타사 id 공급자와 페더레이션 인증을 포함 해야 했습니다.

## <a name="the-contoso-active-directory-domain-services-forest"></a>Contoso Active Directory 도메인 서비스 포리스트

Contoso는 \. 전 세계 각 지역에 대해 하나씩 7 개의 하위 도메인을 갖는 contoso com에 대해 단일 AD DS (Active Directory 도메인 서비스) 포리스트를 사용 합니다. 본사, 지역 허브 사무실 및 위성 사무실에는 로컬 인증 및 권한 부여를 위한 도메인 컨트롤러가 있습니다.

다음은 지역별 허브를 포함 하는 전 세계 여러 지역에 대 한 지역별 도메인을 포함 하는 Contoso 포리스트입니다.

![Contoso의 전 세계 포리스트 및 도메인](../media/contoso-identity/contoso-identity-fig1.png)
 
Contoso는 \. Microsoft 365 작업 및 서비스에 대 한 인증 및 권한 부여를 위해 contoso com 포리스트에서 계정 및 그룹을 사용 하기로 결정 했습니다.

## <a name="the-contoso-federated-authentication-infrastructure"></a>Contoso 페더레이션 인증 인프라

Contoso는 다음을 허용합니다.

- 고객은 Microsoft, Facebook 또는 Google Mail 계정을 사용 하 여 회사의 공용 웹 사이트에 로그인 할 수 있습니다.
- 공급 업체 및 파트너가 LinkedIn, Salesforce 또는 Google Mail 계정을 사용 하 여 회사의 파트너 엑스트라넷에 로그인 할 수 있습니다.

다음은 공용 웹 사이트, 파트너 엑스트라넷 및 AD FS (Active Directory Federation Services) 서버 집합을 포함 하는 Contoso DMZ입니다. DMZ는 고객, 파트너 및 인터넷 서비스가 포함 된 인터넷에 연결 됩니다.

![Contoso 고객 및 파트너에 대 한 페더레이션 인증 지원](../media/contoso-identity/contoso-identity-fig2.png)
 
DMZ의 AD FS 서버는 id 공급자에의 한 고객 자격 증명을 사용 하 여 공용 웹 사이트에 액세스 하 고 파트너 엑스트라넷에 액세스할 수 있는 파트너 자격 증명을 인증 합니다.

Contoso는이 인프라를 유지 하 고 고객 및 파트너 인증을 전담 하도록 결정 했습니다. Contoso identity 설계자는이 인프라를 Azure AD [B2B](https://docs.microsoft.com/azure/active-directory/b2b/hybrid-organizations) 및 [B2C](https://docs.microsoft.com/azure/active-directory-b2c/solution-articles) 솔루션으로 변환 하는 방법을 조사 중입니다.

## <a name="hybrid-identity-with-password-hash-synchronization-for-cloud-based-authentication"></a>클라우드 기반 인증을 위해 암호 해시 동기화를 사용하는 하이브리드 ID

Contoso는 온-프레미스 AD DS 포리스트를 사용 하 여 Microsoft 365 클라우드 리소스에 대 한 인증을 원했습니다. 암호 해시 동기화 (PHS)를 사용 하기로 결정 했습니다.

PHS는 온-프레미스 AD DS 포리스트와 엔터프라이즈 구독에 대 한 Microsoft 365의 Azure AD 테 넌 트를 동기화 하 고 사용자 및 그룹 계정 및 해시 버전의 사용자 계정 암호를 복사 합니다.

디렉터리 동기화를 수행 하기 위해 Contoso는 파리 데이터 센터의 서버에 Azure AD Connect 도구를 배포 했습니다.

Azure AD Connect를 실행 하는 서버는 변경에 대 한 Contoso AD DS 포리스트를 폴링하고 이러한 변경 내용을 Azure AD 테 넌 트와 동기화 합니다.

![Contoso PHS 디렉터리 동기화 인프라](../media/contoso-identity/contoso-identity-fig4.png)
 
## <a name="conditional-access-policies-for-identity-and-device-access"></a>ID 및 디바이스 액세스에 대한 조건부 액세스 정책

Contoso는 다음 세 가지 보호 수준에서 Azure AD 및 Intune [조건부 액세스 정책](identity-access-policies.md) 세트를 만들었습니다.

- *기본* 보호는 모든 사용자 계정에 적용 됩니다.
- *중요 한* 보호는 선임 리더십 및 경영 직원에 게 적용 됩니다.
- *높은 규제* 보호는 높은 규제 대상 데이터에 대 한 액세스 권한이 있는 재무, 법률 및 연구 부서에서 특정 사용자에 게 적용 됩니다.

다음은 Contoso id 및 장치 조건부 액세스 정책의 결과 집합입니다.

![Contoso의 ID 및 디바이스 조건부 액세스 정책](../media/contoso-identity/contoso-identity-fig5.png)
 
## <a name="next-step"></a>다음 단계

Contoso에서 Microsoft 끝점 구성 관리자 인프라를 사용 하 여 조직 전체에 [최신 Windows 10 Enterprise를 배포 하 고 유지](contoso-win10.md) 하는 방법을 알아봅니다.

## <a name="see-also"></a>참고 항목

[Microsoft 365의 ID 로드맵](identity-roadmap-microsoft-365.md)

[엔터프라이즈용 Microsoft 365 개요](microsoft-365-overview.md)

[테스트 랩 가이드](m365-enterprise-test-lab-guides.md)
