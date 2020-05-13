---
title: '2단계: 암호 보호'
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 조직 전체에 암호를 강력하고 관리하기 쉽도록 설정해야 합니다.
ms.openlocfilehash: 6e5c2567ee2027be2a84121fdad10ba873ec1c43
ms.sourcegitcommit: 1c90bcc5c56f24895f01c3e0423c3f6b73715c13
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/13/2020
ms.locfileid: "44214653"
---
# <a name="step-2-secure-your-passwords"></a>2단계: 암호 보호

![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-password-prot"></a>
## <a name="prevent-bad-passwords"></a>잘못된 암호 방지

*이 단계는 선택 사항이며 Microsoft 365 E3 및 E5 버전에 모두 적용됩니다*

모든 사용자가 [Microsoft의 암호 지침](https://www.microsoft.com/research/publication/password-guidance) 을 사용하여 사용자 계정 암호를 만들어야 합니다.

사용자가 쉽게 확인할 수 있는 암호를 만들지 못하도록 하려면 전역 금지 암호 목록과 사용자가 지정한 선택적 사용자 지정 금지 암호 목록을 사용하는 Azure AD 암호 보호를 사용합니다. 예를 들어, 다음과 같이 조직에 맞는 조건을 지정할 수 있습니다.

- 브랜드 이름
- 제품 이름
- 위치(예: 본사)
- 회사 관련 내부 조건
- 특정 회사 의미를 갖는 약어

[클라우드](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad) 및 [온-프레미스 AD DS(Active Directory Domain Services)](https://docs.microsoft.com/azure/active-directory/authentication/concept-password-ban-bad-on-premises)에 대해 잘못된 암호를 금지할 수 있습니다.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-password-prot)을 확인할 수 있습니다.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>암호 재설정 간소화

*이 단계는 선택 사항이며 Microsoft 365 E3 및 E5 버전에 모두 적용됩니다*

이 부문에서 셀프 서비스 암호 재설정은 사용자가 암호 혹은 계정을 재설정 혹은 잠금을 해제하도록 해줍니다. 오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다. 암호 재설정 전에 암호 쓰기 저장을 사용할 수 있도록 설정해야 합니다.

[암호 재설정을 시작하기 위한 지침](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 암호 재설정](password-reset-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-reset)을 확인할 수 있습니다.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>사용자 로그인 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 사용자 암호 및 사용자 이름을 입력할 필요없이 Azure AD 사용자 계정을 사용하는 서비스에 로그인 할 수 있도록 PHS(Password Hash Synchronization) 및 PTA(Pass-Through Authentication)와 함께 작동하는 Azure AD Seamless SSO(Azure Active Directory Seamless Single Sign-On)를 설정할 수 있습니다. 이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.

Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.

[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: Azure AD Seamless Single Sign-on](single-sign-on-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-sign-in-page"></a>로그인 페이지 사용자 지정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전을 위한 것입니다.*

이 부문에서 회사 이름, 로고 및 기타 인식 가능한 요소를 추가하여 사용자가 조직의 로그인 페이지를 인식하도록 도와줍니다. 

Microsoft 365 Enterprise를 사용하는 경우 회사 로고, 색 구성표 및 사용자 지정 사용자 정보를 포함하도록 로그인 및 액세스 패널 페이지의 모양을 사용자 지정할 수 있습니다. 

자세한 내용은 [Microsoft 365 로그인 페이지에 회사 브랜딩 추가](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)를 참조하세요.

구성 지침은 [로그인 및 액세스 패널에 회사 브랜딩 추가](https://aka.ms/aadpaddbranding)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-custom-sign-in)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![3단계](../media/stepnumbers/Step3.png)| [사용자 로그인 보안 및 관리](identity-secure-user-sign-ins.md) |
