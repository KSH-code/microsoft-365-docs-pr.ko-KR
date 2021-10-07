---
title: Microsoft 365 Enterprise 자원 계획 - 보안 아키텍처
description: Microsoft의 기술 수석 설계자인 Alex Shteynberg의 Microsoft Enterprise 아키텍처에 대한 주요 디자인 전략에 대해 자세히 알아보세요.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: seo-marvel-jun2020
f1.keywords: NOCSH
ms.openlocfilehash: 8dd5b5f94a8c418cc8d077d785c73c968c40c3bc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60202372"
---
# <a name="to-identity-and-beyondone-architects-viewpoint"></a>ID 및 그 이상을 아우르는 설계자의 관점

이 문서에서는 Microsoft의 수석 기술 설계자인 [Alex Shteynberg가](https://www.linkedin.com/in/alex-shteynberg/)비즈니스 및 기타 Microsoft 클라우드 서비스를 채택하는 기업 조직을 Microsoft 365 주요 디자인 전략에 대해 논의합니다.

## <a name="about-the-author"></a>만든 이 정보

![Alex Shteynberg 사진.](../media/solutions-architecture-center/identity-and-beyond-alex-shteynberg.jpg)

뉴욕 Microsoft 기술 센터의 수석 기술 [설계자입니다.](https://www.microsoft.com/mtc?rtc=1) 대부분 대규모 고객 및 복잡한 요구 사항과 함께 작업합니다. 내 관점과 의견은 이러한 상호 작용을 기반으로 하여 일부 상황에는 적용되지 않을 수 있습니다. 그러나 내 경험에서 가장 복잡한 문제를 고객에게 도움을 줄 수 있는 경우 모든 고객을 지원할 수 있습니다.

일반적으로 매년 100명 이상의 고객과 작업합니다. 모든 조직에는 고유한 특성이 있겠지만 추세와 공통성은 흥미로운 점입니다. 예를 들어 한 가지 추세는 많은 고객에 대한 업계 간 관심입니다. 결국 은행 지점은 커피숍과 커뮤니티 센터도 될 수 있습니다.

내 역할에서는 고객이 고유한 비즈니스 목표 집합을 해결하기 위한 최상의 기술 솔루션을 터득하는 데 집중하고 있습니다. 공식적으로는 ID, 보안, 개인 정보 보호 및 규정 준수에 집중합니다. 이러한 터치는 우리가 하는 모든 것을 좋아합니다. 대부분의 프로젝트에 참여할 수 있는 기회를 제공합니다. 이렇게 하여 많은 분들이 이 역할을 즐길 수 있습니다.

뉴욕시(최고)에 거주하며 문화, 식 및 사람(교통이 아닐 때)의 다양성을 즐길 수 있습니다. I love to travel when I can and hope to see most of the world in my lifetime. 현재 아프리카 여행에 대해 조사 중이라서 와일드카드에 대해 알아보고 있습니다.

## <a name="guiding-principles"></a>Guiding principles

- **단순성은 종종 더** 좋습니다. 기술로 (거의) 모든 작업을 할 수 있지만 그렇게 해야 하는 것은 아니며, 특히 보안 공간에서 많은 고객이 솔루션을 과도하게 관리합니다. Google의 [스트라이프](https://www.youtube.com/watch?v=SOQgABDSYZE) 회의에서 이 점의 밑줄로 이 비디오를 시청하고 있습니다.
- **사람, 프로세스, 기술:** [먼저](https://en.wikipedia.org/wiki/Human-centered_design) 기술이 아닌 프로세스를 개선할 수 있는 사람 디자인입니다. "완벽한" 해결 방법도 있습니다. 다양한 위험 요소의 균형을 조정해야 하며 각 비즈니스에 따라 결정이 다릅니다. 너무 많은 고객이 나중에 사용자가 피하는 접근 방식을 디자인합니다.
- **'이유' 첫** 번째 및 '방법' 이후 중점: 100만 명이 넘는 질문을 하는 성가신 7-yr 노인이 될 수 있습니다. 질문할 올바른 질문을 모르는 경우 올바른 답변에 도착할 수 없습니다. 많은 고객이 비즈니스 문제를 정의하는 대신 작업 방식에 대해 가정합니다. 항상 여러 경로를 사용할 수 있습니다.
- **과거의** 모범 사례에 대한 긴 tail: 모범 사례가 빠른 속도로 변화하고 있습니다. Azure AD를 3개월 이상 살펴보면 최신이 아를 수 있습니다. 여기에 있는 모든 것은 게시 후 변경될 수 있습니다. 현재 "최상의" 옵션은 현재와 6개월이 같지 않을 수 있습니다.

## <a name="baseline-concepts"></a>기준 개념

이 섹션을 건너뛰지 않습니다. 수년 동안 클라우드 서비스를 사용해온 고객에게도 이러한 항목으로 돌아가야 하는 경우가 종종 있습니다.
Alas, language isn't a precise tool. 종종 동일한 단어를 사용하여 다른 개념을 의미하거나 다른 단어를 사용하여 동일한 개념을 의미합니다. 아래 다이어그램을 사용하여 몇 가지 기준 용어와 "계층 구조 모델"을 설정하는 경우가 종종 있습니다.
<br><br>

![테넌트, 구독, 서비스 및 데이터의 그림입니다.](../media/solutions-architecture-center/Identity-and-beyond-tenant-level.png)

<br>

배정을 배워보는 것을 배워보는 것이 좋겠고, 풀에서 시작하는 것이 좋습니다. 이 다이어그램을 사용하여 기술적으로 정확하지는 않습니다. 몇 가지 기본 개념을 논의하는 모델입니다.

다음은 이 다이어그램에 대한 설명입니다.

- 테넌트 = Azure AD의 인스턴스입니다. 계층 구조의 "맨 위" 또는 다이어그램의 수준 1에 있습니다. 이 경계는 다른 모든 것이 발생하는["](/azure/active-directory/users-groups-roles/licensing-directory-independence)경계"[(Azure AD B2B를 아는](/azure/active-directory/b2b/what-is-b2b) 것)로 고려할 수 있습니다. 모든 Microsoft 엔터프라이즈 클라우드 서비스는 이러한 테넌트 중 하나에 해당합니다. 소비자 서비스는 별도입니다. "테넌트"는 문서에 Office 365, Azure 테넌트, WVD 테넌트 등으로 표시됩니다. 이러한 변형으로 인해 고객에게 혼동을 일으킬 수 있는 경우가 종종 있습니다.
- 다이어그램의 수준 2인 서비스/구독은 하나의 테넌트에만 속합니다. 대부분의 SaaS 서비스는 1:1로 마이그레이션하지 않고는 이동할 수 없습니다. Azure는 다르며, [](/azure/cost-management-billing/manage/billing-subscription-transfer) 청구 및/또는 구독을 다른 테넌트로 [이동할](/azure/active-directory/fundamentals/active-directory-how-subscriptions-associated-directory) 수 있습니다. Azure 구독을 이동해야 하는 고객은 많이 있습니다. 이 경우 다양한 의미가 있습니다. 구독 외부에 있는 개체(예: 역할 기반 액세스 제어 또는 Azure RBAC 및 그룹, 앱, 정책 등의 Azure AD 개체)는 이동하지 않습니다. 또한 일부 서비스(예: Azure Key Vault, 데이터 블록 등) 비즈니스에 도움이 필요한 서비스를 마이그레이션하지 않습니다. 마이그레이션에 도움이 될 수 있는 일부 스크립트는 에서 [GitHub.](https://github.com/lwajswaj/azure-tenant-migration)
- 일반적으로 주어진 서비스에는 일종의 "하위 수준" 경계 또는 수준 3(L3)이 있습니다. 이는 보안, 정책, 거버넌스 등의 세분화에 대해 이해하는 데 유용합니다. 안타깝게도 알고 있는 uniform 이름이 없습니다. L3의 몇 가지 예는 다음과 같습니다. Azure Subscription = [resource](/azure/azure-resource-manager/management/manage-resources-portal); Dynamics 365 CE = [인스턴스](/dynamics365/admin/new-instance-management); Power BI = [작업 영역](/power-bi/service-create-the-new-workspaces); Power Apps = [environment](/power-platform/admin/environments-overview); 등.
- 수준 4는 실제 데이터가 있는 위치입니다. 이 '데이터 평면'은 복잡한 항목입니다. RBAC에 Azure AD를 사용하는 서비스도 있습니다. 위임 항목에 대해 설명할 것입니다.

많은 고객(및 Microsoft 직원)이 혼동하거나 이에 대한 질문이 있는 몇 가지 추가 개념은 다음과 같습니다.

- 누구나 [비용으로](/azure/active-directory/fundamentals/active-directory-access-create-new-tenant) 많은 테넌트를 [만들 수 있습니다.](https://azure.microsoft.com/pricing/details/active-directory/) 서비스 내에 프로비전된 서비스가 필요하지 않습니다. 수십 개가 있습니다. 각 테넌트 이름은 Microsoft의 전 세계 클라우드 서비스에서 고유합니다(즉, 두 테넌트의 이름이 같을 수 없음). 모두 형식이 TenantName.onmicrosoft.com. 테넌트(관리되지 않는 테넌트)를 자동으로[만드는 프로세스도 있습니다.](/azure/active-directory/users-groups-roles/directory-self-service-signup) 예를 들어 사용자가 다른 테넌트에 없는 전자 메일 도메인을 사용하여 엔터프라이즈 서비스에 등록할 때 이 문제가 발생할 수 있습니다.
- 관리되는 테넌트에서 많은 [DNS](/azure/active-directory/fundamentals/add-custom-domain) 도메인을 등록할 수 있습니다. 원래 테넌트 이름은 변경되지 않습니다. 현재 마이그레이션 외의 방법으로 테넌트 이름을 쉽게 이름을 정할 수 있는 방법은 없습니다. 기술적으로 테넌트 이름이 중요한 것은 아니며 일부에서는 이 이름이 제한적일 수 있습니다.
- 아직 서비스를 배포할 계획이 없는 경우에도 조직의 테넌트 이름을 예약해야 합니다. 그렇지 않으면 누군가가 이를 사용자로부터 받아들일 수 있으며 이를 되돌리기 간단한 프로세스가 없습니다(DNS 이름과 동일한 문제). 고객으로부터 너무 자주 듣게 됩니다. 테넌트 이름에 대한 토론 항목도 있습니다.
- DNS 네임스페이스를 소유하고 있는 경우 테넌트에 이러한 모든 네임스페이스를 추가해야 합니다. 그렇지 않으면 이 [](/azure/active-directory/users-groups-roles/directory-self-service-signup) 이름으로 관리되지 않는 테넌트가 만들어질 수 있습니다. 그러면 관리되지 않는 테넌트가 [관리되지 않습니다.](/azure/active-directory/users-groups-roles/domains-admin-takeover)
- DNS 네임스페이스(예: contoso.com)는 하나의 테넌트에만 속할 수 있습니다. 이는 다양한 시나리오(예: 합병 또는 인수 중에 전자 메일 도메인 공유 등)에 의미가 있습니다. 다른 테넌트에 DNS 하위(예: div.contoso.com)를 등록하는 방법이 있지만 이렇게 하면 안 됩니다. 최상위 도메인 이름을 등록하면 모든 하위 도메인이 동일한 테넌트에 속하는 것으로 가정됩니다. 다중 테넌트 시나리오(아래 참조)에서는 일반적으로 다른 최상위 도메인 이름(예: contoso.ch 또는 도메인 이름)을 ch-contoso.com.
- Who "소유"해야 하나요? 현재 테넌트의 소유주를 모르는 고객을 종종 볼 수 있습니다. 이는 큰 빨강 플래그입니다. Microsoft 지원 ASAP에 문의합니다. 서비스 소유자(종종 Exchange 관리자)가 테넌트 관리로 지정되어 있는 경우와 처럼 문제가 될 수 있습니다. 테넌트에는 향후 원하는 모든 서비스가 포함되어 있습니다. 테넌트 소유자는 조직의 모든 클라우드 서비스 사용에 대해 결정을 내릴 수 있는 그룹입니다. 또 다른 문제는 테넌트 소유자 그룹에 모든 서비스를 관리해야 하는 경우입니다. 대규모 조직에서는 확장되지 않습니다.
- 하위/슈퍼 테넌트에 대한 개념이 없는 경우 어떤 이유로 이 신화는 계속 반복됩니다. Azure AD [B2C](/azure/active-directory-b2c/) 테넌트에도 적용됩니다. "내 B2C 환경이 내 XYZ 테넌트에 있습니다." 또는 "Azure 테넌트를 내 테넌트로 이동하는 Office 365?"
- 이 문서는 대부분 대부분의 고객이 사용 중이기 때문에 상업용 전 세계 클라우드에 초점을 맞추고 있습니다. 때때로 주권 클라우드에 대해 [알아 두는 것이 유용할 수 있습니다.](/azure/active-directory/develop/authentication-national-cloud) Sovereign clouds have additional implications to discuss which are out of this discussion.

## <a name="baseline-identity-topics"></a>기준 ID 항목

Azure AD(Azure AD)에 대한 많은 설명서가 microsoft의 ID 플랫폼에 Azure Active Directory 있습니다. 방금 시작한 이들에게는 종종 압도적인 느낌이 들 수 있습니다. 학습한 후에도 지속적인 혁신과 변경을 유지하는 것은 어려울 수 있습니다. 고객 상호 작용에서 종종 비즈니스 목표와 이러한 문제를 해결하기 위한 "좋음, 더 좋음, 최상의" 접근 방법(및 이러한 항목에 대한 사람 "절제 메모") 간의 "번역자"를 발견합니다. 완벽한 답변은 거의 없습니다. "올바른" 결정은 다양한 위험 요소의 균형을 이루는 것입니다. 다음은 고객과 논의하는 경향이 있는 몇 가지 일반적인 질문과 혼동 영역입니다.

### <a name="provisioning"></a>프로비전

Azure AD는 ID 세계에서 거버넌스가 부족한 문제를 해결하지 못합니다. [ID 거버넌스는](/azure/active-directory/governance/identity-governance-overview) 클라우드 결정과는 독립적인 중요한 요소입니다. 거버넌스 요구 사항은 시간이 경과할 때 변경됩니다. 이는 도구가 아닌 프로그램인 이유입니다.

[Azure AD 커넥트](/azure/active-directory/hybrid/whatis-azure-ad-connect) [(Microsoft Identity Manager)](/microsoft-identity-manager/microsoft-identity-manager-2016) 및 다른 MIM(타사 또는 사용자 지정)? 지금이나 앞으로도 많은 두통을 에워두고 Azure AD 2013으로 커넥트. 이 도구에는 고객 특유의 구성과 지속적인 혁신을 해결하기 위한 모든 종류의 스마트가 있습니다.

좀 더 복잡한 아키텍처로 구동될 수 있는 몇 가지 에지 사례:

- 이러한 포리스트 간에 네트워크 연결이 없는 여러 AD 포리스트가 있습니다. 클라우드 프로비전이라는 [새로운 옵션이 있습니다.](/azure/active-directory/cloud-provisioning/what-is-cloud-provisioning)
- Active Directory가 없으며 설치하지도 않습니다. Azure AD 커넥트 [LDAP에서](/azure/active-directory/hybrid/plan-hybrid-identity-design-considerations-tools-comparison) 동기화하도록 구성할 수 있습니다(파트너가 요구될 수 있습니다).
- 동일한 개체를 여러 테넌트에 프로비전해야 합니다. 이는 기술적으로 지원되지 않지만 "동일"의 정의에 따라 다를 수 있습니다.

기본 동기화[규칙(필터](/azure/active-directory/hybrid/how-to-connect-sync-configure-filtering) [개체,](/azure/active-directory/hybrid/reference-connect-sync-attributes-synchronized)특성 변경, 대체 로그인 [ID](/azure/active-directory/hybrid/plan-connect-userprincipalname)등)을 사용자 지정해야 하나요? 피하세요! ID 플랫폼은 플랫폼을 사용하는 서비스만큼만 가치가 있습니다. 모든 종류의 너티 구성을 할 수 있는 동안 이 질문에 대답하려면 응용 프로그램에 미치는 영향을 살펴보아야 합니다. 메일 사용이 가능한 개체를 필터링하는 경우 온라인 서비스의 GAL이 불완전합니다. 응용 프로그램이 특정 특성에 의존하는 경우 이러한 특성을 필터링하면 예측할 수 없는 영향을 미치게 됩니다. 등. 이는 ID 팀 결정이 아니기도 합니다.

XYZ SaaS는 JIT(Just-In-Time) 프로비저닝을 지원하고 동기화해야 하는 이유는 무엇입니까? 위 내용을 참조하세요. 많은 응용 프로그램에서는 기능을 위해 "프로필" 정보가 필요합니다. 모든 메일 사용이 가능한 개체를 사용할 수 없는 경우 GAL을 사용할 수 없습니다. Azure [AD와 통합된](/azure/active-directory/app-provisioning/user-provisioning) 응용 프로그램의 사용자 프로비전에도 마찬가지입니다.

### <a name="authentication"></a>인증

[PHS(암호 해시](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization) 동기화) 및 PTA(통과 인증) [](/azure/active-directory/hybrid/how-to-connect-fed-compatibility)및 페더전 . [](/azure/active-directory/hybrid/how-to-connect-pta-how-it-works)

일반적으로 페더미스에 대한 열렬한 의욕적인 란이 있습니다. [](/azure/active-directory/hybrid/choose-ad-authn) 일반적으로 더 간단하므로 사용하지 않을 이유가 없는 한 PHS를 사용하는 것이 좋습니다. 동일한 테넌트의 여러 DNS 도메인에 대해 서로 다른 인증 방법을 구성할 수도 있습니다.

일부 고객은 페더ation + PHS를 주로 사용할 수 있습니다.

- 페더ation 서비스를 [사용할](/azure/active-directory/hybrid/plan-migrate-adfs-password-hash-sync) 수 없는 경우(재해 복구용)로 되돌아가기 위한 옵션입니다.
- 추가 기능(예: [Azure AD DS)](/azure/active-directory-domain-services/tutorial-configure-password-hash-sync)및 보안 서비스(예: [유출된 자격 증명)](/azure/active-directory/reports-monitoring/concept-risk-events#leaked-credentials)
- 페더타 인증을 이해하지 않는 Azure의 서비스(예: [Azure Files)가 지원됩니다.](/azure/storage/files/storage-files-active-directory-overview)

종종 일부 오해를 명확히하기 위해 클라이언트 인증 흐름을 진행합니다. 결과는 아래 그림처럼 보입니다. 이 그림은 대화형 프로세스만큼 좋지 않습니다.

![화이트보드 대화 예제.](../media/solutions-architecture-center/identity-beyond-whiteboard-example.png)

이 유형의 화이트보드 그리기에서는 인증 요청 흐름 내에서 보안 정책이 적용되는 위치를 보여 주며, 이 예에서는 AD FS(Active Directory Federation Service)를 통해 적용된 정책이 첫 번째 서비스 요청에 적용되지만 후속 서비스 요청에는 적용되지 않습니다. 이는 적어도 한 가지 이유 때문에 보안 제어를 최대한 클라우드로 이동해야 합니다.

기억할 수 있는 한 SSO(Single [Sign-On)를](/azure/active-directory/manage-apps/what-is-single-sign-on) 추격해오고 있습니다. 일부 고객은 "올바른" STS(페더링) 공급자를 선택하여 이를 달성할 수 있습니다. Azure AD는 [SSO](/azure/active-directory/manage-apps/plan-sso-deployment) 기능을 활성화하는 데 크게 도움이 될 수 있지만 STS는 마법적이지 않습니다. 중요한 응용 프로그램에 여전히 사용되는 "레거시" 인증 방법이 너무 많이 있습니다. 파트너 솔루션으로 Azure [AD를 확장하면](/azure/active-directory/saas-apps/tutorial-list) 이러한 많은 시나리오를 해결할 수 있습니다. SSO는 전략이자 여정입니다. 응용 프로그램에 대한 표준으로 이동하지 않고는 이 [을(를) 사용할 수 없습니다.](/azure/active-directory/develop/v2-app-types) 이 항목과 관련된 것은 [](/azure/active-directory/authentication/concept-authentication-passwordless) 암호 없는 인증에 대한 여정으로, 마법의 해가 없습니다.

[MFA(다단계](/azure/active-directory/authentication/concept-mfa-howitworks) 인증)는 현재 필수적입니다(자세한 내용은[여기를](https://techcommunity.microsoft.com/t5/azure-active-directory-identity/your-pa-word-doesn-t-matter/ba-p/731984) 클릭). 사용자 동작 [분석에](/azure/active-directory/authentication/tutorial-risk-based-sspr-mfa) 추가하고 가장 일반적인 사이버 공격을 방지하는 솔루션이 있습니다. 소비자 서비스도 MFA를 요구하기 위해 이동하고 있습니다. 하지만 최신 인증 접근 방식으로 이동하지 않는 많은 고객과 [여전히 만나고](../enterprise/hybrid-modern-auth-overview.md) 있습니다. 가장 큰 인수는 사용자 및 레거시 응용 프로그램에 영향을 줄 것 입니다. 때때로 좋은 킥은 고객이 변경 사항을 Exchange Online [도움이 될 수 있습니다.](https://techcommunity.microsoft.com/t5/exchange-team-blog/basic-auth-and-exchange-online-february-2020-update/ba-p/1191282) 이제 다양한 Azure [AD](/azure/active-directory/fundamentals/concept-fundamentals-block-legacy-authentication) 보고서를 통해 고객이 이러한 전환을 지원할 수 있습니다.

### <a name="authorization"></a>권한 부여

[Wikipedia에 따라](https://en.wikipedia.org/wiki/Authorization)"승인"은 액세스 정책을 정의하는 것입니다. 많은 사람들이 개체(파일, 서비스 등)에 대한 액세스 컨트롤을 정의하는 능력으로 봐야 합니다. 현재 사이버 위협 세계에서 이 개념은 다양한 위협 벡터에 반응하고 이에 대응하여 액세스 제어를 신속하게 조정할 수 있는 동적 정책으로 빠르게 진화하고 있습니다. 예를 들어 비정상적인 위치에서 은행 계좌에 액세스하면 추가 확인 단계가 나타납니다. 이를 위해 정책 자체가 아니라 위협 감지 및 신호 상관 관계 방법론의 에코시스템을 고려해야 합니다.

Azure AD의 정책 엔진은 조건부 액세스 정책을 [사용하여 구현됩니다.](/azure/active-directory/conditional-access/overview) 이 시스템은 동적인 의사 결정을 내리기 위해 다른 다양한 위협 감지 시스템의 정보에 의존합니다. 간단한 보기는 다음 그림과 같습니다.

![Azure AD의 정책 엔진입니다.](../media/solutions-architecture-center/identity-and-beyond-illustration-3.png)

이러한 모든 신호를 결합하면 다음과 같은 동적 정책을 사용할 수 있습니다.

- 장치에서 위협이 감지되면 데이터에 대한 액세스는 다운로드할 수 없는 웹으로만 줄어듭니다.
- 비정상적으로 많은 볼륨의 데이터를 다운로드하는 경우 다운로드하는 모든 것이 암호화되고 제한됩니다.
- 관리되지 않는 장치에서 서비스에 액세스하는 경우 매우 중요한 데이터로부터 차단되지만 다른 위치에 복사할 수 없는 제한된 데이터에 액세스할 수 있습니다.

이 확장된 권한 부여 정의에 동의하는 경우 추가 솔루션을 구현해야 합니다. 구현하는 솔루션은 정책의 동적인 방식과 우선 순위를 지정하려는 위협에 따라 결정됩니다. 이러한 시스템의 몇 가지 예는 다음과 같습니다.

- [Azure AD ID 보호](/azure/active-directory/identity-protection/)
- [Microsoft Defender for Identity](/azure-advanced-threat-protection/)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [Office 365용 Microsoft Defender](../security/office-365-security/defender-for-office-365.md)
- [](/cloud-app-security/) Microsoft Cloud App Security(MCAS)
- [Microsoft 365 Defender](../security/defender/microsoft-365-defender.md)
- [Microsoft Intune](/mem/intune/)
- [](../compliance/information-protection.md) Microsoft Information Protection(MIP)
- [Azure Sentinel](/azure/sentinel/)

물론 Azure AD 외에도 다양한 서비스 및 응용 프로그램에는 자체적인 특정 권한 부여 모델이 있습니다. 이러한 중 일부는 위임 섹션의 나중에 설명합니다.

### <a name="audit"></a>감사

Azure AD에는 자세한 감사 [및 보고 기능이](/azure/active-directory/reports-monitoring/) 있습니다. 그러나 일반적으로 보안 결정을 내리는 데 필요한 정보의 원본은 이뿐이 않습니다. 위임 섹션에서 자세한 설명을 참조하세요.

## <a name="theres-no-exchange"></a>이 Exchange

당황하지 마! 이는 더 Exchange(또는 SharePoint 등)를 의미하지는 않습니다. 여전히 핵심 서비스입니다. 지금까지 기술 공급자는 여러 서비스의 구성 요소를 포함하도록 UX(사용자 환경)를 전환하고 있습니다. 이 Microsoft 365 간단한 예로는[전자](https://support.office.com/article/Attach-files-or-insert-pictures-in-Outlook-email-messages-BDFAFEF5-792A-42B1-9A7B-84512D7DE7FC)메일의 첨부 파일이 SharePoint Online 또는 비즈니스용 OneDrive.

![전자 메일에 파일 첨부](../media/solutions-architecture-center/modern-attachments.png)

Outlook 클라이언트를 보고, 이 환경의 일부로 "연결"하는 많은 서비스를 볼 수 Exchange. 여기에는 Azure AD, Microsoft Search, 앱, 프로필, 규정 준수 및 Office 365 포함됩니다.

![Outlook 인터페이스입니다.](../media/solutions-architecture-center/identity-and-beyond-conceptual-screenshot.png)

예정된 [Microsoft Fluid Framework](https://techcommunity.microsoft.com/t5/microsoft-365-blog/microsoft-ignite-blog-microsoft-fluid-framework-preview/ba-p/978268) 미리 보기에 대한 자세한 내용을 읽어 읽습니다. 이제 미리 보기에서 직접 Teams 읽고 회신할 수 Outlook. 실제로 Teams [](https://products.office.com/microsoft-teams/download-app) 클라이언트는 이 전략의 보다 두드러진 예 중 하나입니다.

전반적으로 Microsoft 클라우드의 다른 서비스와 Office 365 명확한 선을 그리는 것이 점점 더 어려워지고 있습니다. 고객이 구성 요소를 하나만 사용 경우에도 모든 작업을 혁신적으로 이행할 수 있는 이점을 고객에게는 큰 혜택으로 보고 있습니다. 매우 멋지며 많은 고객에게는 의미가 있습니다.

현재 많은 고객 IT 그룹이 "제품"을 중심으로 구성됩니다. 각 특정 제품에 대한 전문가가 필요하기 때문에 이 방식은 사내에 논리적입니다. 그러나 이러한 서비스가 클라우드로 이동되어 Active Directory 또는 Exchange 데이터베이스를 다시 디버그할 수 없습니다. 자동화(클라우드 종류)는 특정 반복적인 수동 작업을 제거합니다(팩터리에 어떤 일이 발생했습니다. 그러나 이러한 요구 사항은 서비스 간 상호 작용, 영향, 비즈니스 요구 사항 등 이해하기 위한 보다 복잡한 요구 사항으로 대체되었습니다. 원하는 경우 클라우드 [](/learn/)변환을 통해 사용할 수 있는 좋은 기회가 있습니다. 기술로 이동하기 전에 IT 기술 및 팀 구조의 변경 관리에 대해 고객에게 자주 이야기합니다.

모든 SharePoint 팬과 개발자에게 "온라인에서 XYZ를 어떻게 해야 SharePoint?" 를 중지하세요. [워크플로에](/power-automate/) Power Automate(또는 Flow)를 사용하는 것이 훨씬 더 강력한 플랫폼입니다. [Azure Bot Framework를](/azure/bot-service/) 사용하여 500 K 항목 목록에 대한 더 나은 UX를 만들 수 있습니다. CSOM Graph [Microsoft](https://developer.microsoft.com/graph/) 2013을 사용하여 시작하세요. [Microsoft Teams](/MicrosoftTeams/Teams-overview) 포함된 SharePoint 세계도 포함됩니다. 나열할 수 있는 다른 많은 예제가 있습니다. 이 공간에는 방대하고 멋진 은하수도 있습니다. 문을 열고 [탐색을 시작해 을 탐색합니다.]()

다른 일반적인 영향은 규정 준수 영역에 있습니다. 이 서비스 간 접근 방식은 많은 규정 준수 정책을 완전히 혼동하는 것으로 보입니다. "모든 전자 메일 통신을 eDiscovery 시스템으로 저널링해야 합니다."라는 조직을 계속 보고 있습니다. 전자 메일이 더 이상 전자 메일이 아니라 다른 서비스에 대한 창이면 어떤 의미입니까? Office 365 규정 준수에 대한 포괄적인 접근 방식이 [있지만,](../compliance/index.yml)사람 및 프로세스 변경은 기술보다 훨씬 더 어려운 경우가 종종 있습니다.

다른 많은 사람이 있으며 프로세스에 의미가 있습니다. 이 영역은 중요하고 논의된 영역입니다. 다른 문서에서 더 많은 문서가 추가된 것일 수 있습니다.

## <a name="tenant-structure-options"></a>테넌트 구조 옵션

### <a name="single-tenant-vs-multi-tenant"></a>단일 테넌트 및 다중 테넌트

일반적으로 대부분의 고객은 프로덕션 테넌트가 하나만 있습니다. 여러 테넌트가 어려운 이유는 여러 가지가 있습니다(검색을 [Bing)](https://www.bing.com/search?q=office%20365%20multiple%20tenants)또는 이 백서 [를 읽습니다.](https://aka.ms/multi-tenant-user) 동시에 함께 작업하는 많은 엔터프라이즈 고객은 IT 학습, 테스트 및 실험을 위한 다른 (소규모) 테넌트가 있습니다. [Azure Lighthouse를](https://azure.microsoft.com/services/azure-lighthouse/)사용하여 테넌트 간 Azure 액세스를 더 쉽게 할 수 있습니다. Office 365 기타 많은 SaaS 서비스에는 테넌트 간 시나리오에 대한 제한이 있습니다. [Azure AD B2B](/azure/active-directory/b2b/what-is-b2b) 시나리오에서는 여러 가지를 고려해야 합니다.

인수 합병(M&A)한 후 많은 고객이 여러 프로덕션 테넌트에 종결하게 되어 통합을 원합니다. 오늘날 단순한 것은 아니며 MCS(Microsoft Consulting Services) 또는 파트너 및 타사 소프트웨어가 필요할 것입니다. 향후 다중 테넌트 고객과의 다양한 시나리오를 해결하기 위한 지속적인 엔지니어링 작업도 진행 중입니다.

일부 고객은 두 개 이상의 테넌트와 함께 이동하기로 선택했습니다. 이는 매우 신중한 결정이야 하며 거의 항상 비즈니스 이유를 결정해야 합니다. 몇 가지 예는 다음과 같습니다.

- 서로 다른 엔터티 간에 쉬운 공동 작업이 필요하지 않을 뿐만 아니라 강력한 관리 및 기타 분리 요구가 있는 보유 유형 회사 구조입니다.
- 인수 후 두 엔터티를 분리하기 위한 비즈니스 결정이 결정됩니다.
- 고객의 프로덕션 환경을 변경하지 않는 고객 환경 시뮬레이션
- 고객을 위한 소프트웨어 개발.

이러한 다중 테넌트 시나리오에서 고객은 일부 구성을 테넌트 전체에서 동일하게 유지하거나 구성 변경 및 변경 내용에 대해 보고하려는 경우가 종종 있습니다. 이는 종종 수동으로 변경한 구성에서 코드로 구성을 이동하는 것입니다. Microsoft 프리미어 지원에서는 이 공용 IP를 기반으로 하여 이러한 유형의 요구 사항에 대한 워크숍을 <https://Microsoft365dsc.com> 제공합니다.

### <a name="multi-geo"></a>Multi-Geo

[Multi-Geo 또는](../enterprise/microsoft-365-multi-geo.md) Multi-Geo가 아닌 경우 이는 질문입니다. Multi-Office 365 사용하여 데이터 상주 요구 사항을 충족하기 위해 선택한 지리적 위치에 미사용 데이터를 프로비전하고 저장할 [수](../enterprise/o365-data-locations.md) 있습니다. 이 기능에 대한 오해가 많이 있습니다. 다음 사항에 유의해야 합니다.

- 성능 이점은 제공하지 않습니다. 네트워크 디자인이 정확하지 않은 경우 성능이 [나빠질](https://aka.ms/office365networking) 수 있습니다. 디바이스를 Microsoft 네트워크에 "닫기"합니다. 반드시 데이터를 사용할 필요는 없습니다.
- GDPR 규정 준수를 위한 [솔루션이 아닙니다.](https://www.microsoft.com/trust-center/privacy/gdpr-overview) GDPR은 데이터 주권 또는 저장소 위치에 초점을 맞추지 않습니다. 이에 대한 다른 규정 준수 프레임워크가 있습니다.
- 관리 위임(아래 참조) 또는 정보 장벽은 [해결되지 않습니다.](../compliance/information-barriers.md)
- 다중 테넌트와는 같지 않습니다. 따라서 추가 사용자 프로비전 [워크플로가](https://github.com/MicrosoftDocs/azure-docs-pr/blob/master/articles/active-directory/hybrid/how-to-connect-sync-feature-preferreddatalocation.md) 필요합니다.
- 테넌트(Azure AD)를 다른 지리로 이동하지 않습니다. [](../enterprise/moving-data-to-new-datacenter-geos.md)

## <a name="delegation-of-administration"></a>관리 위임

대부분의 대규모 조직에서는 업무와 RBAC(역할 기반 액세스 제어)의 분리가 필요한 현실입니다. 미리 사과할 것입니다. 이는 일부 고객이 원하는 것만큼 간단하지는 않습니다. 고객, 법률, 규정 준수 및 기타 요구 사항은 다르며 전 세계에 충돌하기도 합니다. 단순성과 유연성은 서로 반대되는 경우가 종종 있습니다. 문제가 될 수 없습니다. 이 작업을 통해 더 나은 작업을 할 수 있습니다. 시간이 지날 때 크게 개선될 것입니다. 현지 [Microsoft 기술](https://www.microsoft.com/mtc) 센터를 방문하여 379230 docs를 읽어보지 않고 비즈니스 요구 사항에 맞는 모델을 해결하세요! 여기서는 이러한 방식이 아니라 어떻게 생각해야 하는지 중점적으로 다를 것입니다. 다음은 계획할 다섯 가지 다른 영역과 자주 묻는 질문 중 일부입니다.

### <a name="azure-ad-and-microsoft-365-admin-centers"></a>Azure AD 및 Microsoft 365 센터

길고 성장하는 기본 제공 역할 [목록이 있습니다.](/azure/active-directory/roles/permissions-reference) 각 역할은 특정 작업이 수행될 수 있도록 그룹화되는 역할 권한 목록으로 구성됩니다. 이러한 사용 권한은 각 역할 내 "설명" 탭에서 볼 수 있습니다. 또는 사용자 센터에서 좀 더 사람이 읽을 수 있는 버전을 Microsoft 365 관리 있습니다. 기본 제공 역할에 대한 정의는 수정할 수 없습니다. 일반적으로 다음 세 가지 범주로 그룹화합니다.

- **전역 관리자:** 이 "모든 강력한" 역할은 다른 시스템에서와 마찬가지로 매우 보호해야 합니다. [](../enterprise/protect-your-global-administrator-accounts.md) 일반적인 권장 사항은 다음과 같습니다. 영구 할당 없음 및 Azure AD PIM(Privileged Identity Management); 강력한 인증 등. 흥미롭게도 이 역할은 기본적으로 모든 데이터에 대한 액세스 권한을 부여하지 않습니다. 일반적으로 나중에 설명하는 규정 준수 액세스 및 Azure 액세스에 대해 혼동을 하게 됩니다. 그러나 이 역할은 항상 테넌트의 다른 서비스에 대한 액세스를 할당할 수 있습니다.
- **특정 서비스 관리자:** 일부 서비스(Exchange, SharePoint, Power BI 등)는 Azure AD의 높은 수준의 관리 역할을 사용 합니다. 이는 모든 서비스에서 일관되지는 못하며 나중에 더 많은 서비스별 역할에 대해 논의합니다.
- **기능:** 특정 작업(게스트 초대자 등)에 초점을 맞추는 긴(및 성장) 역할 목록이 있습니다. 주기적으로 이러한 추가는 고객의 요구에 따라 추가됩니다.

간격이 줄어들어도 모든 것을 위임할 수 없습니다. 즉, 전역 관리자 역할을 때때로 사용해야 합니다. 이 역할의 구성원 자격 대신 코드로 구성 및 자동화를 고려해야 합니다.

**참고:** Microsoft 365 관리 센터 인터페이스는 사용자에게 친숙하지만 Azure AD 관리자 환경과 비교할 때 기능의 하위 집합이 있습니다. 두 포털 모두 동일한 Azure AD 역할을 사용 하여 동일한 장소에서 변경이 발생하고 있습니다. 팁: 모든 Azure 클러터 없이 ID 관리 중심의 관리 UI를 원할 경우 를 <https://aad.portal.azure.com> 사용하세요.

이름에 무엇이 있나요? 역할 이름에서 가정하지 않습니다. 언어는 매우 정확한 도구가 아니기도 합니다. 목표는 필요한 역할을 보기 전에 위임해야 하는 작업을 정의하는 것입니다. 누군가를 "보안 독자" 역할에 추가하면 모든 역할에 보안 설정이 표시되지는 않습니다.

사용자 지정 역할을 만드는 [능력은](/azure/active-directory/users-groups-roles/roles-custom-overview) 일반적인 질문입니다. 이는 현재 Azure AD에서 제한되지만(아래 참조) 시간이 지날수록 기능이 커질 것입니다. 이러한 기능은 Azure AD의 기능에 적용 가능한 것으로 생각하며 계층 구조 모델(위에서 설명한)에 걸쳐 있지 않을 수 있습니다. "사용자 지정"을 할 때마다 "단순이 더 낫습니다."라는 내 보안 주체로 돌아가는 경향이 있습니다.

또 다른 일반적인 질문은 디렉터리의 하위 집합으로 역할 범위를 지정하는 능력입니다. 한 가지 예는 "EU의 사용자에 한해 헬프데스크 관리자"입니다. [AU(관리](/azure/active-directory/users-groups-roles/directory-administrative-units) 단위)는 이를 해결하기 위한 것입니다. 위의 경우와 마찬가지로 이러한 기능은 Azure AD의 기능에 적용 가능한 것으로 생각하며 "아래로"에 걸쳐 있지 않을 수 있습니다. 물론 특정 역할은 범위(전역 관리자, 서비스 관리자 등)에 타당하지 않습니다.

현재 이러한 모든 역할에는 직접 구성원 자격(또는 Azure AD PIM을 사용하는 경우 동적 [할당)이 필요하게 됩니다.](/azure/active-directory/privileged-identity-management/) 즉, 고객은 Azure AD에서 직접 관리해야 하며 이러한 관리는 보안 그룹 구성원 자격을 기반으로 할 수 없습니다. 상승된 권한으로 실행해야 하기 때문에 이러한 스크립트를 관리하기 위해 스크립트를 만드는 것은 팬이 되지 않습니다. 일반적으로 ServiceNow와 같은 프로세스 시스템이나 Saviynt와 같은 파트너 거버넌스 도구를 사용하여 API를 통합하는 것이 좋습니다. 시간이 지날 때 이 문제를 해결하기 위한 엔지니어링 작업도 진행됩니다.

Azure [AD PIM을](/azure/active-directory/privileged-identity-management/) 몇 번 언급했습니다. 해당 Microsoft Identity Manager(MIM) [PAM(Privileged Access Management)](/microsoft-identity-manager/pam/privileged-identity-management-for-active-directory-domain-services) 솔루션이 있습니다. [PAW(Privileged Access Workstation)](/windows-server/identity/securing-privileged-access/privileged-access-workstations) 및 Azure AD Id 거버넌스를 확인할 [수도 있습니다.](/azure/active-directory/governance/identity-governance-overview) 다양한 타사 도구도 있으며, 이 도구는 Just-In-Time, just-enough 및 동적 역할 상승을 가능하게 할 수 있습니다. 이는 일반적으로 환경 보안에 대한 자세한 논의의 일부입니다.

경우에 따라 역할에 외부 사용자를 추가해야 하는 경우도 있습니다(위의 다중 테넌트 섹션 참조). 이 방식은 괜찮습니다. [Azure AD B2B는](/azure/active-directory/b2b/) 고객이 다른 문서에서 참조할 수 있는 또 다른 크고 재미있는 항목입니다.

### <a name="security-and-compliance-center-scc"></a>SCC(보안 및 준수 센터)

[Office 365 보안 &](../security/office-365-security/permissions-in-the-security-and-compliance-center.md) 준수 센터의 사용 권한은 Azure AD 역할과 별개인 "역할 그룹"의 모음입니다. 이러한 역할 그룹 중 일부는 Azure AD 역할(예: 보안 리더)과 이름이 같지만 구성원 자격이 다를 수 있기 때문에 혼란스러울 수 있습니다. Azure AD 역할을 사용하는 것이 좋습니다. 각 역할 그룹은 하나 이상의 "역할"(동일한 단어를 다시 사용하는 경우의 의미 참조)과 전자 메일 사용이 가능한 개체인 Azure AD의 구성원으로 구성됩니다. 또한 역할과 이름이 같은 역할 그룹을 만들 수 있습니다. 이 역할은 해당 역할을 포함하거나 포함하지 않을 수 있습니다(이러한 혼동을 피하기).

의미상, 이러한 역할 그룹 모델은 Exchange 발전된 것입니다. 그러나 Exchange Online 자체 [역할 그룹 관리 인터페이스가](/exchange/permissions-exo) 있습니다. Exchange Online 일부 역할 그룹은 Azure AD 또는 보안 & 준수 센터에서 잠기고 관리되지만 다른 역할 그룹은 이름이 같거나 유사할 수 있으며 Exchange Online(혼란에 추가)에서 관리됩니다. 사용자 인터페이스의 범위가 필요한 Exchange Online 사용자 인터페이스는 사용하지 않는 Exchange 좋습니다.

사용자 지정 역할은 만들 수 없습니다. 역할은 Microsoft에서 만든 서비스에 의해 정의되고 새 서비스가 도입되면 커질 것입니다. 개념상 Azure AD의 응용 프로그램에서 [정의한 역할과](/azure/active-directory/develop/howto-add-app-roles-in-azure-ad-apps) 비슷합니다. 새 서비스를 사용하도록 설정한 경우 이러한 서비스에 대한 액세스 권한을 부여하거나 위임하기 위해 새 역할 그룹을 만들어야 하는 경우가 종종 있습니다(예: 내부자 위험 [관리).](../compliance/insider-risk-management-configure.md)

또한 이러한 역할 그룹에는 직접 구성원 자격이 필요하며 Azure AD 그룹을 포함할 수 없습니다. 안타깝게도 현재 이러한 역할 그룹은 Azure AD PIM에서 지원되지 않습니다. Azure AD 역할과 마찬가지로 API 또는 Saviynt와 같은 파트너 거버넌스 제품을 통해 이러한 관리가 권장됩니다.

보안 & 준수 센터 역할은 Microsoft 365 범위가 지정되어 있으며 이러한 역할 그룹을 환경의 하위 집합으로 범위 지정할 수 없습니다(예: Azure AD의 관리 단위를 사용할 수 있습니다). 많은 고객이 하위 위임할 수 있는 방법을 묻는 질문이 있습니다. 예를 들어 "EU 사용자에 대한 DLP 정책 만들기"를 예로 들 수 있습니다. 현재 보안 및 준수 센터에서 특정 기능에 & 있는 경우 테넌트에서 이 기능이 다루는 모든 기능에 대한 권한을 가합니다. 그러나 많은 정책에는 환경의 하위 집합을 대상으로 지정하는 기능이 [](../compliance/create-sensitivity-labels.md#publish-sensitivity-labels-by-creating-a-label-policy) 있습니다(예: "이러한 레이블을 이러한 사용자만 사용할 수 있도록 설정"). 적절한 거버넌스 및 커뮤니케이션은 충돌을 방지하기 위한 핵심 구성 요소입니다. 일부 고객은 보안 및 준수 센터에서 하위 위임 문제를 해결하기 위해 "코드로 구성" 접근 방식을 & 있습니다. 일부 특정 서비스는 하위 위임(아래 참조)을 지원합니다.

현재 보안 & 준수 센터(protection.office.com)를 통해 관리되는 컨트롤은 두 개의 개별 관리 포털인 security.microsoft.com 및 compliance.microsoft.com. 변경이 유일한 상수입니다!

### <a name="service-specific"></a>서비스 관련

앞에서 밝혔듯이 많은 고객은 보다 세분화된 위임 모델을 달성하기를 원합니다. 일반적인 예: "부서 X 사용자 및 위치에 대한 XYZ 서비스만 관리"(또는 다른 차원). 이 작업을 하는 기능은 각 서비스에 따라 달라지며 서비스 및 기능 전체에서 일관되지 않습니다. 또한 각 서비스에는 별도의 고유한 RBAC 모델이 있을 수 있습니다. 이러한 모든 정보를 논의하는 대신(영문일 수 있습니다) 각 서비스에 대한 관련 링크를 추가하고 있습니다. 이 목록은 전체 목록이 아니며 시작할 수 있습니다.

- **Exchange Online** - (/exchange/permissions-exo/permissions-exo)
- **SharePoint Online** - (/sharepoint/manage-site-collection-administrators)
- **Microsoft Teams** - (/microsoftteams/itadmin-readiness)
- **eDiscovery** - (.. /compliance/index.yml)
  - **사용 권한 필터링** - (.. /compliance/index.yml)
  - **규정 준수 경계** - (.. /compliance/set-up-compliance-boundaries.md)
  - **Advanced eDiscovery** - (.. /compliance/overview-ediscovery-20.md)
- **Yammer** - (/yammer/manage-yammer-users/manage-yammer-admins)
- **Multi-Geo** - (.. /enterprise/add-a-sharepoint-geo-admin.md)
- **Dynamics 365** – (/dynamics365/)

  참고: 이 링크는 설명서의 루트에 연결됩니다. 관리자/위임 모델에는 변형이 있는 여러 유형의 서비스가 있습니다.

- **Power Platform** - (/power-platform/admin/admin-documentation)
  - **Power Apps** - (/power-platform/admin/wp-security)

    참고: 관리자/위임 모델에는 변형이 있는 여러 유형이 있습니다.

  - **Power Automate** - (/power-automate/environments-overview-admin)
  - **Power BI** - (/power-bi/service-admin-governance)

    참고: 데이터 플랫폼 보안 및 위임(구성 요소인 Power BI)은 복잡한 영역입니다.

- **MEM/Intune** - (/mem/intune/fundamentals/role-based-access-control)
- **끝점용 Microsoft Defender** - (/windows/security/threat-protection/microsoft-defender-atp/user-roles)
- **Microsoft 365 Defender** - (.. /security/defender/m365d-permissions.md)
- **Microsoft Cloud App Security** - (/cloud-app-security/manage-admins)
- **Stream** - (/stream/assign-administrator-user-role)
- **정보 장벽** - (.. /compliance/information-barriers.md)

### <a name="activity-logs"></a>활동 로그

Office 365 감사 [로그가 있습니다.](../compliance/search-the-audit-log-in-security-and-compliance.md) 매우 자세한 [로그이지만](/office/office-365-management-api/office-365-management-activity-api-schema)이름에 너무 많이 읽지 않습니다. 보안 및 규정 준수 요구에 필요한 모든 것을 포함하지 않을 수 있습니다. 또한 일부 고객은 고급 감사에 [실제로 관심이 있습니다.](../compliance/advanced-audit.md)

다른 Microsoft 365 액세스하는 로그의 예는 다음과 같습니다.

- [Azure](/azure/azure-monitor/platform/diagnostic-settings) AD(사용자와 관련되지 않은 Office 365)
- [Exchange 메시지 추적](/powershell/module/exchange/get-messagetrace)
- 위에서 설명한 위협/UEBA 시스템(예: Azure AD ID 보호, Microsoft Cloud App Security, 끝점용 Microsoft Defender 등)
- [Microsoft 정보 보호](../compliance/data-classification-activity-explorer.md)
- [엔드포인트용 Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/api-power-bi)
- [Microsoft Graph](https://graph.microsoft.com)

먼저 보안 및 규정 준수 프로그램에 필요한 모든 로그 원본을 식별하는 것이 중요합니다. 또한 로그마다 서로 다른 인라인 보존 제한이 있습니다.

관리자 위임 관점에서 볼 때 대부분의 Microsoft 365 로그에는 기본 제공 RBAC 모델이 없습니다. 로그를 볼 수 있는 권한이 있는 경우 로그의 모든 것을 볼 수 있습니다. 고객 요구 사항의 일반적인 예는 "EU 사용자에 대한 활동만 쿼리할 수 있도록 하려는 경우"(또는 다른 차원)입니다. 이 요구 사항을 충족하려면 로그를 다른 서비스로 전송해야 합니다. Microsoft 클라우드에서 [Azure Sentinel](/azure/sentinel/overview) 또는 Log Analytics로 전송하는 [것이 좋습니다.](/azure/azure-monitor/learn/quick-create-workspace)

높은 수준의 다이어그램:

![보안 및 규정 준수 프로그램의 로그 원본 다이어그램](../media/solutions-architecture-center/identity-beyond-illustration-4.png)

위의 다이어그램은 이벤트 허브 및/또는 Azure Log Analytics 및/또는 Azure Azure Storage 보낼 수 있는 기본 제공 기능을 제공합니다. 모든 시스템에는 이러한 첫 운영 체제가 아직 포함되어 있지 않습니다. 그러나 이러한 로그를 동일한 리포지토리로 보내는 다른 방법도 있습니다. 예를 들어 [Azure Sentinel로 Teams 보호를 참조하세요.](https://techcommunity.microsoft.com/t5/azure-sentinel/protecting-your-teams-with-azure-sentinel/ba-p/1265761)

모든 로그를 하나의 저장소 위치에 결합하면 상호 상관 관계, 사용자 지정 보존 시간, RBAC 모델을 지원하는 데 필요한 데이터로 확장 등의 추가 이점이 포함됩니다. 이 저장소 시스템에 데이터가 있는 경우 적절한 RBAC 모델을 사용하여 Power BI 대시보드(또는 다른 유형의 시각화)를 만들 수 있습니다.

로그를 한 곳으로만 연결하지는 않습니다. 또한 의 사용자 지정 [RBAC](/cloud-app-security/connect-office-365-to-microsoft-cloud-app-security) 모델이나 Office 365 로그를 통합하는 Microsoft Cloud App Security 유용할 [Power BI.](../admin/usage-analytics/usage-analytics.md) 리포지토리마다 이점과 대상이 다릅니다.

이라는 서비스에 보안, 위협, 취약성 등 다양한 기본 제공 분석 [시스템이](../security/defender/microsoft-365-defender.md)Microsoft 365 Defender.

많은 대규모 고객은 이 로그 데이터를 타사 시스템(예: SIEM)으로 전송하기를 원합니다. 이 방법은 서로 다르지만 일반적인 [Azure](/azure/azure-monitor/platform/stream-monitoring-data-event-hubs) [이벤트](/graph/security-integration) 허브 및 Graph 좋은 시작점입니다.

### <a name="azure"></a>Azure

Azure AD, Azure 및 SaaS 간에 높은 권한 역할을 구분할 수 있는 방법이 있는지(예: Azure의 경우 전역 관리자Office 365 질문이 있습니다.  설마.  완전한 관리 분리가 필요하지만 매우 복잡해진 경우 다중 테넌트 아키텍처가 [필요합니다(위](https://aka.ms/multi-tenant-user) 참조). 이러한 모든 서비스는 동일한 보안/ID 경계에 포함됩니다(위의 계층 구조 모델 살펴보기).

동일한 테넌트에 있는 다양한 서비스 간의 관계를 이해하는 것이 중요합니다. Azure, Office 365 및 Power Platform에 걸쳐 비즈니스 솔루션을 구축하는 많은 고객과 협력하고 있습니다(또한 종종 사내 및 타사 클라우드 서비스). 한 가지 일반적인 예:

1. 문서/이미지/등 집합에 대해 공동 작업을 하고 싶음(Office 365)
2. 승인 프로세스(Power Platform)를 통해 각각 보내기
3. 모든 구성 요소가 승인되면 이러한 구성 요소를 통합 결과물(Azure) Microsoft Graph [API로](/azure/active-directory/develop/microsoft-graph-intro) 어셈블합니다.  불가능하지는 않지만 여러 테넌트에 걸쳐 있는 솔루션을 디자인하는 것이 훨씬 [더 복잡합니다.](/azure/active-directory/develop/single-and-multi-tenant-apps)

Azure Role-Based RBAC(액세스 제어)를 사용하면 Azure에 대해 세분화된 액세스 관리를 사용할 수 있습니다. RBAC를 사용하면 사용자에게 작업을 수행하는 데 필요한 몇 가지 권한을 부여하여 리소스에 대한 액세스를 관리할 수 있습니다. 자세한 내용은 이 문서의 범위를 벗어날 수 있지만 RBAC에 대한 자세한 내용은 Azure의 RBAC(역할 기반 액세스 [제어)란?을 참조하세요.](/azure/role-based-access-control/overview) RBAC는 중요하지만 Azure에 대한 거버넌스 고려 사항의 일부일 뿐입니다. [클라우드 채택 프레임워크는](/azure/cloud-adoption-framework/govern/) 자세한 내용을 알아보는 좋은 시작 지점입니다. I like how my friend, [Andres Ravinet](https://www.linkedin.com/in/andres-ravinet/), walks customers step by step though various components to decide on the approach. 다양한 요소에 대한 개성 있는 보기(실제 고객 모델에 대한 프로세스만큼 좋지는 않습니다.)는 같습니다.

![위임된 관리에 대한 Azure 구성 요소의 개성 높은 보기](../media/solutions-architecture-center/identity-beyond-illustration-5.png)

위의 그림에서 볼 수 있듯이 다른 많은 서비스는 디자인의 일부로 간주해야 합니다(예: [Azure 정책, Azure](/azure/governance/policy/overview) [Blueprint,](/azure/governance/blueprints/overview) [관리 그룹](/azure/governance/management-groups/)등).

## <a name="conclusion"></a>결론

짧은 요약으로 시작된 후 예상보다 더 오래 끝났습니다.  이제 조직을 위한 위임 모델을 만드는 방법을 심도 깊게 확인하게 되길 바라.  이 대화는 고객과 매우 일반적입니다. 모든 사람이 사용할 수 있는 모델은 없습니다. 여러 고객에게 공통된 패턴을 문서화하기 전에 Microsoft 엔지니어링에서 계획된 몇 가지 개선을 기다리는 중입니다. 그동안 Microsoft 계정 팀과 함께 가장 가까운 Microsoft 기술 센터 방문을 [준비할 수 있습니다.](https://www.microsoft.com/mtc)  이 곳을 참조하세요!
