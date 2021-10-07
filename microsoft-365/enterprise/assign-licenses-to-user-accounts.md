---
title: 사용자 Microsoft 365 라이선스 할당
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 개별적으로 또는 그룹 멤버 자격에 따라 Microsoft 365 계정에 라이선스를 할당하는 방법에 대해 설명
ms.openlocfilehash: dd941be0d257aa356cf6e69bfdd59a8d1743ed93
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159465"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a>사용자 Microsoft 365 라이선스 할당

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

클라우드 전용 ID 모델의 경우 사용자 Microsoft 365 만드는 방법에 따라 사용자 계정에 라이선스를 할당할 수 있습니다.

하이브리드 ID 모델의 경우 AD DS(Active Directory 도메인 서비스) 사용자 계정이 처음으로 동기화될 때 위치 또는 Microsoft 365 할당되지 않습니다. **라이선스 할당 전 또는 할당과 함께 사용자 위치로 각 사용자 계정을 구성해야 합니다.**

두 경우 모두 사용자가 전자 메일 및 메일과 같은 Microsoft 365 서비스에 액세스할 수 있도록 사용자 계정에 라이선스를 할당해야 Microsoft Teams.

그룹 구성원 자격을 통해 개별적으로 또는 자동으로 사용자 계정에 라이선스를 할당할 수 있습니다.

개별 Microsoft 365 라이선스를 할당하기 위해 다음을 사용할 수 있습니다.

- [Microsoft 365 관리 센터](../admin/manage/assign-licenses-to-users.md)
- [PowerShell](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- Azure AD 관리 센터

## <a name="group-based-licensing"></a>그룹 기반 라이선스

Azure AD에서 보안 그룹을 구성하여 구독 집합의 라이선스를 그룹의 모든 구성원에게 자동으로 할당할 수 있습니다. 이를 *그룹 기반 라이센싱* 이라고 합니다. 사용자 계정이 그룹에 추가되거나 제거된다면 그룹 구독 라이센스는 사용자 계정에서 자동으로 할당되거나 할당 해제됩니다.

모든 그룹 구성원에 대한 충분한 라이센스가 있는지 확인합니다. 라이선스가 부족할 경우 라이선스를 사용할 수 있게 될 때까지 신규 사용자에게 라이선스가 할당되지 않습니다.

>[!Note]
>Azure B2B 계정이 포함된 그룹에 대해 그룹 기반 라이선싱을 구성해서는 안 됩니다.
>

자세한 내용은 Azure AD의 그룹 [기반 라이선싱을 참조하세요.](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)

## <a name="next-steps"></a>다음 단계

라이선스가 할당된 적절한 사용자 계정 집합을 통해 이제 다음을 할 준비가 된 것입니다.

- [보안 구현](../security/office-365-security/security-roadmap.md)
- [클라이언트 소프트웨어 배포(예: Microsoft 365 앱](/DeployOffice/deployment-guide-microsoft-365-apps)
- [장치 관리 설정](device-management-roadmap-microsoft-365.md)
- [서비스 및 응용 프로그램 구성](configure-services-and-applications.md)