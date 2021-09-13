---
title: Microsoft 365 전용 ID
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Microsoft 365 구독에서 클라우드 전용 ID를 사용하는 경우 사용자 및 그룹을 만드는 방법에 대해 설명하는 문서입니다.
ms.openlocfilehash: 9b58b831f2a338e5fb79726b8de66c11bba96d0e
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59192839"
---
# <a name="microsoft-365-cloud-only-identity"></a>Microsoft 365 전용 ID

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

클라우드 전용 ID를 사용하여 모든 사용자, 그룹 및 연락처는 Azure Active Directory 구독의 Azure Active Directory(Azure AD) 테넌트에 Microsoft 365 저장됩니다. 다음은 클라우드 전용 ID의 기본 구성 요소입니다.
 
![클라우드 전용 ID의 기본 구성 요소입니다.](../media/about-microsoft-365-identity/cloud-only-identity.png)

조직의 사용자 및 해당 사용자 계정은 여러 가지 방법으로 분류할 수 있습니다. 예를 들어 일부는 직원으로, 영구적 상태입니다. 일부는 임시 상태인 공급업체, 계약자 또는 파트너입니다. 사용자 계정이 없지만 상호 작용 및 공동 작업을 지원하기 위해 특정 서비스 및 리소스에 대한 액세스 권한을 부여받아야 하는 외부 사용자도 있습니다. 예:

- 테넌트 계정은 클라우드 서비스에 대한 라이선스를 부여한 조직 내부의 사용자를 나타냅니다.

- B2B 계정은 공동 작업에 참여하도록 초대한 조직 외부의 사용자를 나타냅니다.

조직의 사용자 유형에 대한 정보를 제공합니다. 그룹화란? 예를 들어 조직에 대한 높은 수준의 기능 또는 목적에 따라 사용자를 그룹화할 수 있습니다.

또한 일부 클라우드 서비스는 사용자 계정 없이 조직 외부의 사용자와 공유될 수 있습니다. 이러한 사용자 그룹도 식별해야 합니다.

클라우드 환경 관리를 간소화하는 여러 가지 목적으로 Azure AD의 그룹을 사용할 수 있습니다. 예를 들어 Azure AD 그룹을 사용하여 다음을 할 수 있습니다.

- 그룹 기반 라이선스를 사용하여 구성원으로 추가되는 Microsoft 365 계정에 라이선스를 자동으로 할당합니다.
- 부서 이름과 같은 사용자 계정 특성에 따라 특정 그룹에 사용자 계정을 동적으로 추가합니다.
- SaaS(Software as a Service) 응용 프로그램을 자동으로 프로비전하고 MFA(다단계 인증) 및 기타 조건부 액세스 정책을 사용하여 해당 응용 프로그램에 대한 액세스를 보호합니다.
- 온라인 팀 사이트에 대한 사용 SharePoint 수준 프로비전합니다.

## <a name="next-steps-for-cloud-only-identity"></a>클라우드 전용 ID에 대한 다음 단계

- [사용자 계정 관리](manage-microsoft-365-accounts.md)
- [사용자 계정에 라이선스 할당](assign-licenses-to-user-accounts.md)
- [그룹 및 그룹 구성원 관리](manage-microsoft-365-groups.md)
- [사용자 계정 암호 관리](manage-microsoft-365-passwords.md)
