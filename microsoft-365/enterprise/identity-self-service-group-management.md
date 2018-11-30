---
title: '14단계: 사용자가 자신의 그룹을 만들고 관리하도록 허용'
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
description: Azure AD 그룹 셀프 서비스 관리를 이해하고 구성합니다.
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870048"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>14단계: 사용자가 자신의 그룹을 만들고 관리하도록 허용

*이 단계는 선택 사항이며, Microsoft 365 Enterprise E3 및 E5 버전에 적용됩니다.*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

이 단계에서는 IT 관리자 대신 그룹 소유자가 관리할 수 있는 Azure AD(Active Directory) 그룹을 식별합니다. *셀프 서비스 그룹 관리*라는 이 기능은 관리 역할이 할당되지 않은 그룹 소유자가 보안 그룹을 만들고 관리하도록 해줍니다. 

사용자는 보안 그룹에서 구성원을 요청할 수 있으며, 이 요청은 IT 관리자가 아니라 그룹 소유자에게 전달됩니다. 이를 통해 그룹의 비즈니스 사용을 이해하고 해당 구성원을 관리할 수 있는 팀, 프로젝트 또는 비즈니스 소유자에게 일상적인 그룹 구성원 제어를 위임할 수 있습니다.

>[!Note]
>셀프 서비스 그룹 관리는 Azure AD 보안 및 Office 365 그룹에만 사용할 수 있습니다. 메일 사용이 가능한 그룹, 메일 그룹 또는 온-프레미스 Windows Server AD(Active Directory)에서 동기화 된 그룹에는 사용할 수 없습니다.
>

자세한 내용은 [셀프 서비스 관리에 대한 Azure AD 구성 지침](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)을 참조하세요.

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-self-service-groups)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [동적 그룹 구성원 설정](identity-automatic-group-membership.md) |
