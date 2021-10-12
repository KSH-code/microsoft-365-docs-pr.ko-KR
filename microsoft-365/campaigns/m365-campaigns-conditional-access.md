---
title: 보안 기본값 켜기
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- M365-Campaigns
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
- MOE150
description: 보안 기본값이 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 어떻게 도움이 될 수 있는지 확인합니다.
ms.openlocfilehash: ce8cd568fa452aa6c4ff9b03cf2a17ed57d959b6
ms.sourcegitcommit: df1ad7118c4a95a310a4f17124322a6ae6ace26f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/11/2021
ms.locfileid: "60268697"
---
# <a name="turn-on-security-defaults"></a>보안 기본값 켜기

보안 기본값은 Microsoft가 조직을 대신하여 관리하는 미리 구성한 보안 설정을 제공하여 ID 관련 공격으로부터 조직을 보호하는 데 도움이 됩니다. 이러한 설정에는 모든 관리자 및 사용자 계정에 대해 MFA(다단계 인증)를 사용하도록 설정하는 것이 포함됩니다. 대부분의 조직에서 보안 기본값은 좋은 수준의 추가 로그인 보안을 제공합니다.

보안 기본값 및 적용하는 정책에 대한 자세한 내용은 [보안 기본값이란?을 참조하세요.](/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)

2019년 10월 22일 이후에 구독을 만든 경우 보안 기본값이 자동으로 사용하도록 설정되어 있을 수 &mdash; 있습니다.

Azure AD(Azure Active Directory)에서 보안 기본값을 사용하도록 설정하거나 이미 활성화되어 있는지 확인하려면

1. 보안 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">관리자Microsoft 365 관리 센터</a> 조건부 액세스 관리자 또는 전역 관리자 자격 증명으로 로그인합니다.

2. 왼쪽 창에서 모두  표시를 선택한 다음 관리 센터에서 를 **Azure Active Directory.**

3. Azure Active Directory 센터의 왼쪽 창에서 **를** **Azure Active Directory.**

4. 대시보드의 왼쪽 메뉴에 있는 관리 **섹션에서** 속성을 **선택합니다.**

    :::image type="content" source="../media/m365-campaigns-conditional-access/azure-ad-properties.png" alt-text="속성 메뉴 Azure Active Directory 위치를 보여주는 Azure Active Directory 관리 센터의 스크린샷입니다.":::

5. 속성 페이지의 맨 **아래에서** **보안 기본값 관리를 선택합니다.**

6. 오른쪽 창에 보안 기본값 사용 **설정이** 표시됩니다. **예를** 선택하면 보안 기본값이 이미 사용하도록 설정되어 있으며 추가 작업이 필요하지 않습니다. 보안 기본값을 현재 사용하도록 설정하지  않은 경우 예를 선택하여 사용하도록 설정한 다음 **저장을 선택합니다.**

> [!NOTE]
> 조건부 액세스 정책을 사용한 경우 보안 기본값을 사용하려면 먼저 정책을 해제해야 합니다.
>
> 보안 기본값 또는 조건부 액세스 정책을 사용할 수 있지만 두 정책을 동시에 사용할 수 없습니다.

## <a name="consider-using-conditional-access"></a>조건부 액세스 사용 고려

조직에 복잡한 보안 요구 사항이 있는 경우 또는 보안 정책에 대해 좀 더 세부적인 제어가 필요한 경우 보안 기본값 대신 조건부 액세스를 사용하여 유사하거나 더 높은 보안 상태를 달성하는 것이 좋습니다. 

조건부 액세스를 사용하면 사용자가 응용 프로그램 또는 서비스에 대한 액세스 권한을 부여하기 전에 로그인 이벤트에 반응하는 정책을 만들고 정의하고 추가 작업을 요청할 수 있습니다. 조건부 액세스 정책은 세분화되어 구체적일 수 있으며, 사용자가 언제 어디서나 생산성을 발휘할 수 있도록 하지만 조직을 보호할 수 있습니다.

모든 고객이 보안 기본값을 사용할 수 있습니다. 조건부 액세스에는 다음 계획 중 하나에 대한 라이선스가 필요합니다.

- Azure Active Directory Premium P1 또는 P2
- Microsoft 365 Business Premium
- Microsoft 365 E3 혹은 E5
- Enterprise 모바일 & E3 또는 E5

조건부 액세스를 사용하여 기본적으로 보안이 설정된 정책과 동등한 정책을 구성하려는 경우 다음 단계별 가이드를 참조하세요.

- [관리자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-admin-mfa)
- [Azure 관리를 위한 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-azure-management)
- [레거시 인증 차단](/azure/active-directory/conditional-access/howto-conditional-access-policy-block-legacy)
- [모든 사용자에게 MFA 요구](/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa)
- [Azure AD MFA 등록](/azure/active-directory/identity-protection/howto-identity-protection-configure-mfa-policy) 필요 - Azure AD ID 보호가 Azure Active Directory Premium P2

조건부 액세스에 대한 자세한 내용은 [조건부 액세스란?을 참조하세요.](/azure/active-directory/conditional-access/overview) 조건부 액세스 정책을 만드는 데 대한 자세한 내용은 [Create a Conditional Access policy를 참조하십시오.](/azure/active-directory/authentication/tutorial-enable-azure-mfa#create-a-conditional-access-policy)

> [!NOTE]
> 조건부 액세스를 제공하지만 아직 조건부 액세스 정책을 만들지 않은 계획이나 라이선스가 있는 경우 보안 기본값을 사용할 수 있습니다. 그러나 조건부 액세스 정책을 사용하려면 먼저 보안 기본값을 해제해야 합니다.
