---
title: 조직에서 사용자 삭제
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- SPO_Content
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 사용자 계정을 삭제하는 방법과 사용자의 전자 메일 및 전자 메일로 할 OneDrive 콘텐츠 및 제품 라이선스를 유지할지 여부에 대해 자세히 알아보겠습니다.
ms.openlocfilehash: 852ebe9a99718be9bf025fbc8347bc2ca7854cc2
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161825"
---
# <a name="delete-a-user-from-your-organization"></a>조직에서 사용자 삭제
  
**직장이나 학교에서  사용하는 Microsoft 365 계정을 삭제하는 방법을 찾고 있나요? 이 단계를 수행하기 위해 직장이나 대학의 기술 지원에 문의하세요.**

## <a name="before-you-begin"></a>시작하기 전에

- 전역 관리자 [](about-admin-roles.md) 또는 Microsoft 365 사용자 관리 권한이 있는 사용자만 사용자 계정을 삭제할 수 있습니다.
- 30일 내에 계정을 [복원](restore-user.md)하지 않으면 사용자 데이터가 영구적으로 삭제됩니다.
- 사용자의 OneDrive 데이터를 유지하려는 경우 다른 위치로 이동합니다. 계정을 삭제한 후 최대 30일까지 데이터를 이동할 수 있습니다. [이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요. 해당 SharePoint 파일을 이동할 필요는 없으며 계속 액세스할 수 있습니다.
- 사용자의 전자 메일을 유지하려는 경우 계정을 삭제하기 **전에** 전자 메일을 다른 위치로 이동합니다. 계정을 이미 삭제한 경우 아직 30일이 경과하지 않았으면 계정을 복원한 뒤 전자 메일 데이터를 이동한 다음에 계정을 삭제합니다. [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md)(이전 사용자의 데이터 액세스 및 백업)를 참조하세요.
- Enterprise E3와 같은 Office 365 Enterprise 구독이 있는 경우 삭제된 사용자 계정의 사서함 데이터를 비활성 사서함으로 전환하여 보존할 *수 있습니다.* 자세한 내용은 [Office 365에서 비활성 사서함 관리](../../compliance/inactive-mailboxes-in-office-365.md)를 참조하세요.

## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>전역 관리자: 사용자 삭제, 라이선스 비용 지불 중지, 전자 메일 및 콘텐츠로 할 OneDrive 선택

전역 관리자인 경우 사용자를 삭제할 때 다른 사용자에게 전자 메일에 대한 액세스 권한을 부여하고 해당 전자 메일 콘텐츠로 할 작업을 OneDrive 있습니다.

### <a name="things-to-consider"></a>고려할 사항

시작하기 전에 사용자의 전자 메일 및 전자 메일 콘텐츠로 OneDrive, 라이선스를 유지하거나 라이선스 비용 지불을 중지할지 여부를 생각해 보아야 합니다.
  
|항목 | 설명 |
|:-----|:-----|
|제품 라이선스  <br/> |사용자에서 라이선스를 제거하고 구독에서 라이선스를 제거하여 해당 라이선스 비용 지불을 중지할 수 있습니다. 이 옵션을 선택하면 라이선스가 구독에서 자동으로 제거됩니다.  <br/><br/> **파트너 또는 볼륨** 라이선스를 통해 라이선스를 구입한 경우 라이선스를 제거할 수 없습니다. 연간 요금제 비용을 지불하거나 청구 주기가 진행 중이면 약정이 완료될 때까지 구독에서 라이선스를 제거할 수 없습니다.  <br/> |
|OneDrive 콘텐츠  <br/> |사용자가 파일을 저장하여 파일을 OneDrive 다른 사용자에게 이러한 파일에 대한 액세스 권한을 부여할 수 있습니다.  <br/><br/> 보존 기간 내에 보관할 파일을 이동해야 합니다. 이 기간에는 해당 파일에 대해 OneDrive 합니다. **기본적으로 보존 기간은 30일입니다.** 사용자를 삭제한 후 보존 기간 내에 파일을 이동하지 않는 경우 삭제된 사용자의 OneDrive 사이트 모음이 93일 동안 보관되는 사이트 모음 재활용 보관 파일로 이동됩니다. 이 기간 동안 사용자는 더 이상 OneDrive의 공유 콘텐츠에 액세스할 수 없습니다. OneDrive를 복원하려면 PowerShell을 사용해야 합니다. 자세한 내용은 [삭제된 OneDrive 복원하기](/onedrive/restore-deleted-onedrive)를 참고하세요.<br/><br/> 삭제된 계정에 대한 OneDrive 보존하는 기간을 늘리기 위해 삭제된 사용자에 대한 OneDrive 보존 설정 [을 참조합니다.](/onedrive/set-retention)  <br/><br/> **중요!** 삭제된 사용자가 개인 컴퓨터를 사용하여 SharePoint 및 OneDrive 파일을 다운로드하는 경우 컴퓨터에 저장된 파일을 지우는 방법이 없습니다. 이러한 파일은 해당 파일에서 동기화된 모든 파일에 계속 액세스할 수 OneDrive.           |
|전자 메일  <br/> | 삭제된 사용자의 전자 메일에 다른 사용자에게 액세스 권한을 부여하면 삭제된 사용자의 사서함이 공유 사서함으로 변환됩니다. 그러면 새 사서함 소유자가 사서함에 액세스하여 새 전자 메일을 모니터링할 수 있습니다. 다음 옵션도 있습니다.  <br/>  <br/>표시 이름 변경 - 활성 사용자 목록에서 공유 사서함을 쉽게 식별할 수 있도록 표시 이름을 변경하는 **것이** 좋습니다.  <br/>  자동 회신 설정 - 이미 정중한 자동 회신을 작성했습니다. 조직 내 사용자와 조직 외부의 사용자에 대해 다른 자동 응답을 보낼 수 있습니다.  <br/> <br/> 별칭 정리 - 별칭은 사용자를 위한 추가 전자 메일 주소입니다. 일부 조직에서는 사용하지 않습니다. 따라서 사용하지 않는 조직이 없는 경우 여기에서 다른 작업을 할 필요가 없습니다. 사용자에게 별칭이 있는 경우 해당 전자 메일 주소를 다시 사용할 수 있도록 별칭을 제거하는 것이 좋습니다. 그렇지 않으면 삭제된 사서함의 보존 기간이 지나야 해당 전자 메일 주소를 다시 사용할 수 있습니다. 기본적으로 삭제된 사서함은 30일 동안 복구할 수 있습니다. 자세한 내용은 [Delete or restore user mailboxes in Exchange Online.](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox) <br/> |
|PowerShell 연결  <br/> |비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 Active Directory에서 사용자 계정을 삭제해야 합니다. Office 365를 통해서는 이렇게 할 수 없습니다. 자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))  <br/> |

