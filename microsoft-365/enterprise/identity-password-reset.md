---
title: '5단계: 사용자에 대한 액세스 간소화'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/19/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD(Microsoft Azure Active Directory)에 대한 SSPR(셀프 서비스 암호 재설정)을 이해하고 구성하십시오.
ms.openlocfilehash: 98118a5891ea8224843faa638b52a421d96e8a0b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32287070"
---
# <a name="step-5-simplify-access-for-users"></a>5단계: 사용자에 대한 액세스 간소화

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)


<a name="identity-pw-writeback"></a>
## <a name="simplify-password-updates"></a>암호 업데이트 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 사용자는 Azure 액티브 디렉토리(Azure AD-Microsoft Azure Active Directory)를 통해 암호를 재설정할 수 있으며 로컬 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)로 복제될 수 있습니다. 이 과정을 암호 쓰기 저장이라고 합니다. 암호 쓰기 저장에서 사용자는 사용자 계정과 속성이 저장된 온 브레미스 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)를 통한 암호의 업데이트가 필요 없습니다. 온-프레미스 네트워크에 대한 원격 액세스 연결이 없는 로밍 또는 원격 사용자에게 유용합니다.

암호 쓰기 저장은 계정 손상의 높은 위험이 감지된 경우 사용자에게 온-프레미스 암호를 변경하도록 요구하는 등 ID 보호 기능을 최대한 활용하기 위해 필요합니다.

추가 정보 및 구성 지침은 [암호 쓰기 저장을 지원하는 Azure AD SSPR](https://docs.microsoft.com/azure/active-directory/active-directory-passwords-writeback)을 참조하세요.

>[!Note]
>가능한 최상의 환경 및 새로운 기능(릴리스될 때)을 유지하도록 최신 버전의 Azure AD Connect로 업그레이드하세요. 자세한 내용은 [Azure AD Connect의 사용자 지정 설치](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-get-started-custom)를 참조하세요.
>

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 암호 쓰기 저장](password-writeback-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-writeback)을 확인할 수 있습니다.

<a name="identity-pw-reset"></a>
## <a name="simplify-password-resets"></a>암호 재설정 간소화

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 셀프 서비스 암호 재설정은 사용자가 암호 혹은 계정을 재설정 혹은 잠금을 해제하도록 해줍니다. 오용 또는 남용에 대한 경고로 사용자가 시스템에 언제 액세스하는지 추적하는 상세한 보고서와 알림을 사용할 수 있습니다. 암호 재설정 전에 암호 쓰기 저장을 사용할 수 있도록 설정해야 합니다.

[암호 재설정을 시작하기 위한 지침](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-deployment)을 참조하십시오.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 암호 재설정](password-reset-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-pw-reset)을 확인할 수 있습니다.


<a name="identity-sso"></a>
## <a name="simplify-user-sign-in"></a>사용자 로그인 간소화

*이 단계는 하이브리드 환경의 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 사용자 암호 및 사용자 이름을 입력할 필요없이 Azure 사용자 계정을 사용하는 서비스에 로그인 할 수 있도록 Azure 액티브 디렉토리 심리스 Single Sign-On(Azure AD Seamless SSO) 를 설정할 수 있습니다. 이는 사용자의 계정이 Office 365와 같은 클라우드 기반 응용 프로그램에 identity 페더레이션 서버와 같은 추가적인 온 프레미스 구성 요소 필요없이 더 쉽게 액세스할 수 있습니다.

Azure AD Connect 도구를 사용하여 Azure AD Seamless SSO를 구성합니다.

[Azure AD Seamless SSO 구성 지침](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-sso-quick-start)을 참조하세요.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: Azure AD Seamless Single Sign-on](single-sign-on-m365-ent-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-sso)을 확인할 수 있습니다.


<a name="identity-custom-sign-in"></a>
## <a name="customize-the-office-365-sign-in-page"></a>Microsoft Office 365 로그인 페이지 사용자 지정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전을 위한 것입니다.*

이 부문에서 회사 이름, 로고 및 기타 인식 가능한 요소를 추가하여 사용자가 조직의 로그인 페이지를 인식하도록 도와줍니다. 

Microsoft 365 Enterprise를 사용하는 경우 회사 로고, 색 구성표 및 사용자 지정 사용자 정보를 포함하도록 로그인 및 액세스 패널 페이지의 모양을 사용자 지정할 수 있습니다. 

사용자가 장치에서 로그인을 시도하면 다음 예와 같은 *사용자 지정 전* Office 365 로그인 페이지가 표시됩니다.

![사용자 지정 전 Office 365 로그인 페이지 예](./media/identity-customize-office-365-sign-in/id-step01-sign-in-before.png)

*사용자 지정 후* Contoso Corporation의 동일한 사용자에게 표시되는 페이지는 다음과 같습니다.

![사용자 지정 후 Office 365 로그인 페이지의 예](./media/identity-customize-office-365-sign-in/id-step01-sign-in-after.png)

자세한 내용은 [Office 365 로그인 페이지에 회사 브랜딩 추가](https://docs.microsoft.com/office365/admin/setup/customize-sign-in-page)를 참조하세요.

구성 지침은 [로그인 및 액세스 패널에 회사 브랜딩 추가](http://aka.ms/aadpaddbranding)를 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-custom-sign-in)을 확인할 수 있습니다.


## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step6.png)| [더 쉬운 관리를 위한 그룹 사용](identity-self-service-group-management.md) |


