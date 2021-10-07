---
title: Microsoft 365 그룹 관리
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: 그룹 관리 방법에 대해 Microsoft 365 자세히 알아보아야 합니다.
ms.openlocfilehash: 28d8bae8aaed6d02fe082824c07afe03bdc0ce5a
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150765"
---
# <a name="manage-microsoft-365-groups"></a>Microsoft 365 그룹 관리

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

구성에 Microsoft 365 여러 가지 방법으로 그룹 그룹을 관리할 수 있습니다. azure AD(Active Directory [도메인 서비스)](/admin)관리 Microsoft 365 관리 센터, AD DS(Active Directory 도메인 [서비스)](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)또는 Azure Active Directory 관리 센터에서 사용자 계정을 관리할 수 있습니다. 

## <a name="plan-for-where-and-how-you-will-manage-your-groups"></a>그룹 관리 위치 및 방법 계획

사용자 계정을 관리하는 위치 및 방법은 사용자 계정의 ID 모델에 따라 Microsoft 365. 두 가지 전체 모델은 클라우드 전용 및 하이브리드입니다.
  
### <a name="cloud-only"></a>클라우드 전용

다음을 사용하여 그룹을 만들고 관리합니다.

- [Microsoft 365 관리 센터](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 관리 센터](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)
    
### <a name="hybrid"></a>하이브리드

AD DS 그룹은 AD DS의 Microsoft 365 동기화되어 있으므로 이러한 그룹을 관리하려면 사내 AD DS 도구를 사용해야 합니다.

AD DS 그룹과는 별개이지만 AD DS의 사용자 및 그룹을 포함할 수 있는 Azure AD 그룹을 만들고 관리할 수도 있습니다. 이 경우 다음을 사용할 수 있습니다.

- [Microsoft 365 관리 센터](/admin)
- [PowerShell](maintain-group-membership-with-microsoft-365-powershell.md)
- [Azure AD 관리 센터](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)

## <a name="allow-users-to-create-and-manage-their-own-groups"></a>사용자가 자신의 그룹을 만들고 관리하도록 허용하십시오.

Azure AD는 IT 관리자 대신 그룹 소유자가 관리할 수 있는 그룹을 허용합니다. *셀프 서비스 그룹 관리* 로 알려진 기능은 관리역할이 할당되지 않은 그룹 소유자가 보안 그룹을 생성하고 관리할 수 있도록 해줍니다. 

사용자는 보안 그룹에서 구성원을 요청할 수 있으며, 이 요청은 IT 관리자가 아니라 그룹 소유자에게 전달됩니다. 이를 통해 그룹의 비즈니스 사용을 이해하고 해당 구성원을 관리할 수 있는 팀, 프로젝트 또는 비즈니스 소유자에게 일상적인 그룹 구성원 제어를 위임할 수 있습니다.

>[!Note]
>셀프 서비스 그룹 관리는 Azure AD 보안 및 Microsoft 365 그룹에서만 사용할 수 있습니다. 메일 사용 가능 그룹, 메일 그룹 또는 AD DS에서 동기화된 그룹에는 사용할 수 없습니다.
>

자세한 내용은 [셀프 서비스 관리에 대한 Azure AD(Microsoft Azure Active Directory) 그룹 구성 지침](/azure/active-directory/active-directory-accessmanagement-self-service-group-management)을 참조하십시오.

## <a name="set-up-dynamic-group-membership"></a>동적 그룹 구성원 설정

Azure AD는 Azure AD 그룹의 구성원으로 사용자 계정을 자동으로 추가하거나 제거하는 일련의 규칙을 구성할 수 있습니다. 이를 *동적 그룹 구성원* 이라고 합니다. 이 규칙은 부서나 국가와 같은 사용자 계정 속성을 기반으로 하고 있습니다.

규칙이 적용되는 방식은 다음과 같습니다.

- 새 사용자 계정이 그룹에 대한 모든 규칙과 일치하는 경우 구성원이 됩니다.
- 사용자가 그룹의 구성원이 아니지만 해당 속성이 그룹에 대한 모든 규칙과 일치하도록 변경되는 경우 해당 그룹의 구성원이 됩니다.
- 사용자 계정이 그룹에 대한 일부 규칙과 일치하지 않는 경우 그룹에 추가되지 않습니다.
- 사용자가 그룹의 구성원이지만 해당 속성이 그룹에 대한 모든 규칙과 더 이상 일치하지 않도록 변경되는 경우 그룹의 구성원에서 제거됩니다.

동적 구성원을 사용하려면 먼저 공통적인 사용자 계정 속성 집합이 있는 그룹 집합 확인해야 합니다. 예를 들어 Sales 부서의 모든 구성원은 “Sales”로 설정된 Department 사용자 계정 특성에 따라 Sales Azure AD 그룹에 속해야 합니다.

[동적 Azure AD 그룹에 대한 규칙을 만들고 구성하는 지침](/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)을 참조하세요.

## <a name="set-up-automatic-licensing"></a>자동 라이선싱 설정

Azure AD에서 보안 그룹을 구성하여 구독 집합의 라이선스를 그룹의 모든 구성원에게 자동으로 할당할 수 있습니다. 이를 *그룹 기반 라이센싱* 이라고 합니다. 사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 계정에서 자동으로 할당되거나 할당 해제됩니다.

Microsoft 365 Enterprise의 경우 적절한 Microsoft 365 Enterprise 라이선스를 할당하도록 Azure AD 보안 그룹을 구성합니다.

모든 그룹 구성원에 대한 충분한 라이센스가 있는지 확인합니다. 라이선스가 부족할 경우 라이선스를 사용할 수 있게 될 때까지 신규 사용자에게 라이선스가 할당되지 않습니다.

>[!Note]
>Azure B2B 계정이 포함된 그룹에 대해 그룹 기반 라이선싱을 구성해서는 안 됩니다.
>

자세한 내용은 Azure AD의 그룹 [기반 라이선싱 기본 정보를 참조하세요.](/azure/active-directory/active-directory-licensing-whatis-azure-portal)

Azure 보안 그룹에 대한 그룹 [기반 라이선싱을 구성하는 지침을 참조하세요.](/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)