---
title: 사용자 추가 및 라이선스 할당
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
ms.custom:
- okr_smb
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
description: 각 팀 구성원에게는 비즈니스용 Microsoft 365에 로그인하고 액세스할 수 있는 사용자 계정이 필요합니다. 사용자를 추가하고 라이선스를 할당하는 방법을 알아보세요.
ms.date: 07/01/2020
ms.openlocfilehash: b7fa0842812a83e510d7e200ebef3db4507d4b9d
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 09/12/2021
ms.locfileid: "59185331"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>사용자 추가 및 동시에 라이선스 할당

팀의 각 구성원은 먼저 사용자 계정이 있어야 [Microsoft 365 비즈니스](https://www.microsoft.com/microsoft-365/business) 에디션에 로그인하고 액세스할 수 있습니다. 사용자 계정을 추가하는 가장 쉬운 방법은 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 관리 센터</a>에서 한 번에 한 명씩 사용자를 추가하는 것입니다. 이 단계를 수행하면 팀 구성원은 Microsoft 365 라이선스, 로그인 자격 증명 및 Microsoft 365 사서함을 갖게 됩니다.

## <a name="before-you-begin"></a>시작하기 전에

사용자를 추가하고 라이선스를 할당하려면 전역, 라이선스 또는 사용자 관리자여야 합니다. 자세한 내용은 [관리자 역할 정보](../../admin/add-users/about-admin-roles.md)를 참조하세요.

## <a name="add-a-user-in-the-admin-simplified-view"></a>관리자 간소화된 보기에 사용자 추가

관리 센터에 이 페이지가 표시되는 경우, **관리자 간소화된 보기** 에 있는 것입니다. 아래 단계에 따라 사용자를 추가합니다.

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="스크린샷: 간소화된 관리 센터 보기":::

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.

::: moniker-end 

2. **다른 사용자를 위한 계정 만들기** 를 선택합니다.
3. **사용자 계정 추가** 페이지에서 로그인하는 데 사용할 성과 이름, 표시 이름, 사용자 이름을 입력합니다.
4. **최대 5개 전자 메일 주소** 텍스트 상자에 사용자의 전자 메일 주소를 추가합니다. 이렇게 하면 새 사용자가 Microsoft 365 서비스에 로그인하는 데 필요한 정보를 얻게 됩니다.
5. 이 정보를 저장하려면 **사용자 추가** 및 **로그인 정보 다운로드** 를 선택합니다.

## <a name="watch-add-users-in-the-dashboard-view"></a>보기: 대시보드 보기에서 사용자 추가

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> 비디오에 사용된 단계는 사용자를 추가하기 위한 다른 시작점을 보여주지만, 나머지 단계는 다음 절차와 동일합니다.

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>대시보드 보기에서 한 번씩 사용자 추가

:::image type="content" source="../../media/classic-admin-center.png" alt-text="스크린샷: 관리 센터 대시보드 보기":::

::: moniker range="o365-worldwide"

1. <https://admin.microsoft.com>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-germany"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>의 관리 센터로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>의 관리 센터로 이동합니다.

::: moniker-end 

2. **사용자**  >  **활성 사용자** 로 이동한 후, **사용자 추가** 를 선택합니다.
3. **기본 설정** 창에서 사용자 정보를 입력하고 **다음** 을 택합니다.
    - **이름** 이름과 성, 표시 이름 및 사용자 이름을 입력합니다.
    - **도메인** 사용자 계정의 도메인을 선택합니다. 예를 들어 사용자의 사용자 이름이 Jakob이고 도메인이 contoso.com인 경우 jakob@contoso.com을 사용하여 로그인합니다.
    - **암호 설정** 자동으로 생성되는 암호를 사용하거나 사용자에 대해 강력한 암호를 만들지 여부를 선택합니다.
    - 사용자는 90일 후에 암호를 변경해야 합니다. 또는 **사용자가 처음 로그인할 때 암호를 변경하도록 요구** 할 수도 있습니다.
    - 사용자가 추가될 때 암호를 전자 메일로 보낼지 여부를 선택하세요.
4. **제품 라이선스 할당** 창에서 사용자의 위치와 적절한 라이선스를 선택합니다. 사용 가능한 라이선스가 없어도 사용자를 추가하고 추가 라이선스를 구입할 수 있습니다. **앱** 을 확장하고 앱을 선택하거나 선택을 선택 해제 사용자에게 라이선스가 있는 앱을 제한합니다. **다음** 을 선택합니다.
5. **선택적 설정** 창에서 **역할** 을 확장하여 이 사용자를 관리자로 만듭니다. **프로필 정보** 를 확장하여 사용자에 대한 추가 정보를 추가합니다.
6. **다음** 을 선택하고 새 사용자의 설정을 검토하고 원하는 대로 변경한 다음 **추가 완료**, **닫기** 를 차례로 선택합니다.

## <a name="add-multiple-users-at-the-same-time"></a>동시에 여러 사용자 추가

다음 방법 중 원하는 방법을 사용하여 동시에 여러 사용자를 추가할 수 있습니다.

- **스프레드시트를 사용하여 사용자를 일괄 추가합니다.** [동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)를 참조하세요.
- **계정을 추가하고 라이선스를 할당하는 작업을 자동화합니다.** [Microsoft 365 PowerShell을 사용하여 사용자 계정 만들기](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md)를 참조하세요. Windows PowerShell cmdlet 사용에 익숙한 경우 이 방법을 선택하세요.
- **ActiveDirectory를 사용하나요?** [Microsoft 365의 디렉터리 동기화 설정](../../enterprise/set-up-directory-synchronization.md) Microsoft 365에서 Azure AD Connect 도구를 사용하여 Active Directory 사용자 계정 및 기타 Active Directory 개체를 복제합니다. 동기화를 수행하면 사용자 계정만 추가됩니다. 동기화된 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다.
- **Exchange에서 마이그레이션하나요?** [Office 365로 여러 전자 메일 계정을 마이그레이션하는 방법](/Exchange/mailbox-migration/mailbox-migration)을 참조하세요. 단독형, 미리 구성된 또는 하이브리드 Exchange 방법을 사용하여 여러 사서함을 Microsoft 365로 마이그레이션하는 경우 마이그레이션의 일환으로 사용자가 자동으로 추가됩니다. 마이그레이션하면 사용자 계정만 추가됩니다. 사용자에게 라이선스를 할당해야 전자 메일 및 기타 Office 앱을 사용할 수 있습니다. 사용자에게 라이선스를 할당하지 않은 경우 30일의 유예 기간 후에 해당 사서함이 비활성화됩니다. Microsoft 365 관리 센터에서 [사용자에게 라이선스를 할당](../manage/assign-licenses-to-users.md)하는 방법을 배워보세요.

## <a name="next-steps"></a>다음 단계

사용자를 추가한 후 Microsoft에서 전자 메일 알림을 수신합니다. 전자 메일에는 사용자가 Microsoft 365에 로그인할 수 있도록 해당 사용자의 사용자 ID와 암호가 포함됩니다. 새 암호를 알려 주기 위한 일반 프로세스를 사용합니다. [직원 빠른 시작 가이드](../../business-video/employee-quick-setup.md)를 새 사용자와 공유하여 [PC 또는 Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)에서 Office 앱을 다운로드하고 설치하는 방법, [모바일 장치에서 Office 앱 및 전자 메일을 설정](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f)하는 방법 등을 설정하세요.

## <a name="related-content"></a>관련 콘텐츠

[Microsoft 365에 새 직원 추가](add-new-employee.md)(문서)\
[Microsoft 365 앱에 동시에 여러 사용자 추가](../../enterprise/add-several-users-at-the-same-time.md)(문서)\
[Microsoft 365의 사용자 복원](restore-user.md)(문서)\
[사용자에게 라이선스 할당](../manage/assign-licenses-to-users.md)(문서)\
[조직에서 사용자 삭제](delete-a-user.md)(문서)\
