---
title: '7단계: ID 거버넌스 구성'
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
description: Azure AD 테넌트에 대한 ID 거버넌스를 이해하고 구성합니다.
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633586"
---
# <a name="step-6-configure-identity-governance"></a>6단계: ID 거버넌스 구성

![2단계-ID](../media/deploy-foundation-infrastructure/identity_icon-small.png)

ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다. 예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.

Azure ID(Azure Active Directory)의 ID 거버넌스에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)를 참조하세요.


*이 단계는 선택 사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>Azure AD 액세스 검토 설정

*이 단계는 선택사항이며 Microsoft 365 Enterprise E5 버전에만 적용됩니다.*

이 단계에서는 Azure AD 액세스 검토를 설정하여 사용자의 액세스를 검토함으로써 올바른 사용자만 계속 액세스할 수 있도록 합니다. 예:

- 새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.
- 해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.
- 해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.

이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.

Azure AD 액세스 검토에 대한 자세한 내용은 [이 문서](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)를 참조하세요.

PIM(Azure AD Privileged Identity Management)에서는 Azure AD, Azure 및 기타 Microsoft 클라우드 서비스에서 리소스에 대한 액세스 권한을 보호하기 위해 조정된 추가 컨트롤을 제공합니다. Azure AD PIM은 디렉터리, Office 365, Azure 리소스 역할 등 회사의 리소스를 보호하는 데 도움이 되는 포괄적인 관리 제어 집합을 제공합니다. 다른 양식의 액세스를 사용하는 경우와 마찬가지로 조직은 액세스 검토를 사용하여 관리자 역할의 모든 사용자에 대해 정기 액세스 재인증을 구성할 수 있습니다. Azure AD PIM은 Microsoft 365 Enterprise의 E5 버전에서만 사용할 수 있습니다.

다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.

- [그룹 및 앱](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 리소스 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

중간 검사점으로 이 단계에 대한 [종료 조건](identity-exit-criteria.md#crit-identity-access-reviews)을 확인할 수 있습니다.

## <a name="next-step"></a>다음 단계

[ID 인프라 종료 조건](identity-exit-criteria.md)

