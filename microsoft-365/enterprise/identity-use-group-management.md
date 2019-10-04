---
title: '5단계: 그룹을 사용하여 관리하십시오.'
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
description: 그룹을 사용하여 일부 관리 작업을 자동화할 수 있습니다.
ms.openlocfilehash: 769fc0dd69b13978dbb9cf91d890ad271a7d9bb5
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370185"
---
# <a name="step-5-use-groups-for-management"></a>5단계: 그룹을 사용하여 관리하십시오.

![2단계-ID](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<a name="identity-self-service-groups"></a>
## <a name="allow-users-to-create-and-manage-their-own-groups"></a>사용자가 자신의 그룹을 만들고 관리하도록 허용하십시오.

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 IT 관리자를 대신하여 그룹 소유자가 관리할 수 있는 Azure 액티브 디렉토리(Azure AD-Microsoft Azure Active Directory) 그룹을 식별할 것입니다. *셀프 서비스 그룹 관리*로 알려진 기능은 관리역할이 할당되지 않은 그룹 소유자가 보안 그룹을 생성하고 관리할 수 있도록 해줍니다. 

사용자는 보안 그룹에서 구성원을 요청할 수 있으며, 이 요청은 IT 관리자가 아니라 그룹 소유자에게 전달됩니다. 이를 통해 그룹의 비즈니스 사용을 이해하고 해당 구성원을 관리할 수 있는 팀, 프로젝트 또는 비즈니스 소유자에게 일상적인 그룹 구성원 제어를 위임할 수 있습니다.

>[!Note]
>셀프 서비스 그룹 관리는 Azure AD(Microsoft Azure Active Directory) 보안 및 Microsoft Office 365 그룹에서만 사용할 수 있습니다. 온 프레미스 액티브 디렉토리 도메인 서비스(AD DS-Active Directory Domain Services)에서 동기화된 메일이 사용가능한 그룹, 배포 목록 또는 다른 그룹에서 사용이 불가능합니다.
>

자세한 내용은 [셀프 서비스 관리에 대한 Azure AD(Microsoft Azure Active Directory) 그룹 구성 지침](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)을 참조하십시오.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-self-service-groups)을 확인할 수 있습니다.

<a name="identity-dyn-groups"></a>
## <a name="set-up-dynamic-group-membership"></a>동적 그룹 구성원 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 Azure AD(Microsoft Azure Active Directory) 그룹의 구성원으로서 사용자 계정을 자동으로 추가하거나 제거할 수 있는 일련의 규칙을 생성할 것입니다. 이를 *동적 그룹 구성원*이라고 합니다. 이 규칙은 부서나 국가와 같은 사용자 계정 속성을 기반으로 하고 있습니다.

규칙이 적용되는 방식은 다음과 같습니다.

- 새 사용자 계정이 그룹에 대한 모든 규칙과 일치하는 경우 구성원이 됩니다.
- 사용자가 그룹의 구성원이 아니지만 해당 속성이 그룹에 대한 모든 규칙과 일치하도록 변경되는 경우 해당 그룹의 구성원이 됩니다.
- 사용자 계정이 그룹에 대한 일부 규칙과 일치하지 않는 경우 그룹에 추가되지 않습니다.
- 사용자가 그룹의 구성원이지만 해당 속성이 그룹에 대한 모든 규칙과 더 이상 일치하지 않도록 변경되는 경우 그룹의 구성원에서 제거됩니다.

동적 구성원을 사용하려면 먼저 공통적인 사용자 계정 속성 집합이 있는 그룹 집합 확인해야 합니다. 예를 들어 Sales 부서의 모든 구성원은 “Sales”로 설정된 Department 사용자 계정 특성에 따라 Sales Azure AD 그룹에 속해야 합니다.

[동적 Azure AD 그룹에 대한 규칙을 만들고 구성하는 지침](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 참조하세요.

이 부문의 결과:

- 동적 구성원에 대해 구성할 수 있는 Azure AD 그룹 집합
- 각 동적 그룹에 대한 규칙 집합

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 라이선스 및 그룹 등록 자동화](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-dyn-groups)을 확인할 수 있습니다.

<a name="identity-group-license"></a>
## <a name="set-up-automatic-licensing"></a>자동 라이선싱 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

이 부문에서 그룹의 모든 구성원에게 일습의 구독 라이센스를 자동으로 할당하기 위해 Azure AD(Microsoft Azure Active Directory)의 보안 그룹을 구성할 것입니다. 이를 *그룹 기반 라이센싱*이라고 합니다. 사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 계정에서 자동으로 할당되거나 할당 해제됩니다.

Microsoft 365 Enterprise의 경우 적절한 Microsoft 365 Enterprise 라이선스를 할당하도록 Azure AD 보안 그룹을 구성합니다.

모든 그룹 구성원에 대한 충분한 라이센스가 있는지 확인합니다. 라이선스가 부족할 경우 라이선스를 사용할 수 있게 될 때까지 신규 사용자에게 라이선스가 할당되지 않습니다.

>[!Note]
>Azure B2B 계정이 포함된 그룹에 대해 *그룹 기반 라이선싱*을 구성해서는 안 됩니다.
>

추가 정보는 [Azure Active Directory의 그룹 기반 라이선싱 기본 사항](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)을 참조하세요.

[Azure 보안 그룹에 대해 그룹 기반 라이선싱을 구성하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)를 참조하세요.

이 부문의 결과:

- 그룹 기반 라이선싱에 적합한 보안 그룹을 식별했습니다.
- 그룹 기반 라이선싱에 대해 이러한 그룹을 구성했습니다.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 라이선스 및 그룹 등록 자동화](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 섹션에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-group-license)을 확인할 수 있습니다.

|||
|:-------|:-----|
|![6단계](./media/stepnumbers/Step6.png)| [ID 거버넌스 구성](identity-configure-identity-governance.md) |
