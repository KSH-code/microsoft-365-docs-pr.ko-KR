---
title: '12단계: 자동 라이선싱 설정'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 그룹 기반 라이선싱을 이해하고 Azure AD 그룹에 대해 구성합니다.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26869701"
---
# <a name="step-12-set-up-automatic-licensing"></a>12단계: 자동 라이선싱 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 구독 집합의 라이선스를 그룹의 모든 구성원에게 자동으로 할당하도록 Azure AD에서 보안 그룹을 구성합니다. 이를 *그룹 기반 라이선싱*이라고 합니다. 그룹에서 사용자 계정이 추가되거나 제거된 경우 해당 그룹의 구독에 대한 라이선스가 사용자 계정에서 자동으로 할당되거나 제거됩니다.

Microsoft 365 Enterprise의 경우 다음 두 라이선스를 모두 할당하도록 Azure AD 보안 그룹을 구성합니다.

- Office 365 Enterprise E3 또는 E5
- EMS(Enterprise Mobility + Security) E3 또는 E5

2단계에서 식별한 그룹을 사용하여 해당 그룹의 모든 사용자에게 Office 365 및 EMS 라이선스가 있어야 하는 계정 목록이 포함된 그룹을 찾습니다. 모든 그룹 구성원을 위한 라이선스가 충분한지 확인합니다. 라이선스가 부족하면 라이선스를 사용할 수 있을 때까지 새 사용자에게 라이선스가 할당되지 않습니다.

>[!Note]
>Azure B2B 계정이 포함된 그룹에 대해 *그룹 기반 라이선싱*을 구성해서는 안 됩니다.
>

추가 정보는 [Azure Active Directory의 그룹 기반 라이선싱 기본 사항](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)을 참조하세요.

[Azure 보안 그룹에 대해 그룹 기반 라이선싱을 구성하는 단계](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)를 참조하세요.

이 단계의 결과는 다음과 같습니다.

- 그룹 기반 라이선싱에 적합한 보안 그룹을 식별했습니다.
- 그룹 기반 라이선싱에 대해 이러한 그룹을 구성했습니다.

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 라이선스 및 그룹 등록 자동화](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-group-license)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [테넌트 및 로그인 활동 모니터링](identity-azure-ad-access-usage-reporting.md) |

