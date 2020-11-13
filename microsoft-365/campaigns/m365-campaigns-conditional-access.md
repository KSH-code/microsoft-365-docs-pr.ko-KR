---
title: 조건부 액세스 정책을 설정합니다.
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
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
description: MFA를 요구 하는 방법과 비즈니스용 Microsoft 365에 대 한 조건부 액세스 정책을 설정 하는 방법을 알아봅니다.
ms.openlocfilehash: 5908a36f09753cd8f66169c6a67be45c748807b7
ms.sourcegitcommit: 34ebec8e2bd54ba3d4ccfd9724797665c965c17f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071504"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>다단계 인증 필요 및 조건부 액세스 정책 설정

다단계 인증 및 조건부 액세스 정책을 사용 하 여 데이터에 대 한 액세스를 보호 합니다. 이러한 추가 보안은 매우 중요 합니다. Microsoft는 모든 고객에 게 권장 되는 기본 조건부 액세스 정책 집합을 제공 합니다. 기본 정책은 일반적인 여러 공격 으로부터 조직을 보호 하는 데 도움이 되는 미리 정의 된 정책의 집합입니다. 이러한 일반적인 공격에는 암호 스프레이, replay 및 피싱이 포함 될 수 있습니다.

이러한 정책을 사용 하려면 관리자 및 사용자가 특정 조건에 맞을 때 두 번째 인증 형태 (다단계 인증) 또는 MFA를 입력 해야 합니다. 예를 들어 조직의 사용자가 다른 국가나 알 수 없는 장치에서 Microsoft 365에 로그인 하려고 하면 로그인이 위험한 것으로 간주 될 수 있습니다. 사용자는 id를 증명 하기 위해 추가 인증 형식 (예: 지문 또는 코드)을 제공 해야 합니다. 

현재 기본 정책에는 다음이 포함 됩니다.
- Microsoft 365 관리 센터에서 설정:
    - 관리자 **에 대해 MFA 필요** -전역 관리자를 비롯 하 여 권한이 가장 높은 관리자 역할에 대해 multi-factor authentication이 필요 합니다.
    - **최종 사용자 보호** -로그인이 위험한 경우에만 사용자에 대해 multi-factor authentication을 사용 해야 합니다. 
- Azure Active Directory 포털에서 설정:
    - **레거시 인증 차단** -오래 된 클라이언트 앱과 일부 새 앱은 더 최신의 비보안 인증 프로토콜을 사용 하지 않습니다. 이러한 이전 앱은 조건부 액세스 정책을 우회 하 여 환경에 대 한 무단 액세스를 얻을 수 있습니다. 이 정책은 조건부 액세스를 지원 하지 않는 클라이언트의 액세스를 차단 합니다. 
    - **서비스 관리를 위해 MFA 필요** -Azure portal을 포함 하 여 관리 도구에 액세스 하기 위한 다단계 인증 필요 (기준 정책 구성). 

이러한 모든 기본 정책을 사용 하도록 설정 하는 것이 좋습니다. 이러한 정책을 사용 하도록 설정한 후에는 관리자 및 사용자에 게 Azure Multi-factor authentication을 등록 하 라는 메시지가 표시 됩니다.

이러한 정책에 대 한 자세한 내용은 [기본 정책 이란](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)?를 참조 하십시오.


## <a name="require-mfa"></a>MFA 필요

모든 사용자에 게 다른 ID 형태의 로그인을 요구 하려면 다음을 수행 합니다.

1. 관리 센터로 이동 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 하 여 **설치** 를 선택 합니다.

2. 설정 페이지의 **고급 보안 설정** 카드에서 **보기** 를 선택 합니다.


    ![더 안전 하 게 로그인 카드를 만듭니다.](../media/setupmfa.png)
3. 더 안전 하 게 로그인 하기 페이지에서 **시작** 을 선택 합니다.
 
4. 로그인 보안 강화 창에서 **관리자에 대 한 다단계 인증 필요** 옆의 확인란을 선택 하 고, **위험이 감지 되 면 사용자에 게 다단계 인증을 등록 하 고 액세스를 차단 하도록 요구** 합니다.
    **사용자 찾기** 상자에서 MFA 요구 사항 으로부터 [응급](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account) 또는 "투명 효과" 관리자 계정을 제외 해야 합니다.
    
    ![공동으로 보안 페이지를 강화 합니다.](../media/requiremfa.png)

5. 페이지 아래쪽에서 **정책 만들기** 를 선택 합니다.

## <a name="set-up-baseline-policies"></a>기본 정책 설정

1. [Azure 포털로](https://portal.azure.com)이동한 다음 **azure Active Directory** \> **조건부 액세스** 로 이동 하 여 **새 정책을** 만듭니다.

각 정책에 대해 다음과 같은 구체적인 지침을 참조 하세요. <br>
    - [관리자를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [사용자에 대해 MFA 요구](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [서비스 관리를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)
    
> [!NOTE]
> 미리 보기 정책은 더 이상 존재 하지 않으므로 사용자가 고유한 정책을 만들어야 합니다.


승인 된 클라이언트 앱을 요구 하는 등 추가 정책을 설정할 수 있습니다. 자세한 내용은 [조건부 액세스 설명서](https://docs.microsoft.com/azure/active-directory/conditional-access/)를 참조 하세요.
