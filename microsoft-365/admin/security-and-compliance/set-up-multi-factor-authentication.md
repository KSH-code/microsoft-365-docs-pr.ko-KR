---
title: 사용자를 위한 대한 다단계 인증 설정
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: 조직에 대해 multi-factor authentication을 설정 하는 방법을 알아봅니다.
monikerRange: o365-worldwide
ms.openlocfilehash: 9218e81aaf016c379c6ba8c7ae846a2a2132cf35
ms.sourcegitcommit: eee4f651bd51d5aedd64e42d02bfed8ccb9be4cd
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/02/2020
ms.locfileid: "44515810"
---
# <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정
  
[Microsoft 365에서 MFA (multi-factor authentication) 및 해당 지원](multi-factor-authentication-microsoft-365.md)에 대 한 이해를 바탕으로이를 설정 하 고 조직에 롤아웃할 수 있습니다.

시작 하기 전에 이러한 특수 조건이 사용자에 게 적용 되는지 확인 하 고 적절 한 조치를 취해야 합니다.

- Windows 장치에 Office 2013 클라이언트가 있는 경우 [최신 인증을 사용 하도록 설정](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)합니다.

- AD FS (Active Directory Federation Services)와 타사 디렉터리 서비스를 사용 하는 경우에는 Azure MFA 서버를 설정 합니다. 자세한 내용은 [Azure Multi-factor Authentication 및 타사 VPN 솔루션의 고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) 를 참조 하세요.


필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다. 자세한 내용은 [2 단계 인증 방법 및 설정을](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)참조 하세요.

=======
## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>1 단계: 사용자에 게 MFA를 사용 하도록 요구 하는 방법 결정

> [!NOTE]
> MFA를 설정 하거나 수정 하려면 전역 관리자 여야 합니다. 사용자가 로그인을 위해 MFA를 사용 하도록 요구 하는 방법에는 세 가지가 있습니다. 자세한 내용은 [Microsoft 365에서 MFA 지원를](multi-factor-authentication-microsoft-365.md) 참조 하세요.

- 보안 기본값 (small 비즈니스에 대해 권장)

  2019 년 10 월 21 일 이후에 구독 또는 평가판을 구매한 경우 MFA를 예기치 않게 묻는 메시지가 표시 되 면 구독에 대해 [보안 기본값이](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults) 자동으로 사용 하도록 설정 된 것입니다.
  
  모든 새 Microsoft 365 구독에는 자동으로 보안 기본값이 설정 됩니다. 즉, 모든 사용자가 자신의 모바일 장치에 MFA를 설정 하 고 Microsoft Authenticator 앱을 설치 해야 합니다.

  모든 사용자는 Microsoft Authenticator 앱을 추가 확인 방법으로 사용 해야 하며 레거시 인증은 차단 됩니다. 

- 조건부 액세스 정책 (엔터프라이즈에 대해 권장)

  사용자는 MFA 등록 중에 추가 확인 방법을 선택 합니다.

- 사용자별 계정 (권장 하지 않음)

  사용자는 MFA 등록 중에 추가 확인 방법을 선택 합니다.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>2단계. 파일럿 사용자에 대해 MFA 테스트

조건부 액세스 정책 또는 사용자별 MFA (권장 하지 않음)를 사용 하는 경우에는 회사나 조직의 파일럿 사용자를 선택 하 여 MFA 등록 및 로그인을 테스트 합니다. 예를 들어:

- 조건부 액세스 정책에 대해 파일럿 사용자 그룹 및 그룹 구성원과 모든 앱에 대해 MFA를 요구 하는 정책을 만듭니다. 그런 다음 파일럿 사용자 계정을 그룹에 추가 합니다.

- 사용자 단위 MFA의 경우 파일럿 사용자의 사용자 계정에 대해 한 번에 하나씩 MFA를 사용 하도록 설정 합니다.

파일럿 사용자와 협력 하 여 조직의 원활한 롤아웃을 준비할 수 있도록 질문과 문제를 해결 합니다.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>3단계. 사용자에 게 MFA가 출시 되었음을 조직에 알리기

다음과 같이 직원 들이 이해할 수 있도록 전자 메일 알림, hallway 포스터, 팀 회의 또는 공식적인 교육을 사용 합니다.

- 로그인에 MFA가 필요한 이유
- [추가 확인 방법에 등록 하는 방법](https://support.office.com/article/set-up-your-microsoft-365-sign-in-for-multi-factor-authentication-ace1d096-61e5-449b-a875-58eb3d74de14?ui=en-US&rs=en-001&ad=US)
- [등록 후 로그인 하는 방법](https://support.office.com/article/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)
- [추가 확인 방법을 변경 하는 방법](https://support.office.com/article/change-how-you-do-additional-verification-956ec8d0-7081-4518-a701-f8414cc20831)
- [새 smart 전화와 같은 상황을 처리 하는 방법](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)

가장 중요 한 점은 ***MFA 요구 사항을*** 예기치 않게 설정 하는 경우 직원이이를 이해 하 고 있는지 확인 하는 것입니다.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>4단계. 조직 또는 사용자에 게 MFA 요구 사항 롤아웃

선택한 MFA 요구 사항 방법을 기반으로 파일럿 테스터가 아닌 직원에 게 MFA 인증을 배포 합니다.

### <a name="security-defaults"></a>보안 기본값

Azure portal의 azure Active Directory (Azure AD)에 대 한 **속성** 창에서 보안 기본값을 사용 하거나 사용 하지 않도록 설정 합니다.

1.  전역 관리자 자격 증명을 사용 하 여 [Microsoft 365 관리 센터](https://admin.microsoft.com) 에 로그인 합니다.
2.  [Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.
3.  페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.
4.  보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 **선택 합니다.**

[기준 조건부 액세스 정책을](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)사용 하 고 있는 경우 보안 기본값을 사용 하 여 이동 하는 방법이 여기에 해당 됩니다.

1.  [조건부 액세스-정책 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies)이동 합니다.
2.  설정 된 각 기본 정책을 선택 **하 고** **정책 사용** 을 **해제**합니다.
2.  [Azure Active Directory-속성 페이지로](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)이동 합니다.
4.  페이지 맨 아래에서 **보안 기본값 관리**를 선택합니다.
5.  보안 기본값을 사용 하려면 **예** 를 선택 하 고 보안 기본값을 사용 하지 않으려면 **아니요** 를 **선택 합니다.**

### <a name="conditional-access-policies"></a>조건부 액세스 정책

로그인을 위해 MFA를 필요로 하는 사용자 그룹을 포함 하는 적절 한 정책을 만들고 구성 하 고 사용 하도록 설정 합니다.

### <a name="per-user-mfa-not-recommended"></a>사용자별 MFA (권장 하지 않음)

롤아웃에 해당 하는 MFA에 대해 사용자 계정을 사용 하도록 설정 합니다.

### <a name="supporting-your-employees"></a>직원 지원

직원이 MFA에 등록 하 고 로그인을 시작할 때 IT 전문가, IT 부서 또는 지원 자가 질문에 답하고 문제를 빠르게 해결할 수 있도록 합니다.

[MFA 로그인 문제 해결에 대 한 자세한 내용은](https://support.office.com/article/fix-common-problems-with-multi-factor-authentication-6951be76-af50-49a4-847f-21391eaa59f2)이 문서를 참조 하세요. 


