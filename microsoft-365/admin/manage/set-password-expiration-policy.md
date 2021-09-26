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
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: 0f54736f-eb22-414c-8273-498a0918678f
description: 관리자가 Microsoft 365 관리 센터에서 비즈니스, 학교 또는 비영리 단체에 대한 암호 만료 정책을 설정하는 방법을 알아보세요.
ms.openlocfilehash: 48c4df727527000cf5e2676b52fd9b39e5da733d
ms.sourcegitcommit: aebcdbef52e42f37492a7f780b8b9b2bc0998d5c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/24/2021
ms.locfileid: "59775855"
---
# <a name="set-the-password-expiration-policy-for-your-organization"></a>조직의 암호 만료 정책 설정

## <a name="before-you-begin"></a>시작하기 전에

회사, 학교 또는 비영리용 암호 만료 정책을 설정하는 사용자를 위한 문서입니다. 이 단계를 완료하려면 Microsoft 365 관리자 계정으로 로그인해야 합니다. [관리자 계정의 새로운 기능](../../business-video/admin-center-overview.md)

관리자는 특정 일 후에 사용자 암호가 만료되도록 하거나 암호가 만료되지 않도록 설정할 수 있습니다.  기본적으로 조직의 암호는 만료되지 않도록 설정됩니다.

현재 리서치에서는 강제 암호의 변경은 장점보다 단점이 많다는 것을 강하게 나타내고 있습니다. 사용자가 더 취약한 암호를 선택하거나, 암호를 재사용하거나, 해커가 손쉽게 추측할 수 있는 방식으로 기존 암호를 업데이트하도록 만듭니다. [다단계 인증](../security-and-compliance/set-up-multi-factor-authentication.md)을 사용하는 것이 좋습니다. 암호 정책에 대한 자세한 내용은 [암호 정책 권장 사항](../misc/password-policy-recommendations.md)을 참조하세요.

다음 단계를 수행하려면 [전역 관리자](../add-users/about-admin-roles.md)여야 합니다.

사용자에게는 만료일이 없는 암호를 설정할 권한이 없습니다. 회사 또는 학교의 기술 지원에 이 문서의 단계를 수행해달라고 요청하세요.

## <a name="set-password-expiration-policy"></a>암호 만료 정책 설정

특정 시간 후에 사용자 암호가 만료되도록 설정하려면 아래의 단계를 따릅니다.

1. Microsoft 365 관리 센터에서 <a href="https://go.microsoft.com/fwlink/p/?linkid=2072756" target="_blank">**보안 및 개인 정보 보호** 탭</a>으로 이동합니다.
 
    전역 관리자가 아닌 경우에는 보안 및 개인 정보 옵션이 표시되지 않습니다.
  
1. **암호 만료 정책** 을 선택합니다.
  
1. 사용자가 암호를 변경하지 않도록 하려면 **특정 일수가 지나면 사용자 암호가 만료되도록 설정** 옆의 확인란을 선택 해제합니다.
  
1. 암호가 만료되는 빈도를 입력합니다. 14에서 730 사이의 일수를 선택합니다.
  
6. 두 번째 상자에 사용자가 암호가 만료된다는 알림을 받는 시기를 입력한 다음 **저장** 을 클릭합니다. 1에서 30 사이의 일수를 선택합니다.

> [!NOTE]
> 기본 인증을 사용할 때 Office 365 포털 또는 Outlook을 제외한 모든 Office 앱에서 암호 만료 알림이 더 이상 지원되지 않습니다. 최신 인증 기능이 포함된 Outlook은 암호 만료 알림을 지원하지 않습니다.
  
## <a name="important-things-you-need-to-know-about-the-password-expiration-feature"></a>암호 만료 기능에 대해 알아야 할 중요 사항
  
Outlook 앱만 사용하는 사용자는 Microsoft 365 암호가 캐시에서 만료될 때까지 해당 암호를 강제로 재설정할 수 없습니다. 이는 실제 만료 날짜의 몇 일 이후일 수 있습니다. 관리자 수준에서는 이 문제의 해결 방법이 없습니다.

## <a name="prevent-last-password-from-being-used-again"></a>마지막 암호가 다시 사용되지 않도록 방지

사용자가 기존 암호를 재사용하지 못하도록 하려면 온-프레미스 AD(Active Directory)에 암호 기록을 적용하여 수행할 수 있습니다. [사용자 지정 암호 정책 만들기](/azure/active-directory-domain-services/password-policy#create-a-custom-password-policy)를 참조하세요.

Azure AD에서 사용자가 암호를 변경하는 경우 지난 암호를 다시 사용할 수 없습니다. 암호 정책은 Azure AD에서 직접 만들고 관리되는 모든 사용자 계정에 적용됩니다. 기본 정책은 수정할 수 없습니다. [Azure AD 암호 정책](/azure/active-directory/authentication/concept-sspr-policy#password-policies-that-only-apply-to-cloud-user-accounts)을 참조하세요.

## <a name="synchronize-user-passwords-hashes-from-an-on-premises-active-directory-to-azure-ad-microsoft-365"></a>온-프레미스 Active Directory Domain Services의 사용자 암호 해시를 Azure AD로 동기화(Microsoft 365)

이 문서는 클라우드 전용 사용자 (Azure AD)에 대한 만료 정책을 설정하기 위한 것입니다. 암호 해시 동기화, 통과 인증 또는 ADFS와 같은 온-프레미스 페더레이션을 사용하는 하이브리드 ID 사용자에게는 적용되지 않습니다.
  
온-프레미스 AD에서 Azure AD로 사용자 암호 해시를 동기화하는 방법을 알아보려면 [Azure AD Connect 동기화를 사용하여 암호 해시 동기화 구현](/azure/active-directory/hybrid/how-to-connect-password-hash-synchronization)을 참조하세요.

## <a name="password-policies-and-account-restrictions-in-azure-active-directory"></a>Azure Active Directory의 암호 정책 및 제한

Azure Active Directory에서 더 많은 암호 정책 및 제한을 설정할 수 있습니다. 더 자세한 정보는 [Azure Active Directory의 암호 정책 및 제한](/azure/active-directory/authentication/concept-sspr-policy)에서 확인하세요.

## <a name="update-password-policy"></a>암호 정책 업데이트

Set-MsolPasswordPolicy cmdlet은 지정된 도메인 또는 테넌트의 암호 정책을 업데이트합니다. 두 가지 설정이 필요합니다. 첫 번째는 암호 변경 전까지 유효 기간을 표시하고 두 번째는 사용자가 만료 예정에 대한 미리 알림을 처음 받는 암호 만료일 전 일 수를 표시하는 것입니다.

특정 도메인 또는 테넌트에 대한 암호 정책을 업데이트하는 방법에 대한 자세한 내용은 [Set-MsolPasswordPolicy](/powershell/module/msonline/set-msolpasswordpolicy)를 참조하세요.

## <a name="related-content"></a>관련 콘텐츠

[사용자가 암호를 직접 재설정할 수 있도록 허용](../add-users/let-users-reset-passwords.md)(문서)\

[암호 다시 설정](../add-users/reset-passwords.md)(문서)
