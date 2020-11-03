---
title: Id 및 그 외의 설계자 관점
description: 설명이.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: fc975610e24980c6a552179359bb643eb9ac040c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/03/2020
ms.locfileid: "48845255"
---
# <a name="to-identity-and-beyond--one-architects-viewpoint"></a>Id 및 그 외의 설계자 관점

이 문서에서 [Alex Shteynberg](https://www.linkedin.com/in/alex-shteynberg/), microsoft의 주요 기술 설계자는 microsoft 365 및 기타 microsoft 클라우드 서비스를 채택 하는 엔터프라이즈 조직에 대 한 주요 디자인 전략에 대해 설명 합니다.

## <a name="about-the-author"></a>만든 이 정보

![Alex Shteynberg photo](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

저는 뉴욕 [Microsoft 기술 센터](https://www.microsoft.com/mtc?rtc=1)의 기본 기술 설계자입니다. 대부분의 고객 및 복잡 한 요구 사항에 대 한 작업을 수행 하 고 있습니다. 내 관점과 의견은 이러한 상호 작용을 기반으로 하며 모든 상황에 적용 되지 않을 수 있습니다. 하지만 필자의 환경에서 가장 복잡 한 문제를 해결 하는 데 도움이 될 수 있는 경우 모든 고객에 게 도움이 될 수 있습니다. 

일반적으로는 매년 100 + 고객을 사용 합니다. 모든 조직에 고유한 특성이 있지만 경향 및 commonalities를 확인 하는 것은 흥미롭습니다. 예를 들어 많은 고객을 위해 업계 간 관심사를 갖는 경향이 있습니다. 모든 경우에 은행 지점은 커피숍과 커뮤니티 센터가 될 수 있습니다. 

내 역할에서 고객에 게 최상의 기술 솔루션을 도착 하 여 고유한 비즈니스 목표 집합을 해결 하는 데 주력 합니다. 공식적으로는 Id, 보안, 개인 정보 보호 및 규정 준수에 중점을 둔 것입니다. 여기에는 모든 것이 터치 된다는 사실을 좋아합니다. 이를 통해 대부분의 프로젝트와 관련 된 기회를 얻을 수 있습니다. 이를 통해이를 계속 사용 하 고이 역할을 즐길 합니다. 

뉴욕 구/군/시에 살고 있으며, 사실상 문화, 음식 및 사용자 (트래픽 아님)의 다양성을 좋아합니다. 제가 전 세계 대부분을 볼 수 있을 때 여행 하기를 희망 합니다. 현재 wildlife에 대 한 자세한 내용은 아프리카을 연구 하 고 있습니다.

## <a name="guiding-principles"></a>안내 원칙 

- 일반적으로는 기술과 함께 모든 작업을 수행 하 **는 것이 좋습니다** . 이를 의미 하는 것은 아닙니다. 특히 보안 공간에서 솔루션을 과다 하 게 구축 합니다. 이 [비디오](https://www.youtube.com/watch?v=SOQgABDSYZE) 는 Google의 Stripe 전화 회의에서이 지점에 밑줄을 지정 하는 것과 같습니다.
- **사람, 프로세스, 기술** — 사용자가 먼저 기술 없이 프로세스를 향상 시킬 수 [있도록 디자인](https://en.wikipedia.org/wiki/Human-centered_design) 합니다. 완벽 한 솔루션은 없습니다. 각 비즈니스에 따라 다양 한 위험 요인 및 의사 결정을 분산 해야 합니다. 사용자가 나중에 사용 하는 방법을 설계 하는 고객이 너무 많습니다.
- **' 첫 번째 ' 이유와 ' how to '** 를 사용 하는 경우에 중점을 둔 것은 귀찮은 7 yr 오래 된 어린이입니다. 적절 한 질문을 모르는 경우 올바른 답변에 도착할 수 없습니다. 많은 고객이 비즈니스 문제를 정의 하는 대신 작업을 수행 해야 하는 방식에 대 한 가정을 합니다. 항상 여러 개의 경로를 사용할 수 있습니다.
- **이전의 모범 사례 중 긴** 방법-가벼운 속도에서 변경 되는 모범 사례를 인식 합니다. Azure AD를 3 달 이상 전에 살펴본 경우 오래 된 것이 원인일 수 있습니다. 게시 후 변경 되는 내용은 다음과 같습니다. 오늘 "최상" 옵션은 지금부터 6 개월이 다를 수 있습니다.

## <a name="baseline-concepts"></a>기본 개념

이 섹션은 건너뛰지 마세요. 수년간 클라우드 서비스를 사용 하는 고객의 경우에도 이러한 항목에 대 한 단계를 다시 수행 해야 합니다.
하지만 언어는 정확한 도구가 아닙니다. 같은 단어를 사용 하 여 같은 개념을 의미 하는 경우가 많습니다. 이 다이어그램을 사용 하 여 몇 가지 기본 용어와 "계층 구조 모델"을 설정 하는 것이 좋습니다.
<br><br>

![테 넌 트, 구독, 서비스 및 데이터에 대 한 그림](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)  

<br>

스윔에 대 한 자세한 내용은 풀에서 시작 하는 것이 좋습니다. 이 다이어그램과 기술적으로 정확 하 게 생각 하지 않겠습니다. 여기에는 몇 가지 기본 개념에 대해 설명 하는 모델이 있습니다. 

다음은 이 다이어그램에 대한 설명입니다.
- 테 넌 트 = Azure AD의 인스턴스입니다. 계층 구조의 "위쪽" 또는 다이어그램의 수준 1에 있습니다. 이는 다른 모든 작업을 수행 하는 "[경계](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-directory-independence)"로 간주 될 수 있습니다 ([Azure AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) 옆). 모든 Microsoft enterprise 클라우드 서비스는 다음 테 넌 트 중 하나의 일부입니다. 소비자 서비스는 별개입니다. "테 넌 트"가 Office 365 테 넌 트, Azure 테 넌 트, WVD 테 넌 트 등으로 설명서에 표시 됩니다. 이러한 변형은 고객에 게 혼란을 줄 수도 있습니다.
- 다이어그램의 서비스/구독, 수준 2는 하나의 테 넌 트에만 속합니다. 대부분의 SaaS 서비스는 1:1 이며 마이그레이션 없이 이동할 수 없습니다. Azure가 다르면 [대금 청구](https://docs.microsoft.com/azure/cost-management-billing/manage/billing-subscription-transfer) 및/또는 [구독](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) 을 다른 테 넌 트로 이동할 수 있습니다. Azure 구독을 이동 해야 하는 고객이 많습니다. 여기에는 다양 한 함축 기능이 있습니다. 구독 외부에 있는 개체 (예: 그룹, 앱, 정책 등을 비롯 한 RBAC 및 Azure AD 개체)는 이동 하지 않습니다. 또한 일부 서비스 (Azure 키 보관소, 데이터 Brick 등)는 작동 하지 않는 상태에서 이동 합니다. 비즈니스 요구 사항이 없는 경우 서비스를 마이그레이션하지 않습니다. 마이그레이션에 도움이 될 수 있는 일부 스크립트는 [GitHub에서 공유](https://github.com/lwajswaj/azure-tenant-migration)됩니다. 
- 지정 된 서비스에는 일반적으로 일종의 "하위 수준" 경계 또는 L3 (수준 3)이 있습니다. 이는 보안, 정책, 거 버 넌 스 등의 조각화을 이해 하는 데 유용 합니다. 불행 하 게도 아는 이름이 확실 하지 않습니다. L3에 대 한 몇 가지 예: Azure Subscription = [resource](https://docs.microsoft.com/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [인스턴스](https://docs.microsoft.com/dynamics365/admin/new-instance-management); Power BI = [workspace](https://docs.microsoft.com/power-bi/service-create-the-new-workspaces); Power Apps = [환경](https://docs.microsoft.com/power-platform/admin/environments-overview); 기타.
- 수준 4는 실제 데이터가 저장 되는 위치입니다. 이 ' 데이터 평면 '은 복잡 한 주제입니다. 일부 서비스는 RBAC에 대해 Azure AD를 사용 하 고 있습니다. 여기에서는 위임 항목에 대해 자세히 설명 합니다.

많은 고객 및 Microsoft 직원을 찾는 몇 가지 추가 개념은 다음과 같이 혼동을 겪고 있거나 의문 사항이 있습니다.


- 모든 사용자가 비용에 상관 [없이](https://azure.microsoft.com/pricing/details/active-directory/)여러 테 넌 트를 [만들](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) 수 있습니다. It에 프로 비전 된 서비스가 필요 하지 않습니다. 수십 개를가지고 있습니다. 각 테 넌 트 이름은 Microsoft의 전 세계 클라우드 서비스에서 고유 합니다 (즉, 두 테 넌 트에 같은 이름을 사용할 수 없음). 모두 TenantName.onmicrosoft.com의 형식입니다. 테 넌 트를 자동으로 만드는 프로세스 ([관리 되지 않는 테 넌 트](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup))도 있습니다. 예를 들어 사용자가 다른 테 넌 트에 존재 하지 않는 전자 메일 도메인을 사용 하 여 엔터프라이즈 서비스에 등록할 때 이러한 상황이 발생할 수 있습니다. 
- 관리 되는 테 넌 트에서 많은 [DNS 도메인](https://docs.microsoft.com/azure/active-directory/fundamentals/add-custom-domain) 을 등록할 수 있습니다. 이 경우 원래 테 넌 트 이름은 변경 되지 않습니다. 현재 마이그레이션 외에는 테 넌 트의 이름을 바꿀 수 있는 쉬운 방법은 없습니다. 테 넌 트 이름은 기술적으로 중요 하지 않지만 이러한 일은 제한 될 수 있습니다.
- 아직 서비스 배포를 계획 하지 않은 경우에도 조직의 테 넌 트 이름을 예약 해야 합니다. 그렇지 않은 경우 누군가가 사용자의 작업을 수행할 수 있으며,이를 다시 수행 하는 간단한 프로세스는 없습니다 (DNS 이름과 같은 문제). 고객 으로부터 너무 자주이 방법을 들을 수 있습니다. 여기에는 테 넌 트 이름도 있을 것입니다.
- DNS 네임 스페이스를 소유 하 고 있는 경우 해당 사용자를 테 넌 트에 추가 해야 합니다. 그렇지 않으면이 이름을 사용 하 여 [관리 되지 않는 테 넌 트](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-self-service-signup) [를 만들 수 있습니다.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS 네임 스페이스 (예: contoso.com)는 한 테 넌 트 하나에만 속할 수 있습니다. 이는 다양 한 시나리오 (예: 합병 또는 인수 작업 중에 전자 메일 도메인 공유)에 대 한 것입니다. 다른 테 넌 트에 DNS 하위 부분 (예: div.contoso.com)을 등록 하는 방법이 있습니다. 최상위 도메인 이름을 등록 하면 모든 하위 도메인이 같은 테 넌 트에 속해 있는 것으로 간주 됩니다. 다중 테 넌 트 시나리오 (아래 참조)에서는 일반적으로 다른 최상위 도메인 이름 (예: contoso.ch 또는 ch-contoso.com)을 사용 하는 것이 좋습니다.
- 어떤 사용자가 테 넌 트를 "소유" 해야 하나요? 현재 테 넌 트를 소유 하 고 있는지 모르는 고객을 표시 하는 경우가 많습니다. 큰 빨강 플래그입니다. Microsoft 지원 ASAP로 전화 합니다. 서비스 소유자 (대개 Exchange 관리자)가 테 넌 트를 관리 하도록 지정 된 경우에도 문제를 일으키는 것입니다. 이 테 넌 트에는 나중에 필요할 수 있는 모든 서비스가 포함 됩니다. 테 넌 트 소유자는 조직에 있는 모든 클라우드 서비스의 설정에 대 한 결정을 내릴 수 있는 그룹 이어야 합니다. 또 다른 문제는 테 넌 트 소유자 그룹에 모든 서비스 관리를 요청 하는 경우입니다. 대규모 조직에서는 확장 되지 않습니다.
- 하위/수퍼 테 넌 트 라는 개념이 없습니다. 어떤 이유로이 신화는 자신을 반복 해 서 유지 합니다. 이는 [AZURE AD B2C](https://docs.microsoft.com/azure/active-directory-b2c/) 테 넌 트에도 적용 됩니다. "내 B2C 환경이 내 XYZ 테 넌 트에 있습니다." 또는 "Azure 테 넌 트를 내 Office 365 테 넌 트로 이동 하려면 어떻게 해야 하나요?"
- 이 문서는 대부분의 고객이 사용 하는 것과 같은 상업용 세계 클라우드를 중점적으로 다루고 있습니다. [Sovereign 클라우드에 클라우드에](https://docs.microsoft.com/azure/active-directory/develop/authentication-national-cloud)대해 아는 것이 도움이 되는 경우가 있습니다. Sovereign 클라우드에 클라우드에는이 토론의 범위를 벗어나 설명 하는 추가 관련 사항이 있습니다.


## <a name="baseline-identity-topics"></a>기본 id 항목

Microsoft의 id 플랫폼에 대 한 설명서가 많이 있습니다. azure Active Directory (Azure AD) 처음부터 시작 하는 사용자의 경우에는 흔히 해당 되는 경우가 많습니다. 이에 대 한 자세한 내용은 지속적인 혁신 및 변화를 유지 하는 것이 어려울 수 있습니다. 필자의 고객 상호 작용에서는 비즈니스 목표와 "이해 하기 쉽고, 최상"의 "변환기"를 제공 하며 이러한 주제를 해결 하는 방법에 대해 알아봅니다. 완벽 한 대답 및 "적절 한" 결정이 다양 한 위험 요인의 균형을 갖는 경우는 거의 없습니다. 다음은 고객과 논의할 경향이 있는 몇 가지 일반적인 질문 및 혼동 되는 영역입니다.

### <a name="provisioning"></a>Provisioning
Azure AD는 id 세계에서 거 버 넌 스 부족을 해결 하지는 못합니다. [Id 거 버 넌 스](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview) 는 클라우드 결정에 관계 없이 중요 한 요소 여야 합니다. 거 버 넌 스 요구 사항은 시간이 지남에 따라 도구를 사용할 수 없는 프로그램입니다. 

[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect) 와 MIM ( [Microsoft Identity Manager](https://docs.microsoft.com/microsoft-identity-manager/microsoft-identity-manager-2016) ) vs. 기타 (타사 또는 사용자 지정) 지금까지 보다 많은 headache을 저장 하 고 향후 Azure AD Connect를 사용 하 여 이동 합니다. 이 도구에는 peculiar 고객 구성 및 지속적인 혁신을 해결 하기 위한 모든 종류의 smarts이 있습니다. 

좀 더 복잡 한 아키텍처에서 구동 될 수 있는 일부 edge 사례는 다음과 같습니다.
- 이러한 간 네트워크 연결을 사용 하지 않는 여러 AD 포리스트 [클라우드 프로 비전](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)이라는 새로운 옵션이 있습니다.
- Active Directory가 없지만 설치 하 고 싶습니다. [LDAP에서 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) 하도록 Azure AD Connect를 구성할 수 있습니다 (파트너가 필요할 수 있음).
- 여러 테 넌 트에 같은 개체를 구축 해야 합니다. 이는 기술적으로 지원 되지는 않지만 "같음" 정의에 따라 달라 집니다.

기본 동기화 규칙 ([필터 개체](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering), [변경 특성](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized), [대체 로그인 ID](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-userprincipalname)등)을 사용자 지정 해야 하나요? 피하십시오! Id 플랫폼은이를 사용 하는 서비스 만큼 중요 한 역할을 합니다. 모든 종류의 nutty 구성을 수행할 수 있지만이 질문에 답하려면 응용 프로그램에 대 한 영향을 확인 해야 합니다. 메일 사용 가능 개체를 필터링 하면 온라인 서비스에 대 한 GAL이 불완전 하 게 됩니다. 응용 프로그램에서 특정 특성을 사용 하는 경우 필터링은 예기치 않은 영향을 받게 됩니다. 기타. 이는 id 팀 의사 결정이 아닙니다.

XYZ SaaS는 JIT (Just-in-time) 프로 비전을 지원 하며, 동기화 해야 하는 이유는 무엇 인가요? 위 내용을 참조하세요. 대부분의 응용 프로그램에는 기능에 대 한 "프로필" 정보가 필요 합니다. 모든 메일 사용이 가능한 개체를 사용할 수 없는 경우에는 GAL을 가질 수 없습니다. Azure AD와 통합 된 응용 프로그램의 [사용자 프로 비전](https://docs.microsoft.com/azure/active-directory/app-provisioning/user-provisioning) 에도 동일 하 게 적용 됩니다.


### <a name="authentication"></a>인증

[암호 해시 동기화](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) (phs)와 [통과 인증](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-pta-how-it-works) (pta) [vs.](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-fed-compatibility)

일반적으로 페더레이션에 대해서는 passionate 논쟁에 대해 [논의](https://docs.microsoft.com/azure/active-directory/hybrid/choose-ad-authn) 합니다. 일반적으로 좀 더 간단 하 게 작동 하는 것이 좋지만, 따라서 좋은 이유가 없는 경우가 아니면 PHS를 사용 합니다. 같은 테 넌 트에 있는 각 DNS 도메인에 대해 서로 다른 인증 방법을 구성할 수도 있습니다. 

일부 고객은 주로 다음에 대해 페더레이션 + PHS를 사용 하도록 설정 합니다.
- 페더레이션 서비스를 사용할 수 없는 경우 재해 복구를 위해 [폴백](https://docs.microsoft.com/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) 옵션입니다.
- 추가 기능 (예: [AZURE AD DS](https://docs.microsoft.com/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)) 및 보안 서비스 (예: 누수 되는 [자격 증명](https://docs.microsoft.com/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials))
- 페더레이션 인증 (예: [Azure 파일](https://docs.microsoft.com/azure/storage/files/storage-files-active-directory-overview))을 이해 하지 못하는 Azure의 서비스 지원

고객은 클라이언트 인증 흐름을 통해 일부 misconceptions를 명확 하 게 설명 하는 경우가 많습니다. 결과는 아래 그림과 같이 표시 되며,이는 대화형 프로세스에 적합 하지 않습니다.


![화이트 보드 대화 예](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

이 유형의 화이트 보드 드로잉은 인증 요청 흐름 내에서 보안 정책이 적용 되는 위치를 보여 줍니다. 이 예에서는 AD FS (Active Directory Federation Service)를 통해 적용 되는 정책이 첫 번째 서비스 요청에 적용 되지만 후속 서비스 요청에는 해당 되지 않습니다. 이는 보안 제어를 클라우드로 최대한 이동 하는 하나 이상의 이유입니다.

Microsoft는 여러분이 기억이 가능 하기만 하면 sso ( [single sign-on](https://docs.microsoft.com/azure/active-directory/manage-apps/what-is-single-sign-on) )의 꿈를 추적 했습니다. 일부 고객은 "right" 페더레이션 (STS) 공급자를 선택 하 여이를 달성할 수 있다고 생각 합니다. Azure AD는 SSO 기능을 [사용](https://docs.microsoft.com/azure/active-directory/manage-apps/plan-sso-deployment) 하는 데 상당히 도움이 되지만 STS는 놀라운 것이 아닙니다. 중요 한 응용 프로그램에 여전히 사용 되는 "레거시" 인증 방법이 너무 많습니다. [파트너 솔루션](https://docs.microsoft.com/azure/active-directory/saas-apps/tutorial-list) 을 사용 하 여 Azure AD를 확장 하면 이러한 여러 시나리오를 처리할 수 있습니다. SSO는 전략 및 여행입니다. [응용 프로그램에 대 한 표준을](https://docs.microsoft.com/azure/active-directory/develop/v2-app-types)전환 하지 않고도이를 얻을 수 있습니다. 이 항목에는 [암호를 더 적게](https://docs.microsoft.com/azure/active-directory/authentication/concept-authentication-passwordless) 사용할 수 있는데, 이러한 인증을 통해 마법의 대답이 없습니다. 

현재 MFA ( [multi-factor authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) )는 필수 사항입니다 (자세한 내용은[여기](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) ). It [사용자 동작 분석](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) 에 추가 하 고 일반적인 사이버 대부분의 공격을 방지 하는 솔루션을 보유 하 고 있습니다. 심지어 MFA를 요구 하도록 소비자 서비스도 이동 합니다. 그러나 아직 까지는 [최신 인증](https://docs.microsoft.com/microsoft-365/enterprise/hybrid-modern-auth-overview) 방법으로 이동 하지 않으려는 많은 고객을 대상으로 합니다. 가장 큰 인수는 사용자와 레거시 응용 프로그램에 영향을 줍니다. 경우에 따라 고객은 Exchange Online에서 발표 하는 온라인 [변경 사항을](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282)이동 하는 데 도움이 될 수 있습니다. 이제 고객이 이러한 전환을 지원 하기 위해 많은 Azure AD [보고서](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) 를 사용할 수 있습니다.



### <a name="authorization"></a>권한 부여

[위키백과](https://en.wikipedia.org/wiki/Authorization)에 따라 "권한 부여"는 액세스 정책을 정의 하는 것입니다. 대부분의 사용자는 개체 (파일, 서비스 등)에 대 한 액세스 제어를 정의할 수 있는 기능을 찾습니다. 사이버 위협의 현재 세계에서이 개념은 다양 한 위협 벡터에 반응할 수 있는 동적 정책으로 빠르게 발전 하 고 이러한 상황에 대 한 응답으로 액세스 제어를 빠르게 조정 하는 데 사용 됩니다. 예를 들어, 비정상적인 위치에서 은행 계좌에 액세스 하는 경우 추가 확인 단계가 제공 됩니다. 이를 위해서는 정책 자체 뿐 아니라 위협 검색 및 신호 상관 관계 방법론의 에코를 고려해 야 합니다.

Azure AD의 정책 엔진은 [조건부 액세스 정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)사용 하 여 구현 됩니다. 이 시스템은 다양 한 위협 감지 시스템의 정보에 따라 동적인 결정을 내립니다. 간단한 보기는 다음 그림과 같습니다.

![Azure AD의 정책 엔진](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

이러한 모든 신호를 함께 조합 하면 다음과 같은 동적 정책이 허용 됩니다.
- 장치에서 위협이 검색 되 면 데이터에 대 한 액세스는 다운로드 기능 없이 웹으로 제한 됩니다.
- 비정상적으로 많은 양의 데이터를 다운로드 하는 경우 다운로드 하는 모든 내용이 암호화 되 고 제한 됩니다.
- 관리 되지 않는 장치에서 서비스에 액세스 하는 경우 중요 한 데이터는 차단 되지만 다른 위치로 복사 하는 기능 없이 제한 되지 않은 데이터에 액세스할 수 있습니다.

이 확장 된 권한 부여 정의에 동의 하는 경우 추가 솔루션을 구현 해야 합니다. 구현할 솔루션은 정책을 적용할 동적 방법과 우선 순위를 지정할 위협에 따라 달라 집니다. 이러한 시스템의 몇 가지 예는 다음과 같습니다.
- [Azure AD ID 보호](https://docs.microsoft.com/azure/active-directory/identity-protection/) 
- [ID용 Microsoft Defender](https://docs.microsoft.com/azure-advanced-threat-protection/)
- [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Microsoft Defender for Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp?view=o365-worldwide)
- [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/) (mcas)
- [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)
- [Microsoft Intune](https://docs.microsoft.com/mem/intune/)
- [Microsoft 정보 보호](https://docs.microsoft.com/microsoft-365/compliance/protect-information?view=o365-worldwide) (밉)
- [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/) 

물론 Azure AD 외에도 다양 한 서비스와 응용 프로그램에는 고유한 인증 모델이 있습니다. 이 중 일부는 나중에 위임 섹션의 뒷부분에서 설명 합니다.

### <a name="audit"></a>감사
Azure AD에는 자세한 [감사 및 보고](https://docs.microsoft.com/azure/active-directory/reports-monitoring/) 기능이 있습니다. 하지만 보안 결정을 내리는 데 필요한 유일한 정보는 아닙니다. 위임 섹션에서 자세한 설명을 참조 하세요.

## <a name="there-is-no-exchange"></a>Exchange가 없음

당황하지 마! Exchange가 더 이상 사용 되지 않는 것은 아닙니다 (또는 SharePoint 등). 여전히 핵심 서비스입니다. 지금까지 설명 했을 때 기술 공급자는 UX (사용자 환경)를 전환 하 여 여러 서비스의 구성 요소를 포함 하 고 있다는 것을 의미 합니다. Microsoft 365에서는 전자 메일에 첨부 파일을 SharePoint Online 또는 비즈니스용 OneDrive에 저장 하는 "[최신 첨부 파일](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)"을 예로 들 수 있습니다. 

![전자 메일에 파일 첨부](../media/solutions-architecture-center/modern-attachments.png)

Outlook 클라이언트를 살펴보면 Exchange 뿐만 아니라이 환경의 일부로 "연결 된" 여러 서비스가 표시 될 수 있습니다. 여기에는 Azure AD, Microsoft 검색, 앱, 프로필, 준수 및 Office 365 그룹이 포함 됩니다. 

![설명선이 있는 Outlook 인터페이스](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

예정 된 기능의 미리 보기에 대 한 자세한 내용은 [Microsoft 유체 Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) 를 참조 하세요. 지금 미리 보기에서는 Outlook에서 팀에 직접 대화를 읽고 회신할 수 있습니다. 실제로 [팀 클라이언트](https://products.office.com/microsoft-teams/download-app) 는이 전략의 보다 두드러진 예 중 하나입니다. 

전체적으로는 Office 365와 Microsoft 클라우드에서 다른 서비스 사이에 선명한 선을 그리는 것이 더 어렵습니다. 예를 들어 하나의 구성 요소를 사용 하는 경우에도 모든 작업에 대 한 총 혁신을 통해 혜택을 얻을 수 있으므로 고객에 게 큰 도움이 될 것입니다. 상당히 세련 되 고 많은 고객에 게 미치는 영향에 도달 했습니다.

오늘날에는 많은 고객 IT 그룹에 "products"가 구성 되어 있습니다. 각 특정 제품에 대 한 전문가가 필요 하기 때문에 온-프레미스 세계를 논리적으로 사용 해야 합니다. 그러나 이러한 서비스가 클라우드로 이동 되 면 Active Directory 또는 Exchange 데이터베이스를 다시 디버그할 필요가 없습니다. 자동화 (클라우드 종류는 is)는 반복적인 수동 작업을 제거 합니다 (공장에 대 한 자세한 내용 확인). 하지만 서비스 간 상호 작용, 영향, 비즈니스 요구 등을 이해 하기 위해 이러한 요구 사항을 보다 복잡 한 것으로 대체 되었습니다. [자세한](https://docs.microsoft.com/learn/)내용은 클라우드 변환에 따라 사용 하도록 설정 하는 것이 좋습니다. 기술에 참여 하기 전에 IT 기술 및 팀 구조에서 변경 관리에 대해 고객에 게 문의 하는 것이 일반적입니다.

모든 SharePoint 팬-사용자 및 개발자에 게 "SharePoint online에서 XYZ를 어떻게 확인할 수 있습니까?" 라는 질문을 중지 하세요. 즉, Flow ( [Power 자동화](https://docs.microsoft.com/power-automate/) )를 사용 하 여 워크플로를 보다 강력한 플랫폼으로 사용할 수 있습니다. [Azure Bot 프레임 워크](https://docs.microsoft.com/azure/bot-service/?view=azure-bot-service-4.0) 를 사용 하 여 500k 항목 목록에 더 적합 한 UX를 만들 수 있습니다. CSOM 대신 [Microsoft Graph](https://developer.microsoft.com/graph/) 사용을 시작 합니다. [Microsoft 팀](https://docs.microsoft.com/MicrosoftTeams/Teams-overview) 에는 SharePoint 뿐만 아니라 더 많은 작업이 포함 됩니다. 다양 한 예를 나열할 수 있습니다. 아주 광범위 하 고 훌륭한 universe가 있습니다. 문을 열고 탐색을 [시작](https://docs.microsoft.com)합니다.

기타 일반적인 영향은 준수 영역에 있습니다. 이 서비스 간 접근 방식은 많은 준수 정책을 완전히 혼동 하는 것 처럼 보입니다. "EDiscovery 시스템에 대 한 모든 전자 메일 통신을 저널링 해야 합니다." 라는 조직의 상태를 계속 볼 수 있습니다. 이는 전자 메일이 더 이상 전자 메일 일 필요는 없으며 다른 서비스에 대 한 창인 경우는 무엇을 의미 합니까? Office 365에는 포괄적인 [준수](https://docs.microsoft.com/microsoft-365/compliance/)방법이 있지만, 사용자와 프로세스를 변경 하는 것은 일반적으로 기술 보다 훨씬 어렵습니다.

다른 많은 사용자와 프로세스 관련 사항이 있습니다. 필자의 의견에서이는 중요 하 고 설명 된 영역입니다. 다른 문서에서 더 자세히 설명 합니다.

## <a name="tenant-structure-options"></a>테 넌 트 구조 옵션

### <a name="single-tenant-vs-multi-tenant"></a>단일 테 넌 트와 다중 테 넌 트 비교

일반적으로 대부분의 고객에 게는 프로덕션 테 넌 트가 하나만 있어야 합니다. 여러 테 넌 트의 어려움 ( [Bing 검색](https://www.bing.com/search?q=office%20365%20multiple%20tenants)제공) 또는이 [백서](https://aka.ms/multi-tenant-user)에 대 한 자세한 내용을 확인 하는 이유는 여러 가지가 있습니다. 동시에 많은 기업 고객은 IT 학습, 테스트 및 실험을 위한 다른 (소형) 테 넌 트를 사용 합니다. [Azure Lighthouse](https://azure.microsoft.com/services/azure-lighthouse/)를 사용 하면 테 넌 트 Azure 액세스를 보다 쉽게 수행할 수 있습니다. Office 365 및 기타 많은 SaaS 서비스에는 테 넌 트 시나리오에 대 한 제한이 있습니다. [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/what-is-b2b) 시나리오에서는 여러 가지 사항을 고려해 야 합니다.

대부분의 고객은 합병 및 취득 (M&A) 후에 여러 프로덕션 테 넌 트를 사용 하 여 작업을 완료 하 고 통합 하려고 합니다. 현재는 단순한 것이 아니며 MCS (Microsoft 컨설팅 서비스) 또는 파트너와 타사 소프트웨어가 필요 합니다. 나중에 다중 테 넌 트 고객에 게 다양 한 시나리오를 해결 하기 위해 엔지니어링 작업을 지속적으로 진행 하 고 있습니다. 

일부 고객은 둘 이상의 테 넌 트로 이동 하도록 선택 합니다. 이는 중요 한 의사 결정이 고 업무상 항상 중요 한 이유를 기반으로 합니다. 여기에는 다음과 같은 몇 가지 예가 포함 됩니다.
- 서로 다른 엔터티 간의 쉬운 공동 작업이 필요 하지 않으며 관리 및 기타 격리 요구 사항이 높은 지주 유형의 회사 구조입니다.
- 취득 후에는 두 개의 엔터티를 별도로 유지 하기 위해 비즈니스 의사 결정이 이루어집니다.
- 고객 환경에 대 한 시뮬레이션으로, 고객이 프로덕션 환경을 변경 하지는 않습니다. 
- 고객을 위한 소프트웨어 개발

이러한 다중 테 넌 트 시나리오에서 고객은 테 넌 트 간에 일부 구성을 유지 하거나 구성 변경 및 drifts을 보고 하려는 경우가 많습니다. 이는 일반적으로 구성에 대 한 변경 내용을 코드로 옮기는 것을 의미 합니다. Microsoft Premiere support는 다음 공용 IP를 기반으로 하는 이러한 유형의 요구 사항에 대 한 워크숍을 제공 [https://Microsoft365dsc.com](https://Microsoft365dsc.com) 합니다.


### <a name="multi-geo"></a>Multi-Geo 

[다중 지역](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo) 으로, 다중 geo가 아니며, 이것이 질문입니다. Office 365 다중 위치를 사용 하 여 [데이터 상주](https://docs.microsoft.com/microsoft-365/enterprise/o365-data-locations) 요구 사항을 충족 하기 위해 선택한 지리적 위치에 보관 된 데이터를 구축 하 고 저장할 수 있습니다. 이 기능에 대 한 여러 misconceptions 있습니다. 다음 사항에 유의해야 합니다. 
- 성능상의 이점을 제공 하지는 않습니다. [네트워크 디자인이](https://aka.ms/office365networking) 올바르지 않으면 성능이 떨어질 수 있습니다. 데이터가 아닌 Microsoft 네트워크에 대 한 "근접" 장치를 가져옵니다.
- [Gdpr 준수](https://www.microsoft.com/trust-center/privacy/gdpr-overview)에 대 한 솔루션은 아닙니다. GDPR은 데이터 소유권 또는 저장 위치에 중점을 둔 것이 아닙니다. 이에 대 한 다른 규정 준수 프레임 워크가 있습니다.
- 관리 위임 (아래 참조) 또는 [정보 장벽](https://docs.microsoft.com/microsoft-365/compliance/information-barriers)확인은 해결 되지 않습니다.
- 이 파일은 다중 테 넌 트와 동일 하지 않으며 추가 [사용자 프로 비전](https:/docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation) 워크플로가 필요 합니다.
- [테 넌 트](https://docs.microsoft.com/microsoft-365/enterprise/moving-data-to-new-datacenter-geos) (Azure AD)는 다른 지역으로 이동 하지 않습니다. 

## <a name="delegation-of-administration"></a>관리 위임

대부분의 대규모 조직에서 의무 및 RBAC (역할 기반 액세스 제어) 구분은 필요한 현실입니다. 미리 사과 하겠습니다. 이는 일부 고객이 원하는 것 처럼 단순한 것이 아닙니다. 고객, 법률, 규정 준수 및 기타 요구 사항이 서로 다르며 전 세계에 충돌 하는 경우도 있습니다. 단순함 및 유연성이 서로 상반 되는 경우가 많습니다. 문제가 발생 하면 더 나은 작업을 수행할 수 있습니다. 시간이 지남에 따라 상당한 향상이 발생 합니다. 로컬 [Microsoft 기술 센터](https://www.microsoft.com/mtc) 를 방문 하 여 379230 문서를 읽지 않고 비즈니스 요구 사항에 맞는 모델을 처리할 수 있습니다. 여기서는 이러한 방식에 대 한 생각을 중점적으로 설명 합니다. 다음은 계획을 위한 다섯 가지 영역 및 필자가 직면 한 몇 가지 일반적인 질문입니다.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD 및 Microsoft 365 관리 센터

[기본 제공 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)의 길고 증가 된 목록이 있습니다. 각 역할은 특정 작업을 수행할 수 있도록 그룹화 된 역할 권한 목록과 함께 구성 됩니다. 각 역할 내의 "설명" 탭에서 이러한 사용 권한을 확인할 수 있습니다. 또는 Microsoft 365 관리 센터에서이에 해당 하는 사용자의 가독성 버전을 확인할 수 있습니다. 기본 제공 역할에 대 한 정의는 수정할 수 없습니다. 일반적으로 다음과 같은 세 가지 범주로 그룹화 합니다.

- **전역 관리자** —이 "모든 강력한" 역할은 다른 시스템과 마찬가지로 [고도로 보호](https://docs.microsoft.com/microsoft-365/enterprise/protect-your-global-administrator-accounts) 되어야 합니다. 일반적인 권장 사항은 다음과 같습니다. 영구 할당이 없으며 Azure AD PIM (권한 부여 Id 관리)을 사용 합니다. 강력한 인증 기타. 흥미롭게도이 역할은 기본적으로 모든 항목에 대 한 액세스 권한을 제공 하지는 않습니다. 일반적으로 규정 준수 액세스 및 Azure 액세스에 대 한 혼동이 있는데,이에 대해서는 뒷부분에서 설명 합니다. 그러나이 역할은 항상 테 넌 트에서 다른 서비스에 대 한 액세스 권한을 할당할 수 있습니다. 
- **특정 서비스 관리자** -일부 서비스 (Exchange, SharePoint, Power BI 등)는 Azure AD에서 높은 수준의 관리 역할을 사용 합니다. 이 작업은 모든 서비스에서 일관 되지 않으며 나중에 설명 하는 서비스 관련 역할도 더 많이 제공 됩니다.
- **기능** -특정 작업 (게스트 inviter 등)에 초점을 맞춘 긴 (및 증가 하는) 역할 목록이 있습니다. 고객의 요구 사항에 따라 주기적으로 추가 됩니다.

간격이 줄어들어 전체 관리자 역할을 사용 해야 하는 경우도 있지만 모든 항목을 위임할 수는 없습니다. 이 역할의 사용자 멤버 자격 대신 구성-코드 및 자동화를 고려해 야 합니다.

**참고** : Microsoft 365 관리 센터는 사용자에 게 친숙 한 인터페이스를 제공 하지만 Azure AD 관리 환경에 비해 기능 하위 집합이 있습니다. 두 포털 모두 동일한 Azure AD 역할을 사용 하므로 변경 내용이 같은 위치에서 발생 합니다. 팁: 모든 Azure를 사용 하지 않고 id 관리 중심 관리 UI를 사용할 수 있습니다 [https://aad.portal.azure.com](https://aad.portal.azure.com) . 

이름에는 무엇이 있나요? 역할의 이름으로 가정을 만들지 마십시오. 언어가 정확한 도구는 아닙니다. 필요한 역할을 살펴보기 전에 위임 해야 하는 작업을 정의 하는 것이 목표입니다. "보안 독자" 역할에 사용자를 추가 하는 것은 모든 항목에 걸쳐 보안 설정이 표시 되지 않습니다. 

[사용자 지정 역할](https://docs.microsoft.com/azure/active-directory/users-groups-roles/roles-custom-overview) 을 만드는 기능은 일반적인 질문입니다. 이 기능은 Azure AD today (아래 참조)에서 제한 되며 시간에 따라 기능이 향상 됩니다. 이러한 내용은 Azure AD의 함수에 적용 되며 위에서 설명한 계층 구조 모델을 "다운" 하지 못할 수 있습니다. "사용자 지정"을 처리할 때마다 필자의 사용자 계정으로 다시 "simple is 좋음"으로 돌아가는 경향이 있습니다.

또 다른 일반적인 질문은 디렉터리의 하위 집합에 대 한 역할 범위를 설정할 수 있다는 것입니다. 예를 들면 "EU 전용 사용자의 헬프데스크 관리자"와 같습니다. AU ( [관리 단위](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-administrative-units) )는이를 해결 하기 위한 것입니다. 위와 같이 Azure AD의 함수에 해당 되는 것으로 간주 되며 "down"을 사용할 수 없습니다. 물론 특정 역할은 범위 (전역 관리자, 서비스 관리자 등)에 게 적합 하지 않습니다.

현재 이러한 모든 역할에는 직접 구성원 자격 ( [AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/)을 사용 하는 경우 동적 할당)이 필요 합니다. 즉, 고객은 Azure AD에서 직접 관리 해야 하며, 이러한 정보는 보안 그룹 구성원을 기반으로 할 수 없습니다. 이를 관리 하기 위한 스크립트를 만드는 것이 더 높은 권한으로 실행 해야 하는 것은 아닙니다. 일반적으로 Saviynt와 같은 프로세스 시스템과 ServiceNow 또는 파트너 거 버 넌 스 도구를 사용 하는 것이 좋습니다. 이러한 시간에 따라이를 해결 하기 위해 엔지니어링 작업을 진행 하 고 있습니다.

[AZURE AD PIM](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/) 을 몇 번 언급 했습니다. 온-프레미스 컨트롤에 해당 하는 MIM (Microsoft Identity Manager)의 PAM ( [액세스 권한 관리](https://docs.microsoft.com/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) ) 솔루션이 있습니다. PAWs ( [권한 부여 된 액세스 워크스테이션](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/privileged-access-workstations) ) 및 [Azure AD Identity 거 버 넌 스](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)를 확인할 수도 있습니다. 모든 타사 도구를 사용 하는 경우에는 항상 just-in-time, 충분히, 동적 역할 상승을 사용할 수 있습니다. 이는 일반적으로 환경 보안에 대 한 보다 큰 논의의 일부입니다. 

경우에 따라 역할에 외부 사용자를 추가 하기 위한 호출이 발생 합니다 (위의 다중 테 넌 트 섹션 참조). 이렇게 하면 제대로 작동 합니다. [AZURE AD B2B](https://docs.microsoft.com/azure/active-directory/b2b/) 는 다른 문서를 통해 고객을 안내 하는 또 다른 크고 흥미로운 주제입니다.

### <a name="security-and-compliance-center-scc"></a>SCC (보안 및 준수 센터)

[Office 365 보안 & 준수 센터의 사용 권한은](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center) Azure AD 역할에서 분리 되 고 고유한 "역할 그룹" 모음입니다. 이러한 역할 그룹 중 일부는 Azure AD 역할 (예: 보안 판독기)과 이름이 같으므로 서로 다른 멤버 자격이 있을 수 있으므로 혼동 될 수 있습니다. Azure AD 역할을 사용 하는 것이 좋습니다. 각 역할 그룹은 하나 이상의 "역할" (같은 단어 다시 사용에 대 한 것은 무엇을 의미 하나요?)로 구성 되며 Azure AD의 구성원이 전자 메일 사용이 가능한 개체입니다. 또한이 역할을 포함 하거나 포함할 수 없는 역할과 이름이 같은 역할 그룹을 만들 수 있습니다 (이러한 혼동 방지).

이는 Exchange 역할 그룹 모델이 발전 하는 것을 의미 합니다. 그러나 Exchange Online에는 자체 [역할 그룹 관리](https://docs.microsoft.com/exchange/permissions-exo) 인터페이스가 있습니다. Exchange Online의 일부 역할 그룹은 Azure AD 또는 Security & 준수 센터에서 잠기거나 관리 되지만, 일부 다른 이름은 동일 하거나 비슷한 이름을 가지 며 Exchange Online에서 관리 됩니다 (혼동에 추가). Exchange 관리에 대 한 범위가 필요한 경우가 아니면 Exchange Online 사용자 인터페이스를 사용 하지 않는 것이 좋습니다.

사용자 지정 역할은 만들 수 없습니다. 역할은 Microsoft에서 만든 서비스에 의해 정의 되며 새로운 서비스가 도입 됨에 따라 확장 됩니다. 이는 Azure AD의 [응용 프로그램에 정의 된 역할과](https://docs.microsoft.com/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) 유사 합니다. 새 서비스를 사용 하도록 설정 하는 경우에는 이러한 그룹에 대 한 액세스 권한을 부여 하거나 위임 하기 위해 새로운 역할 그룹이 자주 생성 되어야 합니다 (예: [참가자 위험 관리](https://docs.microsoft.com/microsoft-365/compliance/insider-risk-management-configure?view=o365-worldwide#step-1-required-enable-permissions-for-insider-risk-management)).

또한 이러한 역할 그룹에는 직접 구성원 자격이 필요 하며 Azure AD 그룹을 포함할 수 없습니다. 그러나 오늘이 역할 그룹은 Azure AD PIM에서 지원 되지 않습니다. Azure AD 역할과 마찬가지로, Api 또는 Saviynt 같은 파트너 거 버 넌 스 제품을 통해 이러한 관리를 권장 하는 것이 좋습니다.

보안 & 준수 센터 역할은 Microsoft 365으로, 이러한 역할 그룹을 환경의 하위 집합으로 범위를 지정할 수 없습니다 (Azure AD의 관리 단위와 마찬가지로). 대부분의 고객은 하위 대리인을 사용 하는 방법을 알아봅니다. 예를 들어 "EU 사용자에 대해서만 DLP 정책 만들기"를 예로 들 수 있습니다. 현재, 보안 & 준수 센터의 특정 기능에 대 한 권한이 있는 경우 테 넌 트에서이 기능에서 다루는 모든 항목에 대 한 권한이 있습니다. 그러나 대부분의 정책에는 환경 하위 집합을 대상으로 하는 기능이 포함 되어 있습니다 (예: "이러한 [레이블을](https://docs.microsoft.com/microsoft-365/compliance/create-sensitivity-labels#publish-sensitivity-labels-by-creating-a-label-policy) 이러한 사용자 에게만 제공 하도록 설정"). 적절 한 거 버 넌 스 및 통신은 충돌을 방지 하기 위한 핵심 구성 요소입니다. 일부 고객은 보안 & 준수 센터의 주소 하위 위임에 대 한 "구성 코드" 접근 방식을 구현 하는 방법을 선택 합니다. 일부 특정 서비스가 하위 위임을 지원 합니다 (아래 참조). 

Protection.office.com (보안 & 준수 센터)를 통해 현재 관리 되는 컨트롤은 security.microsoft.com 및 compliance.microsoft.com 라는 두 가지 별도의 관리 포털로 마이그레이션되는 프로세스에 있습니다. 변경 사항에 대 한 유일한 상수입니다.

### <a name="service-specific"></a>서비스 관련

앞에서 설명한 것 처럼 많은 고객은 보다 세부적인 위임 모델을 활용 하 고 있습니다. 일반적인 예: "디비전 X 사용자 및 위치에 대 한 XYZ 서비스만 관리" (또는 다른 차원)를 예로 들 수 있습니다. 이 작업을 수행 하는 기능은 각 서비스에 따라 다르며 서비스와 기능 간에 일관 되지 않습니다. 또한 각 서비스에는 별도의 RBAC 모델이 있을 수 있습니다. 이러한 모든 작업을 설명 하는 대신 (시간이 계속 소요 됨) 각 서비스에 대 한 관련 링크를 추가 합니다. 이 목록은 전체 목록이 아니며 시작 하는 것이 좋습니다.

- **Exchange Online** - [https://docs.microsoft.com/exchange/permissions-exo/permissions-exo](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) 
- **SharePoint Online** - [https://docs.microsoft.com/sharepoint/manage-site-collection-administrators](https://docs.microsoft.com/sharepoint/manage-site-collection-administrators) 
- **Microsoft 팀**  -  [https://docs.microsoft.com/microsoftteams/itadmin-readiness](https://docs.microsoft.com/microsoftteams/itadmin-readiness )
- **eDiscovery** - [https://docs.microsoft.com/microsoft-365/compliance/assign-ediscovery-permissions](https://docs.microsoft.com/microsoft-365/compliance/) 
  + **사용 권한 필터링**  -  [https://docs.microsoft.com/microsoft-365/compliance/permissions-filtering-for-content-search](https://docs.microsoft.com/microsoft-365/compliance/)
  + **준수 경계**  -  [https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries](https://docs.microsoft.com/microsoft-365/compliance/set-up-compliance-boundaries )
  + **고급 eDiscovery**  -  [https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20 )
- **Yammer** - [https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins](https://docs.microsoft.com/yammer/manage-yammer-users/manage-yammer-admins) 
- **다중 지역** - [https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin](https://docs.microsoft.com/microsoft-365/enterprise/add-a-sharepoint-geo-admin) 
- **Dynamics 365** – [https://docs.microsoft.com/dynamics365/](https://docs.microsoft.com/dynamics365/) <br>
  참고:이 링크는 설명서의 루트에 대 한 것입니다. 관리/위임 모델에는 다양 한 유형의 서비스가 있습니다.
- **전원 플랫폼**  -  [https://docs.microsoft.com/power-platform/admin/admin-documentation](https://docs.microsoft.com/power-platform/admin/admin-documentation )
  + **파워 앱**  -  [https://docs.microsoft.com/power-platform/admin/wp-security](https://docs.microsoft.com/power-platform/admin/wp-security ) <br>
    참고: 관리/위임 모델에는 다양 한 유형의 변형이 있습니다.
  + **전원 자동화**  -  [https://docs.microsoft.com/power-automate/environments-overview-admin](https://docs.microsoft.com/power-automate/environments-overview-admin )
  + **PowerBI**  -  [https://docs.microsoft.com/power-bi/service-admin-governance](https://docs.microsoft.com/power-bi/service-admin-governance ) <br>
참고: 데이터 플랫폼 보안 및 위임 (Power BI가 구성 요소)은 복잡 한 영역입니다.
- **MEM/Intune**  -  [https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control](https://docs.microsoft.com/mem/intune/fundamentals/role-based-access-control )
- 끝점에 대 **한 Microsoft Defender**  -  [https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles )
- **Microsoft 365 Defender** - [https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-permissions)
- **Microsoft Cloud App Security** - [https://docs.microsoft.com/cloud-app-security/manage-admins](https://docs.microsoft.com/cloud-app-security/manage-admins)
- **Stream**  -  [https://docs.microsoft.com/stream/assign-administrator-user-role](https://docs.microsoft.com/stream/assign-administrator-user-role )
- **정보 장벽**  -  [https://docs.microsoft.com/microsoft-365/compliance/information-barriers](https://docs.microsoft.com/microsoft-365/compliance/information-barriers )

나머지에서는 문서 검색이 매우 유용 [https://docs.microsoft.com/](https://docs.microsoft.com/microsoft-365/compliance/information-barriers) 합니다. 


### <a name="activity-logs"></a>활동 로그
Office 365에는 [통합 감사 로그가](https://docs.microsoft.com/microsoft-365/compliance/search-the-audit-log-in-security-and-compliance)있습니다. 아주 [자세한 로그](https://docs.microsoft.com/office/office-365-management-api/office-365-management-activity-api-schema)지만, 이름을 너무 많이 읽지는 않습니다. 보안 및 규정 준수 요구 사항에 필요한 모든 것이 포함 되지 않을 수 있습니다. 또한 일부 고객은 [고급 감사](https://docs.microsoft.com/microsoft-365/compliance/advanced-audit)에 관심이 있습니다. 

다른 API를 통해 액세스 하는 Microsoft 365 로그의 예는 다음과 같습니다.
- [AZURE AD](https://docs.microsoft.com/azure/azure-monitor/platform/diagnostic-settings) (Office 365와 관련 되지 않은 활동)
- [Exchange 메시지 추적](https://docs.microsoft.com/powershell/module/exchange/get-messagetrace)
- 위에서 설명한 위협/UEBA 시스템 (예: Azure AD Identity Protection, Microsoft Cloud App Security, Microsoft Defender for Endpoint 등)
- [Microsoft information protection](https://docs.microsoft.com/microsoft-365/compliance/data-classification-activity-explorer?view=o365-worldwide)
- [엔드포인트용 Microsoft Defender](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

먼저 보안 및 준수 프로그램에 필요한 모든 로그 원본을 확인 해야 합니다. 또한 각 로그의 온라인 보존 제한이 서로 다릅니다. 

관리 위임 측면에서 보면 대부분의 Microsoft 365 활동 로그에는 기본적으로 제공 되는 RBAC 모델이 없습니다. 로그를 볼 수 있는 권한이 있는 경우에는 그 안에 있는 모든 항목을 보는 것이 좋습니다. 고객 요구 사항의 일반적인 예로는 "EU 사용자에 대 한 작업만 쿼리할 수 있습니다." (또는 다른 차원)가 있습니다. 이 요구 사항을 충족 하려면 로그를 다른 서비스로 전송 해야 합니다. Microsoft 클라우드에서 [Azure 센티널](https://docs.microsoft.com/azure/sentinel/overview) 또는 [Log Analytics](https://docs.microsoft.com/azure/azure-monitor/learn/quick-create-workspace)로이를 전송 하는 것이 좋습니다. 

높은 수준의 다이어그램:

![로그 흐름에 대 한 높은 수준의 다이어그램](../media/solutions-architecture-center/identity-beyond-illustration-4.png)  

위의 다이어그램은 이벤트 허브 및/또는 azure 저장소 및/또는 Azure Log Analytics에 로그를 전송 하는 기본 제공 기능을 나타냅니다. 일부 시스템에는이 기본 제공 기능이 포함 되어 있지 않습니다. 하지만 이러한 로그를 동일한 저장소로 보내는 다른 방법도 있습니다. 예를 들어 [Azure 센티널로 팀 보호](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)를 참조 하세요.

모든 로그를 하나의 저장소 위치로 결합 하면 상호 상관 관계, 사용자 지정 보존 시간, RBAC 모델을 지 원하는 데 필요한 데이터를 사용 하는 등의 추가 이점이 있습니다. 이 저장소 시스템에 데이터가 있으면 적절 한 RBAC 모델을 사용 하 여 PowerBI 대시보드 또는 다른 유형의 시각화를 만들 수 있습니다.

로그를 한 곳으로만 보낼 필요는 없습니다. 또한 [Microsoft Cloud App Security과 Office 365 로그](https://docs.microsoft.com/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 를 통합 하는 것이 좋을 수도 있고 [power BI](https://docs.microsoft.com/microsoft-365/admin/usage-analytics/usage-analytics?view=o365-worldwide)의 사용자 지정 RBAC 모델과도 동일한 문제가 있을 수 있습니다. 저장소 마다 장단점이 있고 대상은 다릅니다.

[Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection?view=o365-worldwide)라는 서비스에서 보안, 위협, 취약성 등을 위한 매우 다양 한 기본 제공 분석 시스템이 있다는 것을 언급할 필요가 있습니다.

많은 대규모 고객이이 로그 데이터를 타사 시스템 (예: SIEM)으로 전송 하려고 합니다. 이에 대 한 다른 방식은 서로 다르지만 일반적인 [Azure 이벤트 허브](https://docs.microsoft.com/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) 와 [그래프](https://docs.microsoft.com/graph/security-integration) 는 출발점으로 사용 하는 것이 좋습니다.


### <a name="azure"></a>Azure 
Azure AD, Azure 및 SaaS 사이에 높은 권한 역할을 분리 하는 방법이 있는지 묻는 메시지가 종종 있습니다 (예: 전역 관리자 for Office 365 (Azure 아님).  설마.  여러 테 넌 트 아키텍처는 필요한 관리 분리가 필요 하지만 상당한 [복잡도](https://aka.ms/multi-tenant-user) (위 참조)를 추가 하는 경우에 필요 합니다. 이러한 모든 서비스는 동일한 보안/id 경계에 속하며 위의 계층 구조 모델을 확인 합니다.  

같은 테 넌 트에 있는 다양 한 서비스 간의 관계를 이해 하는 것이 중요 합니다. 저는 Azure, Office 365 및 Power Platform (그리고 온-프레미스 및 타사 클라우드 서비스)에 걸친 비즈니스 솔루션을 구축 하는 여러 고객을 대상으로 작업 하 고 있습니다. 일반적인 예는 다음과 같습니다. 
-   문서/이미지 집합에서 공동 작업 하려고 함 (Office 365)
-   승인 프로세스를 통해 각 사용자 보내기 (전원 플랫폼)
-   모든 구성 요소가 승인 되 면이를 통합 결과물 (Azure)로 어셈블합니다. [Microsoft GRAPH API](https://docs.microsoft.com/azure/active-directory/develop/microsoft-graph-intro) 는 이러한 경우에 가장 적합 한 친구입니다.  [여러 테 넌 트](https://docs.microsoft.com/azure/active-directory/develop/single-and-multi-tenant-apps)에 걸친 솔루션을 디자인 하는 것은 불가능 하지만 훨씬 더 복잡 합니다.

RBAC (azure Role-Based 액세스 제어)를 사용 하면 Azure에 세분화 된 액세스 관리를 사용할 수 있습니다. RBAC를 사용 하면 사용자에 게 작업을 수행 하는 데 필요한 최소한의 사용 권한을 부여 하 여 리소스에 대 한 액세스를 관리할 수 있습니다. 세부 정보는이 문서의 범위를 벗어나지만 RBAC에 대 한 자세한 내용은 [Azure의 rbac (역할 기반 액세스 제어](https://docs.microsoft.com/azure/role-based-access-control/overview) ) 란?를 참조 하세요. RBAC는 중요 하지만 Azure에 대 한 거 버 넌 스 고려 사항 중 일부에 불과합니다. [클라우드 채택 프레임 워크](https://docs.microsoft.com/azure/cloud-adoption-framework/govern/) 는 더 자세히 알아볼 수 있는 좋은 출발점입니다. 내 친구와 Res Ravinet가 방법을 결정 하기 위해 다양 한 구성 요소를 통해 고객을 단계별로 안내 합니다. 다음은 실제 고객 모델에 액세스할 수 있는 프로세스 만큼 좋은 것이 아니라 다양 한 요소에 대 한 높은 수준의 보기입니다.

![위임 된 관리를 위한 Azure 구성 요소의 고급 보기](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

위의 그림에서 볼 수 있듯이 대부분의 다른 서비스는 디자인의 일부로 간주 해야 합니다 (예: [Azure 정책](https://docs.microsoft.com/azure/governance/policy/overview), [azure 청사진](https://docs.microsoft.com/azure/governance/blueprints/overview), [관리 그룹](https://docs.microsoft.com/azure/governance/management-groups/)등).

## <a name="conclusion"></a>결론
짧은 요약으로 시작 됨, 예상 보다 더 오래 완료 되었습니다.  이제 조직의 위임 모델을 만드는 방법에 대해 자세히 살펴보겠습니다.  이 대화는 고객에 게 흔히 발생 합니다. 모든 사용자에 대해 작동 하는 모델은 없습니다. 고객 들에 게 표시 되는 일반적인 패턴을 문서화 하기 전에 Microsoft 기술팀에서 계획 된 몇 가지 향상을 기다리는 중입니다. 또한 Microsoft 계정 팀과 협력 하 여 가장 가까운 [Microsoft 기술 센터로](https://www.microsoft.com/mtc)의 방문을 배열할 수 있습니다.  거기가 표시 됩니다.


