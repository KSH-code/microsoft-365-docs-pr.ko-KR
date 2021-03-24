---
title: Microsoft 365 보안 및 규정 준수 센터의 권한
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
ms.audience: Admin
ms.topic: article
audience: Admin
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 보안 센터나 Microsoft 365 규정 준수 센터를 사용하여 보안 또는 규정 준수와 관련된 모든 작업에 대한 권한을 중앙에서 관리할 수 있습니다.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7cc0c69008d942e213f3a86e2852265969dd1971
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/23/2021
ms.locfileid: "51069956"
---
# <a name="permissions-in-the-microsoft-365-compliance-center-and-microsoft-365-security-center"></a>Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터의 권한

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**적용 대상**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Office 365용 Microsoft Defender 플랜 1 및 플랜 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

조직에서는 모든 Microsoft 365 서비스에 적용되는 보안 및 규정 준수 시나리오를 관리해야 합니다. 조직의 IT 그룹에 속한 적절한 사용자에게 올바른 관리자 권한을 유연하게 부여할 수 있어야 합니다. Microsoft 365 보안 센터나 Microsoft 365 규정 준수 센터를 사용하여 보안 또는 규정 준수와 관련된 모든 작업에 대한 권한을 중앙에서 관리할 수 있습니다.

전역 관리자가 이러한 관리자 역할에 사용자를 추가하면, 이러한 관리자는 Microsoft 365 보안 센터, Microsoft 365 규정 준수 센터, Azure, Office 365, Enterprise Mobility + Security와 같은 Microsoft 365의 모든 서비스에 적용되는 기능과 데이터에 액세스할 수 있습니다.

## <a name="what-the-microsoft-365-roles-are"></a>Microsoft 365 역할이란?

Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에 나타나는 역할은 Azure Active Directory 역할입니다. 이러한 역할은 조직의 IT 그룹의 직무에 맞게 설계되므로 사용자에게 업무 수행에 필요한 모든 권한을 쉽게 부여할 수 있습니다.

****

