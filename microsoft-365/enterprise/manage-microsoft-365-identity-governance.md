---
title: ID Microsoft 365 관리
ms.author: kvice
author: kelleyvice-msft
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
description: ID 거버넌스 기능을 사용하는 Microsoft 365 대해 자세히 알아보습니다.
ms.openlocfilehash: 9b353a83b79c2b66ca224914a7d33a4854919d4e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59221020"
---
# <a name="manage-microsoft-365-identity-governance"></a>ID Microsoft 365 관리

ID 거버넌스는 직원 생산성을 보장하면서 중요한 자산에 대한 액세스를 보호, 모니터링 및 감사하는 것입니다. 예를 들어 ID 거버넌스를 사용하는 경우 올바른 사용자에게 올바른 리소스에 대한 올바른 액세스 권한이 있는지 확인하고, 해당 액세스 권한이 시간에 따라 변경되는지 확인할 수 있습니다.

자세한 내용은 Azure [AD(Azure AD)의 ID 거버넌스 개요를 Azure Active Directory 참조하세요.](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>Azure AD 액세스 검토 설정

Azure AD 액세스 검토를 사용하면 사용자의 액세스를 검토하여 올바른 사용자만 계속 액세스할 수 있도록 할 수 있습니다. 예:

- 새 직원이 조직에 들어오면 올바른 액세스 권한을 제공하여 생산적으로 작업할 수 있도록 해야 합니다.
- 해당 직원이 다른 팀, 위치 또는 부서로 이동하게 되면 필요에 따라 이전 팀, 위치 또는 부서에 대한 액세스 권한이 제거되도록 해야 합니다.
- 해당 직원이나 게스트가 조직에서 나갈 때 해당 액세스 권한이 제거되도록 해야 합니다.

이러한 작업은 조직이 사용자 계정에 너무 많은 액세스 권한이 있는지 확인하고 산업 또는 지역 규정을 위반할 경우 벌금을 매길 수 있는 보안 감사를 받고 있는 경우에 특히 중요합니다.

자세한 내용은 액세스 검토 [개요를 참조하세요.](/azure/active-directory/governance/access-reviews-overview)

다양한 유형의 액세스 검토를 구성하려면 다음 문서를 참조하세요.

- [그룹 및 앱](/azure/active-directory/governance/create-access-review)
- [Azure AD 역할](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 리소스 역할](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>Azure AD 권리 관리 설정

Wiht Azure AD 권리 부여 관리를 사용하면 액세스 요청 워크플로, 액세스 할당, 검토 및 만료를 자동화하여 ID 및 액세스 수명 주기를 대규모로 관리할 수 있습니다.

직원은 작업을 수행하기 위해 다양한 그룹, 응용 프로그램 및 사이트에 액세스해야 합니다. 요구 사항이 변경되거나, 새 응용 프로그램이 추가되거나, 사용자에게 추가 액세스 권한이 필요하기 때문에 이 액세스를 관리하는 것은 어려울 수 있습니다. 다른 조직과 공동 작업할 때 다른 조직의 사용자가 조직의 리소스에 액세스해야 하는지 알 수 없는 경우, 외부 사용자는 조직에서 사용하는 응용 프로그램, 그룹 또는 사이트를 알 수 없습니다.

Azure AD 권리 부여 관리를 사용하면 내부 및 외부 사용자를 위한 그룹, 응용 프로그램 및 SharePoint 액세스 권한을 보다 효율적으로 관리할 수 있습니다.
 
자세한 내용은 Azure AD 권리 관리 [개요를 참조하세요.](/azure/active-directory/governance/entitlement-management-overview)