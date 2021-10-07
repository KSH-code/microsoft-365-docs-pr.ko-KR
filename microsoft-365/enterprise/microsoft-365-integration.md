---
title: Microsoft 365 환경과의 통합
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
search.appverid:
- MET150
- LYN150
- SPS150
- MOE150
- MED150
ms.assetid: 263faf8d-aa21-428b-aed3-2021837a4b65
description: 이 문서에서는 기존 디렉터리 서비스 및 Microsoft 365 환경과 통합하는 방법을 알아보십시오.
ms.openlocfilehash: 06e6ff598d064f14ffb89bcf88e78932cc621225
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60198436"
---
# <a name="microsoft-365-integration-with-on-premises-environments"></a>Microsoft 365 환경과의 통합

*이 문서는 Microsoft 365 Enterprise와 Office 365 Enterprise에 모두 적용됩니다.*

기존 MICROSOFT 365 AD DS(Active Directory 도메인 서비스) 및 Exchange Server, 비즈니스용 Skype 서버 2015 또는 SharePoint Server의 사내 설치와 통합할 수 있습니다.
  
 - AD DS를 통합할 때 두 환경의 사용자 계정을 동기화하고 관리할 수 있습니다. 또한 사용자가 자신의온-프레미스 자격 증명을 사용하여 두 환경 모두에 로그온할 수 있도록 PHS(암호 해시 동기화) 또는 SSO(Single Sign-On)를 추가할 수도 있습니다.
 - 사내 서버 제품과 통합하는 경우 하이브리드 환경을 만들 수 있습니다. 하이브리드 환경은 사용자 또는 정보를 마이그레이션할 때 도움이 될 수 Microsoft 365, 또는 일부 사용자 또는 일부 정보를 계속해서 클라우드에 두는 데 도움이 될 수 있습니다. 하이브리드 환경에 대한 자세한 내용은 하이브리드 [클라우드를 참조하세요.](../solutions/cloud-architecture-models.md#hybrid)

Azure AD(Azure Active Directory)를 사용하여 사용자 지정된 설정 지침을 Microsoft 365 관리 센터 있습니다(로그인해야 Microsoft 365.

- [Azure AD 설정 가이드](https://aka.ms/aadpguidance)
- [사용자의 디렉터리에서 사용자 동기화](https://aka.ms/aadconnectpwsync)
- [AD FS(Active Directory Federation Services) 배포 어드바이저](https://aka.ms/adfsguidance)
   
## <a name="before-you-begin"></a>시작하기 전에

Microsoft 365 환경과 통합하기 전에 네트워크 계획 및 성능 조정도 [해야 합니다.](network-planning-and-performance.md) 또한 사용 가능한 ID 모델을 이해할 [수 있습니다.](about-microsoft-365-identity.md) 

사용자 [Microsoft 365](manage-microsoft-365-accounts.md) 관리하는 데 사용할 수 있는 도구 목록은 Microsoft 365 관리를 참조하세요. 
  
## <a name="integrate-microsoft-365-with-ad-ds"></a>AD Microsoft 365 통합

AD DS에 기존 사용자 계정이 있는 경우 이러한 모든 계정을 Microsoft 365 환경 간의 차이점이나 오류가 발생할 위험이 있습니다. 디렉터리 동기화를 사용하면 해당 계정을 사내 환경과 온라인 환경 간에 미러링할 수 있습니다. 디렉터리 동기화를 사용하면 사용자가 각 환경에 대한 새 정보를 기억할 필요가 없습니다. 계정을 두 번 만들거나 업데이트할 필요가 없습니다. 디렉터리 동기화를 [위해](prepare-for-directory-synchronization.md) 사내 디렉터리를 준비해야 합니다.
  
![디렉터리 동기화를 사용하여 사내 및 온라인 사용자 계정 정보를 동기화된 것으로 유지할 수 있습니다.](../media/microsoft-365-integration/directory-synchronization.png)
  
사용자가 자신의온-프레미스 자격 증명으로 Microsoft 365 로그온할 수 있도록 하려는 경우 SSO를 구성할 수도 있습니다. SSO를 Microsoft 365 인증을 위해 Microsoft 365 환경을 신뢰하도록 구성됩니다.
  
![Single Sign-On을 사용할 경우 동일한 계정을 사내 환경과 온라인 환경에서 모두 사용할 수 있습니다.](../media/microsoft-365-integration/single-sign-on.png)

### <a name="directory-synchronization-with-or-without-password-hash-synchronization-or-pass-through-authentication-pta"></a>암호 해시 동기화 또는 통과 인증(PTA)과의 디렉터리 동기화

사용자가 사용자 계정(도메인\사용자 이름)을 사용하여 자신의 사내 환경에 로그온합니다. 사용자 계정으로 Microsoft 365 경우 직장 또는 학교 계정(user@domain.com)을 사용하여 다시 로그온해야 합니다. 사용자 이름은 두 환경에서 동일합니다. PHS 또는 PTA를 추가할 때 사용자에게 두 환경 모두에 대해 동일한 암호가 사용되지만, 해당 환경으로 로그온할 때 해당 자격 증명을 다시 제공해야 Microsoft 365. PHS와의 디렉터리 동기화는 가장 일반적으로 사용되는 디렉터리 동기화입니다.

디렉터리 동기화를 설정하기 위해 Azure AD 커넥트. 자세한 내용은 [기본](set-up-directory-synchronization.md) 설정으로 Microsoft 365 Azure AD 커넥트 디렉터리 동기화 [설정을 참조하세요.](/azure/active-directory/hybrid/how-to-connect-install-express)

에서 디렉터리 동기화를 준비하는 방법을 [Microsoft 365.](prepare-for-directory-synchronization.md)

### <a name="directory-synchronization-with-sso"></a>SSO와 디렉터리 동기화

사용자가 사용자 계정을 사용하여 자신의 사내 환경에 로그온합니다. 사용자가 Microsoft 365 로그온할 때 자동으로 로그온하거나, 사용자가 자신의 Microsoft 365 환경에 사용하는 동일한 자격 증명(도메인\사용자 이름)을 사용하여 로그온합니다.

SSO를 설정하기 위해 Azure AD 응용 커넥트. 자세한 내용은 [Azure AD 2016의 사용자 지정 설치를 커넥트.](/azure/active-directory/hybrid/how-to-connect-install-custom)

자세한 내용은 [Single Sign-On 을 참조하세요.](/azure/active-directory/manage-apps/what-is-single-sign-on)

## <a name="azure-ad-connect"></a>Azure AD Connect

Azure AD 커넥트 DirSync 및 Azure AD Sync. Azure AD Azure Active Directory 동기화에서 업데이트하려는 커넥트 업그레이드 [지침을 참조하세요.](/azure/active-directory/hybrid/how-to-dirsync-upgrade-get-started) 

## <a name="see-also"></a>참고 항목

[Microsoft 365 Enterprise 개요](microsoft-365-overview.md)