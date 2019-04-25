---
title: '6단계: 그룹을 사용하여 더 쉽게 관리하십시오.'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 02/25/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: Azure AD(Microsoft Azure Active Directory) 셀프 서비스 그룹 관리를 이해하고 구성하십시오.
ms.openlocfilehash: 9400e99ced45370600d1d5dcee4388ddef4250fe
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283529"
---
# <a name="step-6-use-groups-for-easier-management"></a>6단계: 그룹을 사용하여 더 쉽게 관리하십시오.

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

이 부문에서 그룹의 모든 구성원에게 일습의 구독 라이센스를 자동으로 할당하기 위해 Azure AD(Microsoft Azure Active Directory)의 보안 그룹을 구성할 것입니다. 이를 *그룹 기반 라이센싱*이라고 합니다. 사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 게정에서 자동으로 할당되거나 제거될 것입니다.

Microsoft 365 Enterprise의 경우 다음 두 라이선스를 모두 할당하도록 Azure AD 보안 그룹을 구성합니다.

- Office 365 Enterprise E3 또는 E5
- EMS(Enterprise Mobility + Security) E3 또는 E5

2단계에서 식별한 그룹을 사용하여 해당 그룹의 모든 사용자에게 Office 365 및 EMS 라이선스가 있어야 하는 계정 목록이 포함된 그룹을 찾습니다. 모든 그룹 구성원을 위한 라이선스가 충분한지 확인합니다. 라이선스가 부족하면 라이선스를 사용할 수 있을 때까지 새 사용자에게 라이선스가 할당되지 않습니다.

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

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-group-license)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

[ID 인프라 종료 조건](identity-exit-criteria.md)
