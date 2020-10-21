---
title: 사용자에 대한 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 8f0454b2-f51a-4d9c-bcde-2c48e41621c6
description: 조직에 대한 다단계 인증을 설정하는 방법에 대해 알아 보십시오.
monikerRange: o365-worldwide
ms.openlocfilehash: 609f6d929408dd15ff6f296dc405448140726c89
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644846"
---
# <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정
  
[다단계 인증(MFA)에 대한 이해와 Microsoft 365](multi-factor-authentication-microsoft-365.md)에서의 지원을 바탕으로, 이제 이를 설정하고 조직에 롤아웃할 시기입니다.

> [!IMPORTANT]
> 2019년 10월 21일 이후에 구독 또는 평가판을 구매한 경우 로그인할 때 MFA 메시지가 표시되면 [보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)이 구독에 대해 자동으로 사용되도록 설정된 것입니다.


## <a name="before-you-begin"></a>시작하기 전에

- MFA를 관리하려면 전역 관리자여야 합니다. 자세한 내용은 [관리자 역할 정보](../add-users/about-admin-roles.md)를 참조하세요.
- 사용자마다 MFA가 켜진 경우에는 [사용자마다 레거시 MFA를 해제하세요](#turn-off-legacy-per-person-mfa).
- Windows 장치에 Office 2013 클라이언트가 있는 경우 [Office 2013 클라이언트에 대한 최신 인증을 켜세요](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication).
- 고급: AD FS(Active Directory Federation Services)를 사용하는 타사 디렉터리 서비스가 있는 경우 Azure MFA 서버를 설정하세요. 자세한 내용은 [Azure 다단계 인증 및 타사 VPN 솔루션을 사용한 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)를 참조하세요.

## <a name="turn-security-defaults-on-or-off"></a>보안 기본값 설정 또는 해제하기

대부분의 조직에서 보안 기본값은 적절한 수준의 추가 로그인 보안을 제공합니다. 자세한 내용은 [보안 기본값이란?](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)을 참조하세요.

신규 구독이면 보안 기본값이 이미 자동으로 설정되었을 수 있습니다.

Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.

1.  전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.
2.  왼쪽 탐색 메뉴에서 **모두 표시**를 선택하고 **관리 센터**에서 **Azure Active Directory**를 선택합니다.
3. **Azure Active Directory 관리 센터**에서 **Azure Active Directory** > **속성**을 선택합니다.
3.  페이지 하단에서 **보안 기본값 관리**를 선택합니다.
4.  보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.

[기준 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)을 사용해 온 경우 보안 기본값을 사용하기 위해 이동하기 전에 정잭을 해제하라는 메시지가 표시됩니다.

1.  [조건 액세스 - 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 페이지로 이동합니다.
2.  **켜짐** 상태인 각 기준선 정책을 선택하고 **정책 사용**을 **끔**으로 설정합니다.
2.  [Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.
4.  페이지 하단에서 **보안 기본값 관리**를 선택합니다.
5.  보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.

## <a name="use-conditional-access-policies"></a>조건부 액세스 정책 사용하기

조직에 더 세분화된 로그인 보안 요구 사항이 있으면 조건부 액세스 정책에서 더 많은 제어권을 제공할 수 있습니다. 조건부 액세스를 사용하면 사용자에게 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 로그인 이벤트에 반응하고 추가 작업을 요청하는 정책을 만들고 정의할 수 있습니다. 

> [!IMPORTANT]
> 조건부 액세스 정책을 사용하기 전에 사용자마다 MFA와 보안 기본값을 모두 해제합니다. 

조건부 액세스는 Azure AD Premium P1 또는 이를 포함하는 라이선스(예: Microsoft 365 Business Premium 및 Microsoft 365 E3)를 구매한 고객이 사용할 수 있습니다. 자세한 내용은 [조건부 액세스 정책 만들기](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-azure-mfa)를 참조하세요.

위험 기반 조건부 액세스는 Azure AD Premium P2 라이선스 또는 Microsoft 365 E5와 같이 이를 포함하는 라이선스를 통해 사용할 수 있습니다. 자세한 내용은 [위험에 기반한 조건부 액세스](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-risk)를 참조하세요.

Azure AD P1 및 P2에 대한 자세한 내용은 [Azure Active Directory 가격](https://azure.microsoft.com/pricing/details/active-directory/)을 참조하세요.

### <a name="turn-on-modern-authentication-for-your-organization"></a>조직에 대한 최신 인증 설정하기

대부분의 구독에서 최신 인증이 자동으로 설정되어 있지만 오래전에 구독을 구매한 경우에는 설정되어 있지 않을 수 있습니다. MFA가 Office 앱에서 제대로 작동하려면 설정되어 있어야 합니다.

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **설정** > **조직 설정**을 선택합니다.
1. **서비스** 탭에서 **최신 인증**을 선택하고, **최신 인증** 창에서 **최신 인증 사용**이 선택되어 있는지 확인합니다. **변경 내용 저장**을 선택합니다.

### <a name="turn-off-legacy-per-person-mfa"></a>사용자마다 레거시 MFA 해제하기

이전에 사용자마다 MFA를 설정한 경우 보안 기본값을 사용하기 전에 먼저 이 기능을 해제해야 합니다.

1. Microsoft 365 관리 센터의 왼쪽 탐색 창에서 **사용자** > **활성 사용자**를 선택합니다. 
1. **활성 사용자** 페이지에서 **다단계 인증**을 선택합니다.
1. 다단계 인증 페이지에서 각 사용자를 선택하고 다단계 인증 상태를 **사용 안 함**으로 설정합니다.

## <a name="next-steps"></a>다음 단계
- [추가 확인 방법을 등록하는 방법](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [다단계 인증이란](https://support.microsoft.com/help/4577374/what-is-multifactor-authentication)
- [등록 후 로그인하는 방법](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [추가 확인 방법을 변경하는 방법](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)





