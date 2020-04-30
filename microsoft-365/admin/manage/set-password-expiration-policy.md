---
title: 조직의 암호 만료 정책 설정
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 'Microsoft 365 관리 센터에서 조직에 대한 암호 만료 정책을 설정하는 방법을 알아봅니다. '
ms.openlocfilehash: dd925ee3a5d2aadb07dceed5a0e896e77921e2a1
ms.sourcegitcommit: b6c4b514b2cb6739af949780d7e2a5a5c8dcc161
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/27/2020
ms.locfileid: "43901013"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>조직의 암호 만료 정책 설정

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다.  

사용자에게는 만료일이 없는 암호를 설정할 권한이 없습니다. 회사 또는 학교의 기술 지원에 문의하여 이 문서의 단계를 수행합니다.

관리자는 특정 일수 후에 사용자 암호가 만료되도록 하거나 암호가 만료되지 않도록 설정할 수 있습니다.  

> [!Tip]
> 기본적으로 암호는 90일 이내에 만료되도록 설정됩니다. 현재 리서치에서는 강제 암호의 변경은 장점보다 단점이 많다는 것을 강하게 나타내고 있습니다. 사용자가 더 취약한 암호를 선택하거나, 암호를 재사용하거나, 해커가 손쉽게 추측할 수 있는 방식으로 기존 암호를 업데이트하도록 만듭니다. 암호가 만료되지 않도록 설정하는 경우 [다단계 인증](../security-and-compliance/set-up-multi-factor-authentication.md)을 사용하는 것이 좋습니다.

특정 시간 후에 사용자 암호가 만료되도록 설정하려면 아래의 단계를 따릅니다.
> [!IMPORTANT]
> [전역 관리자](../add-users/about-admin-roles.md)만 이러한 단계를 수행할 수 있습니다.
  
1. 관리 센터에서 **설정** \> **설정**으로 이동합니다.

2. <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">보안 및 개인 정보</a> 페이지로 이동합니다.
 전역 관리자가 아닌 경우에는 보안 및 개인 정보 옵션이 표시되지 않습니다.
  
3. **암호 만료 정책**을 선택합니다.
  
4. 사용자가 암호를 변경하지 않도록 하려면 **특정 일수가 지나면 사용자 암호가 만료되도록 설정** 옆의 확인란을 선택합니다.
  
5. 암호가 만료되는 빈도를 입력합니다. 14에서 730 사이의 일수를 선택합니다.
  
6. 두 번째 상자에 사용자가 암호가 만료된다는 알림을 받는 시기를 입력한 다음 **저장**을 클릭합니다. 1에서 30 사이의 일수를 선택합니다.
    
7. 사용자의 암호가 만료되면 화면 오른쪽 아래에 나타나는 알림이 표시됩니다.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>암호 만료 기능에 대해 알아야 할 중요 사항

다음은 2018년 1월 현재 이 기능의 작동 방식에 대해 알아야 할 몇 가지 사항입니다.
  
- Outlook 앱만 사용하는 사용자는 Microsoft 365 암호가 캐시에서 만료될 때까지 해당 암호를 강제로 재설정할 수 없습니다. 이는 실제 만료 날짜의 몇 일 이후일 수 있습니다. 관리자 수준에서는 이 문제의 해결 방법이 없습니다.
    
- 사용자는 암호가 X일 내에 만료될 것이라는 전자 메일 알림을 받지 않습니다. 이 기능을 원하시나요? **[여기에서 투표하세요.](https://office365.uservoice.com/forums/273493-office-365-admin/suggestions/15028344-office-365-password-email-notification)**
    
## <a name="prevent-last-password-from-being-used-again"></a>마지막 암호가 다시 사용되지 않도록 방지

사용자가 이전 암호를 다시 사용하지 못하도록 하면 Azure AD에서도 이전 암호를 다시 사용할 수 없습니다. [암호 기록 적용](https://docs.microsoft.com/windows/security/threat-protection/security-policy-settings/enforce-password-history)을 참조하세요.

또한 직원이 모바일 장치를 사용하여 Microsoft 365에 액세스하는 경우 해당 장치를 초기화하여 암호가 더 이상 저장 및 재사용되지 않도록 할 수 있습니다. 자세한 내용은 [이전 직원의 모바일 장치 초기화 및 차단](https://docs.microsoft.com/office365/admin/add-users/remove-former-employee?view=o365-worldwide#wipe-and-block-a-former-employees-mobile-device)을 참조하세요.


## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>온-프레미스 Active Directory Domain Services의 사용자 암호 해시를 Azure AD로 동기화(Microsoft 365)

이 문서는 클라우드 전용 사용자 (Azure AD)에 대한 만료 정책을 설정하기 위한 것입니다. 암호 해시 동기화, 통과 인증 또는 ADFS와 같은 온-프레미스 페더레이션을 사용하는 하이브리드 ID 사용자에게는 적용되지 않습니다.
  
온-프레미스 AD에서 Azure AD로 사용자 암호 해시를 동기화하는 방법을 알아보려면 [Azure AD Connect 동기화를 사용하여 암호 해시 동기화 구현](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)을 참조하세요.
