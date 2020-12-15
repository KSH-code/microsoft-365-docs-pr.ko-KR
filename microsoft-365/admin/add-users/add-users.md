---
title: 사용자 추가 및 라이선스 할당
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: 사용자를 추가하고 동시에 Microsoft 365에 라이선스를 할당하는 방법을 배워야 합니다.
ms.date: 07/01/2020
ms.openlocfilehash: 5df0db1cb782cc55bcf3e2b599430a98ea88750c
ms.sourcegitcommit: 8252377f63de188d32ed1ccd37540d92cba3cb65
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/14/2020
ms.locfileid: "49670998"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>사용자 추가 및 동시에 라이선스 할당

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end

팀의 각 사용자는 비즈니스용 [Microsoft 365에](https://www.microsoft.com/microsoft-365/business)로그인하고 액세스할 수 있는 사용자 계정이 필요합니다. 사용자 계정을 추가하는 가장 쉬운 방법은 Microsoft 365 관리 센터에서 한 번씩 계정을 추가하는 것입니다. 이 단계를 진행하면 사용자에게 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함이 있습니다.

## <a name="before-you-begin"></a>시작하기 전에

사용자를 추가하고 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자 되어야 합니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="watch-add-users-in-the-admin-center"></a>감시: 관리 센터에서 사용자 추가

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 비디오에 사용된 단계는 사용자를 추가하기 위한 다른 시작 지점을 보여 주지만 나머지 단계는 다음 절차와 동일합니다.

## <a name="add-users-one-at-a-time"></a>한 번씩 사용자 추가

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com> 의 관리 센터로 이동합니다.
2. 사용자 활성 **사용자로** 이동한 다음 > 사용자 **추가를 선택합니다.**
3. 기본 **설정** 창에서 기본 사용자 정보를 입력하고 다음을 **선택합니다.**
    - **이름** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인** 사용자 계정의 도메인을 선택하십시오. 예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인할 수 있는 jakob@contoso.com.
    - **암호 설정** 자동 생성 암호를 사용하거나 사용자에 대해 강력한 암호를 만들 수 있습니다.
    - 사용자는 90일 후에 암호를 변경해야 합니다. 또는 이 사용자가 처음 로그인할 때 암호를 변경하도록 **선택할 수 있습니다.**
    - 사용자가 추가될 때 암호를 전자 메일로 보낼지 여부를 선택하십시오.
4. 제품 라이선스 **할당** 창에서 사용자의 위치 및 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다. 앱을 **확장하고** 앱을 선택하거나 선택을 선택하여 사용자에게 라이선스가 있는 앱을 제한합니다. **다음** 을 선택합니다.
5. 선택적 **설정 창에서** **역할을** 확장하여 이 사용자를 관리자로 설정합니다. 프로필 **정보를 확장하여** 사용자에 대한 추가 정보를 추가합니다.
6. Select **Next,** review your new user's settings, make any changes you like, then select **Finish adding,** then **Close**.

::: moniker-end

::: moniker range="o365-germany"

1. <https://portal.office.de/adminportal> 의 관리 센터로 이동합니다.
2. 사용자 활성 **사용자로** 이동한 다음 > 사용자 **추가를 선택합니다.**
3. 새 사용자 **창에서** 다음 정보를 입력합니다. 완료되면 추가를 **선택합니다.**
    - **이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인** 예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인하려면 다음을 입력하여 jakob@contoso.com.
    - **연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.
    - **암호** 자동 생성 암호를 사용하거나 확장하여 사용자의 강력한 암호를 지정합니다. 90일 후에 암호를 변경해야 합니다. 또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.
    - **역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.
    - **제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <https://portal.partner.microsoftonline.cn> 의 관리 센터로 이동합니다.
2. 사용자 활성 **사용자로** 이동한 다음 > 사용자 **추가를 선택합니다.**
3. 새 사용자 **창에서** 다음 정보를 입력합니다. 완료되면 추가를 **선택합니다.**
    - **이름** 이름, 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인** 예를 들어 사용자의 사용자 이름이 Jakob인 경우 도메인이 contoso.com 로그인하려면 다음을 입력하여 jakob@contoso.com.
    - **연락처 정보** 확장하여 휴대폰 번호, 주소 등을 입력합니다.
    - **암호** 자동 생성 암호를 사용하거나 확장하여 사용자의 강력한 암호를 지정합니다. 90일 후에 암호를 변경해야 합니다. 또는 **사용자가 처음 로그인할 때 암호를 변경하도록 설정** 할 수도 있습니다.
    - **역할** 사용자를 관리자로 설정해야 하는 경우 확장합니다.
    - **제품 라이선스** 이 섹션을 확장하여 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>동시에 여러 사용자 추가

다음 방법 중 원하는 방법을 사용하여 동시에 여러 사용자를 추가할 수 있습니다.

- **스프레드시트를 사용하여 사용자 일괄 추가** 동시에 [여러 사용자 추가를 참조합니다.](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time)
- **계정 추가 및 라이선스 할당을 자동화합니다.** [Microsoft 365 PowerShell을](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell)사용하여 사용자 계정 만들기를 참조합니다. 이미 cmdlet을 사용하는 방법에 익숙한 경우 이 Windows PowerShell 선택하십시오.
- **ActiveDirectory를 사용하나요?** [Microsoft 365에 대한 디렉터리 동기화를 설치합니다.](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) Azure AD Connect 도구를 사용하여 Microsoft 365에서 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다. 동기화하면 사용자 계정만 추가됩니다. 동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.
- **Exchange에서 마이그레이션?** 여러 [전자 메일 계정을 Office 365로](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration)마이그레이션하는 방법을 참조하세요. 컷오버, 단계적 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Microsoft 365로 마이그레이션하는 경우 마이그레이션의 일부로 사용자를 자동으로 추가합니다. 마이그레이션하면 사용자 계정만 추가됩니다. 전자 메일 및 기타 Office 앱을 사용하려면 먼저 사용자에게 라이선스를 할당해야 합니다. 사용자에게 라이선스를 할당하지 않은 경우 30일의 유예 기간이 지난 후 해당 사서함을 사용할 수 없습니다. Microsoft 365 관리 센터에서 사용자에게 라이선스를 할당하는 방법을 학습합니다. [](../manage/assign-licenses-to-users.md)

## <a name="next-steps"></a>다음 단계

사용자를 추가하고 나면 Microsoft에서 전자 메일 알림을 받을 수 있습니다. 전자 메일에는 Microsoft 365에 로그인할 수 있도록 사용자의 사용자 ID와 암호가 포함되어 있습니다. 새 암호를 전달하는 데 일반 프로세스를 사용합니다. 직원 [빠른](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) 시작 가이드를 새 사용자와 공유하여 PC 또는 [Mac에 Office](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) 앱을 다운로드하고 설치하는 방법 및 모바일 장치에서 Office 앱 및 전자 메일을 설정하는 방법과 같은 것을 [설정할 수 있습니다.](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365에](add-new-employee.md) 새 직원 추가(문서)\
[Microsoft 365에](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) 동시에 여러 사용자 추가(문서)\
[Microsoft 365에서](restore-user.md) 사용자 복원(문서)\
[사용자에게 라이선스 할당(문서)\](../manage/assign-licenses-to-users.md)
[조직에서 사용자](delete-a-user.md) 삭제(문서)
