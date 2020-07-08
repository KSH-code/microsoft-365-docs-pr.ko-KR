---
title: 사용자에 대한 다단계 인증 설정
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
description: 조직에 대한 다단계 인증을 설정하는 방법에 대해 알아 보십시오.
monikerRange: o365-worldwide
ms.openlocfilehash: b0fd16fc74319c88a6f91bf56ac96346915c35ac
ms.sourcegitcommit: 7c1b34205746ff0690ffc774a74bdfd434256cf5
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 07/07/2020
ms.locfileid: "45049763"
---
# <a name="set-up-multi-factor-authentication"></a>다단계 인증 설정
  
[다단계 인증(MFA)에 대한 이해와 Microsoft 365](multi-factor-authentication-microsoft-365.md)에서의 지원을 바탕으로, 이제 이를 설정하고 조직에 롤아웃할 시기입니다.

시작하기 전에 다음과 같은 특수 조건이 자신에게 적용되는지 확인하고 적절한 조치를 취하십시오.

- Windows 디바이스에 Office 2013 클라이언트가 있는 경우 [최신 인증](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)을 사용하도록 설정하십시오.

- AD FS(Active Directory Federation Services)를 사용하는 타사 디렉터리 서비스가 있는 경우 Azure MFA 서버를 설정하십시오. 자세한 내용은 [Azure 다단계 인증 및 타사 VPN 솔루션을 사용한  고급 시나리오](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn)를 참조하십시오.

