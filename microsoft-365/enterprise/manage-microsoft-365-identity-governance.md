---
title: Microsoft 365 id 거 버 넌 스 관리
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: Microsoft 365 id 거 버 넌 스 기능을 사용 하는 방법에 대해 알아봅니다.
ms.openlocfilehash: e4c537e7fa3ac099caf8b7dbc44327308751c8f5
ms.sourcegitcommit: 33afa334328cc4e3f2474abd611c1411adabd39f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/07/2020
ms.locfileid: "48370349"
---
# <a name="manage-microsoft-365-identity-governance"></a>Microsoft 365 id 거 버 넌 스 관리

ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다. 예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.

자세한 내용은 azure [Active Directory에 대 한 id 관리 개요 (AZURE AD)](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)를 참조 하세요.

## <a name="set-up-azure-ad-access-reviews"></a>Azure AD 액세스 검토 설정

Azure AD 액세스 검토를 통해 사용자의 액세스를 검토 하 여 적절 한 사용자만 계속 액세스 하도록 할 수 있습니다. 예:

- 새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.
- 해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.
- 해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.

이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.

자세한 내용은 [access 검토용 개요](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)를 참조 하세요.

다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.

- [그룹 및 앱](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 리소스 역할](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Azure AD 자격 관리 설정

Wiht Azure AD 자격 관리에서는 액세스 요청 워크플로, 액세스 할당, 검토 및 만료를 자동화 하 여 확장에서 id 및 액세스 수명 주기를 관리할 수 있습니다.

직원은 다양 한 그룹, 응용 프로그램 및 사이트에 액세스 하 여 작업을 수행 해야 합니다. 이러한 액세스 관리는 요구 사항이 변경 되거나, 새 응용 프로그램이 추가 되거나, 사용자에 게 추가 액세스 권한이 필요한 경우에 어려움이 있을 수 있습니다. 다른 조직과 공동 작업을 수행 하는 경우 다른 조직의 사용자가 조직의 리소스에 액세스 해야 하는 사람을 알지 못할 수 있으며, 외부 사용자는 조직에서 사용 중인 응용 프로그램, 그룹 또는 사이트를 알지 못합니다.

Azure AD 자격 관리를 통해 내부 및 외부 사용자를 위해 그룹, 응용 프로그램 및 SharePoint 사이트에 대 한 액세스를 보다 효율적으로 관리할 수 있습니다.
 
자세한 내용은 [AZURE AD 자격 관리 개요](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)를 참조 하세요.