|역할|설명|
|---|---|
|**전역 관리자**|모든 Microsoft 365 서비스의 모든 관리 기능에 액세스할 수 있습니다. 전역 관리자만 다른 관리자 역할을 할당할 수 있습니다. 자세한 내용은 [전역 관리자 / 회사 관리자](/azure/active-directory/roles/permissions-reference#global-administrator--company-administrator)를 참조하세요.|
|**규정 준수 데이터 관리자**|Microsoft 365에서 조직의 데이터를 추적하고, 보호가 설정되었는지 확인하고, 위험을 완화하는 데 도움이 되는 모든 문제에 대한 인사이트를 얻으세요. 자세한 내용은 [규정 준수 데이터 관리자](/azure/active-directory/roles/permissions-reference#compliance-data-administrator)를 참조하세요.|
|**규정 준수 관리자**|조직이 모든 규정 요구 사항을 준수하고, eDiscovery 사례를 관리하며, Microsoft 365 위치, ID 및 앱 전반에서 데이터 관리 정책을 유지하도록 돕습니다. 자세한 내용은 [규정 준수 관리자](/azure/active-directory/roles/permissions-reference#compliance-administrator)를 참조하세요.|
|**보안 운영자**|Microsoft 365 사용자, 디바이스 및 콘텐츠에 대한 활성 위협을 보고, 조사하고, 대응합니다. 자세한 내용은 [보안 운영자](/azure/active-directory/roles/permissions-reference#security-operator)를 참조하세요.|
|**보안 읽기 권한자**|Microsoft 365 사용자, 디바이스 및 콘텐츠에 대한 활성 위협을 보고 조사하나 (보안 운영자와는 달리) 조치를 취하여 대응할 권한은 없습니다. 자세한 내용은 [보안 읽기 권한자](/azure/active-directory/roles/permissions-reference#security-reader)를 참조하세요.|
|**보안 관리자**|보안 정책을 관리하고, Microsoft 365 제품 전반에서 보안 분석 및 보고서를 검토하고, 위협 상황에 대한 최신 정보를 파악하여 조직의 전반적인 보안을 제어합니다. 자세한 내용은 [보안 관리자](/azure/active-directory/roles/permissions-reference#security-administrator)를 참조하세요.|
|**전역 읽기 권한자**|**전역 관리자** 역할의 읽기 전용 버전입니다. Microsoft 365 전반의 모든 설정 및 관리 정보를 봅니다. 자세한 내용은 [전역 읽기 권한자](/azure/active-directory/roles/permissions-reference#global-reader)를 참조하세요.|
|

## <a name="global-administrators-can-manage-roles-in-azure-active-directory"></a>전역 관리자는 Azure Active Directory에서 역할을 관리할 수 있습니다.

Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에서 역할을 선택하여 해당 할당을 볼 수 있습니다. 하지만 해당 과제를 관리하려면 Azure Active Directory로 이동해야 합니다.

자세한 내용은 [Azure Active Directory에서 관리자 역할 보기 및 할당](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)을 참조하세요.

![Azure Active Directory의 권한 관리 링크](../../media/permissions-manage-in-azure-ad-link.png)

## <a name="managing-roles-in-a-service-instead-of-azure-active-directory"></a>Azure Active Directory 대신 서비스에서 역할 관리

Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에 나타나는 역할은 사용자에게 권한이 있는 서비스에도 나타납니다. 예를 들어, 보안 및 준수 센터에서 이러한 역할을 볼 수 있습니다.

![보안 및 준수 센터에서 역할](../../media/m365-roles-in-o365-scc.png)

보안 및 규정 준수 센터의 역할 그룹에 대한 자세한 내용은 [보안 및 규정 준수 센터의 사용 권한](permissions-in-the-security-and-compliance-center.md)을 참조하세요.

### <a name="breaking-inheritance"></a>상속 끊기

Azure Active Directory에서 이러한 역할을 관리하는 경우에는 **모든** Microsoft 365 서비스의 역할 관리 작업을 중앙 집중식으로 수행하는 것이 중요합니다. 그러나 보안 및 준수 센터와 같은 특정 서비스에서 역할을 관리하는 경우 해당 특정 서비스에 대한 역할 **만** 관리하게 됩니다. 한 서비스의 역할에 대한 할당 및 사용 권한은 Azure Active Directory 역할에 부여된 모든 사용 권한을 재정의합니다.

이는 유용할 수 있습니다. 예를 들어, 보안 관리자 역할에 할당된 사용자는 인시던트를 관리할 권한이 없습니다. 그렇지만 엔드포인트용 Windows Defender의 사용 권한을 사용하여 해당 서비스의 인시던트 관리를 위한 특정 권한을 부여할 수 있습니다.

## <a name="where-to-find-role-information-for-each-microsoft-365-service"></a>각 Microsoft 365 서비스에 대한 역할 정보를 찾을 수 있는 위치

사용자에게 Microsoft 365 준수 또는 보안 관리자 역할 중 하나를 할당하여 Microsoft 365 서비스 범위에 대한 사용 권한을 부여합니다. 각 서비스의 역할에 대한 특정 권한과 관련된 자세한 내용을 보려면 아래 링크를 사용하세요.

****

|Microsoft 365 서비스|역할 정보|
|---|---|
|Office 365 및 Microsoft 365 비즈니스 요금제 관리자 역할|[Microsoft 365 관리자 역할](../../admin/add-users/about-admin-roles.md)|
|Azure AD(Azure Active Directory) 및 Azure AD ID 보호|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|ID용 Microsoft Defender|[ID용 Microsoft Defender 역할 그룹](/azure-advanced-threat-protection/atp-role-groups)|
|Azure Information Protection|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|규정 관리자|[규정 준수 관리자](../../compliance/compliance-manager-setup.md#set-user-permissions-and-assign-roles)|
|Exchange Online|[Exchange 역할 기반 액세스 제어](/exchange/permissions-exo/permissions-exo)|
|Intune|[Intune 역할 기반 액세스 제어](/intune/role-based-access-control)|
|Managed Desktop|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Microsoft Cloud App Security|[역할 기반 액세스 제어](/cloud-app-security/manage-admins)|
|보안 및 준수 센터|[Microsoft 365 관리자 역할](permissions-in-the-security-and-compliance-center.md)|
|Privileged Identity Management|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|보안 점수|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|SharePoint Online|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [Office 365의 SharePoint 관리자 역할 정보](/sharepoint/sharepoint-admin-role)|
|Teams/비즈니스용 Skype|[Azure AD 관리자 역할](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|엔드포인트용 Microsoft Defender|[엔드포인트용 Microsoft Defender 역할 기반 액세스 제어](/windows/security/threat-protection/windows-defender-atp/rbac-windows-defender-advanced-threat-protection)|
|

## <a name="coming-soon"></a>출시 예정

Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터의 권한과 관련해서 작업을 진행 중입니다. 예를 들어, 현재 다음 기능을 지원하고 있습니다.

- Azure Active Directory로 이동하지 않고, Microsoft 365 규정 준수 센터 및 Microsoft 365 보안 센터에서 역할을 관리합니다.
- 특정 권한을 추가하거나 제거하여 역할을 사용자 지정합니다.
- 선택한 권한을 사용하여 사용자 지정 역할을 만듭니다.