필요한 경우 다른 모든 사용자들은 추가 인증을 수행하라는 요청을 받습니다. 자세한 내용은 [2단계 인증 방법 및 설정](https://docs.microsoft.com/azure/active-directory/user-help/multi-factor-authentication-end-user-manage-settings#turn-on-two-factor-verification-prompts-on-a-trusted-device)을 참조하시기 바랍니다.

## <a name="step-1-decide-on-the-method-of-requiring-your-users-to-use-mfa"></a>1단계: 사용자에게 MFA를 사용하도록 요구하는 방법을 결정합니다.

> [!NOTE]
> MFA를 설정하거나 수정하려면 전역 관리자여야 합니다. 사용자가 로그인하기 위해 MFA를 사용하도록 요구하는 세 가지 방법이 있습니다. 자세한 내용은 [Microsoft 365의 MFA 지원](multi-factor-authentication-microsoft-365.md)을 참조합니다.

- 보안 기본값(소규모 기업에 권장)입니다.

  2019년 10월 21일 이후에 구독 또는 평가판을 구입한 경우 예기치 않게 MFA 메시지가 표시되면 [보안 기본값](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)이 구독에 대해 자동으로 사용되도록 설정되었습니다.
  
  모든 새 Microsoft 365 제품에는 보안 기본값이 자동으로 설정됩니다. 즉, 모든 사용자는 MFA를 설정하고 모바일 장치에 Microsoft 인증자 앱을 설치해야 합니다.

  추가 확인 방법 및 레거시 인증이 차단되므로 모든 사용자는 Microsoft 인증자 앱을 사용해야 합니다. 

- 조건부 액세스 정책(기업용으로 권장)

  사용자는 MFA 등록 시 추가 확인 방법을 선택합니다.

- 사용자별 계정(권장하지 않음)

  사용자는 MFA 등록 시 추가 확인 방법을 선택합니다.

## <a name="step-2-test-mfa-on-your-pilot-users"></a>2단계. 파일럿 사용자를 대상으로 MFA를 테스트합니다.

조건부 액세스 정책 또는 사용자별 MFA(권장하지 않음)를 사용하는 경우 기업 또는 조직의 파일럿 사용자를 선택하여 MFA 등록 및 로그인을 테스트합니다. 예를 들어 다음과 같습니다.

- 조건부 액세스 정책의 경우 그룹 구성원과 모든 앱에 대해 MFA가 필요한 정책 및 파일럿 사용자 그룹을 만듭니다. 그런 다음 파일럿 사용자의 계정을 그룹에 추가합니다.

- 사용자별 MFA의 경우 파일럿 사용자의 사용자 계정에 대해 한 번에 한 번씩 MFA를 사용하도록 설정합니다.

파일럿 사용자와 함께 질문 및 문제를 해결하여 조직에 원활한 롤아웃을 준비할 수 있습니다.

## <a name="step-3-inform-your-organization-that-mfa-is-coming"></a>3단계 MFA가 곧 시행될 것임을 조직에 알립니다.

전자 메일 알림, 복도 포스터, 팀 회의 또는 공식 교육을 통해 직원들이 다음을 이해할 수 있도록 합니다.

- 로그인 시 MFA가 필요한 이유
- [추가 확인 방법을 등록하는 방법](https://support.microsoft.com/office/ace1d096-61e5-449b-a875-58eb3d74de14)
- [등록 후 로그인하는 방법](https://support.microsoft.com/office/2b856342-170a-438e-9a4f-3c092394d3cb)
- [추가 확인 방법을 변경하는 방법](https://support.microsoft.com/office/956ec8d0-7081-4518-a701-f8414cc20831)
- [새 스마트폰과 같은 상황에 대처하는 방법](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)

가장 중요한 것은 ***MFA 요구 사항이 부과될 때*** 직원이 놀라지 않도록 직원들에게 이를 이해하도록 하는 것입니다.

## <a name="step-4-roll-out-the-mfa-requirement-to-your-organization-or-users"></a>4단계 조직 또는 사용자에게 MFA 요구사항을 전달합니다.

선택한 MFA 요구 사항 방법에 따라 파일럿 테스터 이외의 직원에게 MFA 인증을 롤아웃합니다.

### <a name="security-defaults"></a>보안 기본값

Azure 포털의 Azure Active Directory(Azure AD)에 대해 **속성** 창에서 보안 기본값을 사용하거나 사용하지 않도록 설정할 수 있습니다.

1.  전역  관리자 자격 증명으로 [Microsoft 365 관리 센터](https://admin.microsoft.com)에 로그인합니다.
2.  [Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.
3.  페이지 하단에서 **보안 기본값 관리**를 선택합니다.
4.  보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.

[기준 조건부 액세스 정책](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)을 사용해 온 경우 보안 기본값을 사용하여 이동하는 방법은 다음과 같습니다.

1.  [조건 액세스 - 정책](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ConditionalAccessBlade/Policies) 페이지로 이동합니다.
2.  **켜짐** 상태인 각 기준선 정책을 선택하고 **정책 사용**을 **끔**으로 설정합니다.
2.  [Azure Active Directory - 속성 페이지](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)로 이동합니다.
4.  페이지 하단에서 **보안 기본값 관리**를 선택합니다.
5.  보안 기본값을 사용하도록 설정하려면 **예**를 선택하고 사용하지 않도록 설정하려면 **아니요**를 선택한 다음 **저장**을 선택합니다.

### <a name="conditional-access-policies"></a>조건부 액세스 정책

로그인을 위해 MFA가 필요한 사용자 그룹을 포함하는 적절한 정책을 만들고 구성하고 실행합니다.

### <a name="per-user-mfa-not-recommended"></a>사용자별 MFA(권장하지 않음)

롤아웃에 해당하는 MFA에 대해 사용자 계정을 사용하도록 설정합니다.

### <a name="supporting-your-employees"></a>직원 지원

직원이 MFA에 등록하고 로그인하기 시작할 때 IT 전문가, IT 부서 또는 헬프데스크에서 질문에 신속하게 답변하고 문제를 해결할 수 있도록 해야 합니다.

[MFA 로그인 문제 해결에 대한 정보](https://support.microsoft.com/office/6951be76-af50-49a4-847f-21391eaa59f2)를 확인하려면 이 문서를 참조합니다. 


