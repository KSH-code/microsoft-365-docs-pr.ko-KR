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
description: MFA를 요구하고 Microsoft 365 비즈니스 에디션에 대한 조건부 액세스 정책을 설정하는 방법을 배워야 합니다.
ms.openlocfilehash: b13ba9f8c948d9a1209655c44871ca62cb5354dd
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044503"
---
# <a name="require-multi-factor-authentication-and-set-up-conditional-access-policies"></a>다단계 인증 필요 및 조건부 액세스 정책 설정

다단계 인증 및 조건부 액세스 정책을 사용하여 데이터에 대한 액세스를 보호할 수 있습니다. 이러한 보안은 상당한 추가 보안을 추가합니다. Microsoft는 모든 고객에게 권장되는 기준 조건부 액세스 정책 집합을 제공합니다. 기준 정책은 여러 가지 일반적인 공격으로부터 조직을 보호하는 데 도움이 되는 미리 정의된 정책 집합입니다. 이러한 일반적인 공격에는 암호 분사, 재생 및 피싱이 포함됩니다.

이러한 정책을 사용하려면 관리자와 사용자가 특정 조건에서 두 번째 인증 형식(다단계 인증 또는 MFA)을 입력해야 합니다. 예를 들어 조직의 사용자가 다른 국가 또는 알 수 없는 장치에서 Microsoft 365에 로그인을 하도록 하는 경우 로그인은 위험한 것으로 간주될 수 있습니다. 사용자는 추가 인증 형식(예: 지문 또는 코드)을 제공해야 ID를 증명할 수 있습니다.

현재 기준 정책에는 다음 정책이 포함됩니다.

- Microsoft 365 관리 센터에서 설정:
  - **관리자를 위한 MFA** 필요: 전역 관리자를 포함하여 가장 권한이 부여된 관리자 역할에 대해 다단계 인증이 필요합니다.
  - **최종 사용자 보호:** 로그인이 위험할 때만 사용자에 대해 다단계 인증이 필요합니다. 
- Azure Active Directory 포털에서 설정:
  - **레거시 인증** 차단: 이전 클라이언트 앱과 일부 새 앱은 더 안전한 새 인증 프로토콜을 사용하지 않습니다. 이러한 이전 앱은 조건부 액세스 정책을 무시하고 환경에 무단으로 액세스할 수 있습니다. 이 정책은 조건부 액세스를 지원하지 않는 클라이언트의 액세스를 차단합니다. 
  - **서비스 관리를 위한 MFA** 필요: Azure Portal(기준 정책을 구성하는 위치)을 비롯한 관리 도구에 액세스하려면 다단계 인증이 필요합니다.

이러한 모든 기준 정책을 사용하도록 설정하는 것이 좋습니다. 이러한 정책을 사용하도록 설정하면 관리자와 사용자에게 Azure AD 다단계 인증을 등록하라는 메시지가 표시됩니다.

이러한 정책에 대한 자세한 내용은 기준 [정책이란?](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-baseline-protection)

## <a name="require-mfa"></a>MFA 필요

모든 사용자가 두 번째 형식의 ID로 로그인해야 하는 경우:

1. 관리 센터로 이동하여 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 설치를 **선택하세요.**

2. 설치 페이지에서 **로그인하기** 더 안전한 카드로 **보기를** 선택합니다.

    ![로그인을 보다 안전한 카드로 만들어야 합니다.](../media/setupmfa.png)
3. 로그인을 더욱 안전하게 만들기 페이지에서 **시작을 선택합니다.**

4. 로그인 보안 강화 창에서 관리자에 대해 다단계  인증 필요 및 사용자가 다단계 인증을 등록하도록 요구하는 확인란을 선택하고 위험이 감지되면 액세스를 차단합니다. 
    사용자 찾기 상자의 MFA 요구 사항에서 긴급 또는 "중단 유리" 관리자 계정을 **제외해야** 합니다. [](m365-campaigns-protect-admin-accounts.md#create-an-emergency-admin-account)

    ![sing-in 보안 페이지를 강화합니다.](../media/requiremfa.png)

5. 페이지 **아래쪽에** 정책 만들기를 선택합니다.

## <a name="set-up-baseline-policies"></a>기준 정책 설정

1. [Azure Portal로 이동한](https://portal.azure.com)다음 **Azure Active Directory** 조건부 액세스로 이동하여 새 정책을 \>  **만드십시오.**

각 정책에 대한 다음 특정 지침을 참조하세요. <br>
    - [관리자를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-administrators) <br>
    - [사용자에 대해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-end-users) <br>
    - [레거시 인증 차단](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-legacy-auth) <br>
    - [서비스 관리를 위해 MFA 필요](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-baseline-protect-azure)

> [!NOTE]
> 미리 보기 정책이 더 이상 존재하지 않습니다. 사용자는 자신의 정책을 만들어야 합니다.

승인된 클라이언트 앱을 요구하는 등의 추가 정책을 설정할 수 있습니다. 자세한 내용은 [조건부 액세스 설명서를 참조하십시오.](https://docs.microsoft.com/azure/active-directory/conditional-access/)
