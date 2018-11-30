---
title: '15단계: 동적 그룹 구성원 설정'
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
description: 계정 특성에 따른 자동 그룹 구성원을 이해하고 구성합니다.
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870235"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>15단계: 동적 그룹 구성원 설정

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 사용자 계정을 Azure AD 그룹의 구성원으로 자동으로 추가하거나 제거하는 일련의 규칙을 만듭니다. 이를 *동적 그룹 구성원*이라고 합니다. 규칙은 부서 또는 국가와 같은 사용자 계정 속성을 기반으로 합니다.

규칙이 적용되는 방식은 다음과 같습니다.

- 새 사용자 계정이 그룹에 대한 모든 규칙과 일치하는 경우 구성원이 됩니다.
- 사용자가 그룹의 구성원이 아니지만 해당 속성이 그룹에 대한 모든 규칙과 일치하도록 변경되는 경우 해당 그룹의 구성원이 됩니다.
- 사용자 계정이 그룹에 대한 일부 규칙과 일치하지 않는 경우 그룹에 추가되지 않습니다.
- 사용자가 그룹의 구성원이지만 해당 속성이 그룹에 대한 모든 규칙과 더 이상 일치하지 않도록 변경되는 경우 그룹의 구성원에서 제거됩니다.

동적 구성원을 사용하려면 먼저 공통적인 사용자 계정 속성 집합이 있는 그룹 집합 확인해야 합니다. 예를 들어 Sales 부서의 모든 구성원은 “Sales”로 설정된 Department 사용자 계정 특성에 따라 Sales Azure AD 그룹에 속해야 합니다.

[동적 Azure AD 그룹에 대한 규칙을 만들고 구성하는 지침](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 참조하세요.

이 단계의 결과는 다음과 같습니다.

- 동적 구성원에 대해 구성할 수 있는 Azure AD 그룹 집합
- 각 동적 그룹에 대한 규칙 집합

|||
|:-------|:-----|
|![Microsoft 클라우드의 테스트 랩 가이드](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [테스트 랩 가이드: 라이선스 및 그룹 등록 자동화](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-dyn-groups)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

[ID 인프라 종료 조건](identity-exit-criteria.md)