### <a name="get-started"></a>시작하기

안내된 환경은 사용자를 삭제하는 단계를 안내하기 때문에 시작하는 방법에는 다음이 있습니다.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-germany"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

 1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 삭제할 사용자를 선택한 다음 사용자 삭제 **를 선택합니다.**

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>사용자 관리 관리자: 사용자 계정에서 하나 이상의 Office 365

> [!IMPORTANT]
> 공유 사서함으로 변환하거나 계정에 전자 메일 [](../email/convert-user-mailbox-to-shared-mailbox.md) 전달을 설정한 경우 사용자 계정을 삭제하지 않습니다. 이러한 함수에는 여전히 계정이 필요합니다. 공유 사서함에는 라이선스가 필요하지 않습니다. 계정을 공유 사서함으로 변환한 경우 라이선스 비용 지불을 [중지할 수 있습니다.](#stop-paying-for-the-license) 계정에 전자 메일 전달을 설정한 경우 라이선스를 제거할 수 없습니다. 이렇게 하면 전자 메일 전달이 중지된 다음 사서함이 비활성화됩니다.
  
::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..  

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 삭제할 사용자의 이름을 선택하고 세 개의 점(추가 작업)을 선택한 다음 사용자 삭제 **를 선택합니다.**

   사용자의 계정을 삭제한 경우 라이선스 비용은 계속 **지불하고 있습니다.** 라이선스 비용 지불을 중지하는 다음 절차를 참조합니다.  또는 다른 사용자에게 라이선스를 할당할 수 있습니다. 자동으로 누군가에게 할당되지 않습니다.

### <a name="stop-paying-for-the-license"></a>라이선스 비용 지불 중지

라이선스 수를 줄이는 것은 전역 관리자 또는 대금 청구 관리자만 수행할 수 있는 별도의 단계입니다.
  
::: moniker range="o365-worldwide"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a> 페이지로 이동합니다.
::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">내 상품</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">내 상품</a> 페이지로 이동합니다.
::: moniker-end

2. 제품 **탭에서** 라이선스를 제거할 구독을 선택합니다.

3. 구독 세부 정보 페이지에서 **라이선스 제거** 를 선택합니다.

4. 라이선스 **제거 창의** **새** 수량 에서  총 라이선스 상자에 이 구독에 대해 원하는 총 라이선스 수를 입력합니다. 예를 들어 라이선스가 100개인 경우 5개의 라이선스를 제거하려면 95를 입력합니다.

5. **저장** 을 선택합니다.

나중에 다른 사람을 비즈니스에 추가하는 단계를 진행할 때 한 단계만 수행하면 라이선스를 동시에 구입하라는 메시지가 표시될 것입니다.

## <a name="delete-many-users-at-the-same-time"></a>동시에 여러 사용자 삭제

[Remove-MsolUser](/powershell/module/msonline/remove-msoluser) PowerShell cmdlet을 참조합니다.

## <a name="fix-issues-with-deleting-a-user"></a>사용자 삭제와 관련된 문제 해결

다음은 사용자를 삭제하는 경우 발생하는 가장 일반적인 문제입니다.
  
- **"사용자를 삭제할 수 없습니다. 나중에 다시 시도하세요."** 계정에 전자 메일 전달이 설정되어 있는지 또는 공유 사서함으로 변환되어 있는지 다시 한 번 확인할 수 있습니다. 이 두 가지 모두 이 오류가 발생합니다. 전자 메일 전달이 있는 계정이나 공유 사서함으로 변환된 경우 계정을 삭제하지 않습니다.

- **사용자를 삭제하기 위한 적절한 권한이 없습니다**. 전역 관리자 또는 [Microsoft 365 관리자인](about-admin-roles.md) 사용자만 사용자를 삭제할 수 있습니다. 일반적으로 학교 또는 회사의 기술 지원 담당자입니다.

- 사용자를 삭제하지만 해당 이름은 전체 주소 책 **에 계속 표시됩니다.** 이 문제는 기업에서 Active Directory를 사용하는 경우 발생합니다. Active Directory에서 사용자 계정을 삭제해야 합니다. 자세한 내용은 사용자 계정 [삭제를 참조하세요.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))

**컴퓨터에서 Microsoft 365 삭제하고 싶나요? 구독 [취소로 이동하세요.](../../commerce/subscriptions/cancel-your-subscription.md)**

## <a name="related-content"></a>관련 콘텐츠

[사용자](restore-user.md) 복원(문서)\
[사서함 영구](/exchange/permanently-delete-a-mailbox-exchange-2013-help) 삭제(문서)\
[이전 직원을 제거합니다Office 365(문서)\](remove-former-employee.md)
[새 직원을 추가하여](add-new-employee.md) Office 365(문서)\
[사용자 계정 삭제:](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11))비즈니스에서 Azure AD와 동기화되는 **Active Directory를** 사용하는 경우 다음 지침을 사용하세요. Office 365를 통해서는 이렇게 할 수 없습니다. (문서)
