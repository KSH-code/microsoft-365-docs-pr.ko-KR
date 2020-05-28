---
title: 조직에서 사용자 삭제
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: d5155593-3bac-4d8d-9d8b-f4513a81479e
description: 사용자 계정을 삭제 하는 방법에 대해 알아봅니다. 사용자의 전자 메일, OneDrive 콘텐츠, 제품 라이선스를 유지할지 아니면 지불할 지를 결정 합니다.
ms.openlocfilehash: 4102fe4ac297a1f426b3bf575e748a72b323ebb6
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387192"
---
# <a name="delete-a-user-from-your-organization"></a>조직에서 사용자 삭제
  
||
|:-----|
|**회사 또는 학교에서 사용 하는 Microsoft 365 사용자 계정을 *직접* 삭제 하는 방법을 찾으십니까? 회사 또는 대학에서 기술 지원 서비스에 문의 하 여 다음 단계를 수행 하세요.**|
   
## <a name="what-you-need-to-know-about-deleting-users"></a>사용자 삭제에 대해 알아야 할 사항

- 비즈니스 또는 학교에 대 한 [Microsoft 365 전역 관리자](about-admin-roles.md) 또는 사용자 관리 권한이 있는 사용자만 사용자 계정을 삭제할 수 있습니다. 
    
- 30일 내에 계정을 [복원](restore-user.md)하지 않으면 사용자 데이터가 영구적으로 삭제됩니다. 
    
- 사용자의 OneDrive 데이터를 유지하려는 경우 다른 위치로 이동합니다. 계정을 삭제한 후 최대 30일까지 이 작업을 수행할 수 있습니다. [이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요. 해당 SharePoint 파일을 이동할 필요는 없으며 계속 액세스할 수 있습니다.
    
- 사용자의 전자 메일을 유지하려는 경우 계정을 삭제하기 **전에** 전자 메일을 다른 위치로 이동합니다. 계정을 이미 삭제한 경우 아직 30일이 경과하지 않았으면 계정을 복원한 뒤 전자 메일 데이터를 이동한 다음에 계정을 삭제합니다. [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md)(이전 사용자의 데이터 액세스 및 백업)를 참조하세요.
    
- Office 365 Enterprise e 3과 같은 엔터프라이즈 구독을 사용 하는 경우 삭제 된 사용자 계정의 사서함 데이터를 *비활성 사서함*으로 설정 하 여 보존할 수 있습니다. 자세한 내용은 [Office 365에서 비활성 사서함 관리](https://docs.microsoft.com/microsoft-365/compliance/inactive-mailboxes-in-office-365)를 참조하세요.


## <a name="global-admin-delete-a-user-stop-paying-for-their-license-and-choose-what-to-do-with-their-email-and-onedrive-content"></a>전역 관리자: 사용자 삭제, 해당 라이선스에 대 한 지불 중지 및 전자 메일 및 OneDrive 콘텐츠로 수행할 작업 선택

전역 관리자 인 경우 사용자를 삭제 하는 경우 다른 사용자에 게 전자 메일에 대 한 액세스 권한을 부여 하 고 OneDrive 콘텐츠로 수행할 작업을 선택할 수도 있습니다. 

  
### <a name="things-to-consider"></a>고려할 사항...

시작 하기 전에 사용자의 전자 메일 및 OneDrive 콘텐츠를 사용 하 여 수행할 작업과 라이선스를 유지할지, 아니면 비용을 지불할 지를 고려해 야 합니다.
  
|||
|:-----|:-----|
|제품 라이선스  <br/> |사용자 로부터 라이선스를 제거 하 고 해당 라이선스에 대 한 비용 지불을 중지할 수 있습니다. 이 옵션을 선택 하면 구독이 구독에서 자동으로 제거 됩니다.  <br/><br/> 파트너 또는 볼륨 라이선스를 통해 **라이선스를 구입한 경우에는 제거할 수 없습니다** . 연간 요금제에 대 한 비용을 지불 하거나 대금 청구 주기의 중간에 있는 경우에는 약정을 완료할 때까지 구독에서 라이선스를 제거할 수 없습니다.  <br/> |
|OneDrive 콘텐츠  <br/> |사용자가 파일을 OneDrive에 저장 한 경우에는 다른 사용자에 게 이러한 파일에 대 한 액세스 권한을 부여할 수 있습니다.  <br/><br/> 보관 하려는 파일을 OneDrive 파일에 대해 설정 된 보존 기간 내에 이동 해야 합니다. **기본적으로 보존 기간은 30 일입니다.** 사용자를 삭제 한 후 보존 기간 내에 파일을 이동 하지 않으면 OneDrive 콘텐츠가 영구적으로 삭제 됩니다. 삭제 된 계정에 대해 OneDrive 파일을 보존 하는 기간 (일)을 높이려면 [삭제 한 사용자에 대 한 onedrive 보존 설정을](https://docs.microsoft.com/onedrive/set-retention)참조 하세요.  <br/><br/> **중요 한!** 삭제 된 사용자가 개인 컴퓨터를 사용 하 여 SharePoint 및 OneDrive에서 파일을 다운로드 한 경우에는 컴퓨터에 저장 된 파일을 지울 방법이 없습니다. OneDrive에서 동기화 된 모든 파일에 계속 액세스할 수 있습니다.           |
|전자 메일  <br/> | 삭제 된 사용자의 전자 메일에 대해 다른 사용자에 게 액세스 권한을 부여 하면 삭제 된 사용자의 사서함이 공유 사서함으로 변환 됩니다. 그런 다음 새 사서함 소유자가 사서함에 액세스 하 고 새 전자 메일을 모니터링할 수 있습니다. 또한 다음 옵션을 사용할 수 있습니다.  <br/>  <br/>표시 이름 변경-활성 사용자 목록에서 공유 사서함을 쉽게 식별할 수 있도록 표시 이름을 변경 하는 것이 좋습니다.  <br/>  자동 회신 설정-이미 예의 지키고 자동 회신을 작성 했습니다. 조직과 외부의 사용자에 게 서로 다른 자동 회신을 보낼 수 있습니다.  <br/> <br/> 별칭 정리-사용자의 추가 전자 메일 주소입니다. 일부 조직에서는이를 사용 하지 않으므로 여기에서 다른 작업을 수행 하지 않아도 되는 경우가 있습니다. 사용자에 게 별칭이 있는 경우 해당 전자 메일 주소를 다시 사용할 수 있도록이를 제거 하는 것이 좋습니다. 그렇지 않으면 삭제 된 사서함의 보존 기간이 지날 때까지 해당 전자 메일 주소를 다시 사용할 수 없습니다. 기본적으로 삭제 된 사서함은 30 일간 복구 됩니다. 자세한 내용은 [Exchange Online에서 사용자 사서함 삭제 또는 복원을](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes#delete-a-user-mailbox)참조 하세요. <br/> |
|Active Directory  <br/> |회사에서 Azure AD와 동기화 되는 **Active directory** 를 사용 하는 경우 active directory에서 사용자 계정을 삭제 해야 합니다. Office 365를 통해서는 이렇게 할 수 없습니다. 자세한 내용은 [사용자 계정 삭제](https://go.microsoft.com/fwlink/p/?linkid=841808)를 참조 하십시오.  <br/> |
   
### <a name="get-started"></a>시작하기

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

::: moniker-end

안내가 제공 되는 환경에서는 사용자를 삭제 하는 단계를 안내 하므로 시작 하려면 다음을 수행 하세요.

::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

::: moniker-end

2. 삭제 하려는 사용자를 선택 하 고 **사용자 삭제**를 선택 합니다.

## <a name="user-management-admin-delete-one-or-more-users-from-office-365"></a>사용자 관리 관리자: Office 365에서 하나 이상의 사용자를 삭제 합니다.


> [!IMPORTANT]
> 사용자 계정이 [공유 사서함으로 변환](../email/convert-user-mailbox-to-shared-mailbox.md) 되었거나 계정에 전자 메일 전달을 설정한 경우에는 해당 계정을 삭제 하지 마세요. 이러한 기능은 여전히 계정이 필요 합니다. 공유 사서함에는 라이선스가 필요 하지 않습니다. 계정을 공유 사서함으로 변환한 경우 [에는 라이선스에 대 한 비용 지불을 중지할](#stop-paying-for-the-license)수 있습니다. 계정에 전자 메일 전달을 설정한 경우에는 라이선스를 제거할 수 없습니다. 이렇게 하면 전자 메일 전달이 중지 되 고 사서함이 비활성화 됩니다.
  
::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..  

2. 삭제할 사용자의 이름을 선택 하 고 **기타 옵션** (**...**)을 선택한 다음 **사용자 삭제**를 선택 합니다.

   사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다. 라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.  또는 다른 사용자에 게 라이선스를 할당할 수 있습니다. 자동으로 사용자에 게 할당 되지 않습니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 삭제 하려는 사용자의 이름을 선택 하 고 **대량 작업** 창에서 **사용자 삭제**를 선택 합니다.

   사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다. 라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.  또는 다른 사용자에 게 라이선스를 할당할 수 있습니다. 자동으로 사용자에 게 할당 되지 않습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 삭제 하려는 사용자의 이름을 선택 하 고 **대량 작업** 창에서 **사용자 삭제**를 선택 합니다.

   사용자 계정을 삭제 했지만 **여전히 라이선스에 대 한**비용을 지불 하 고 있습니다. 라이선스에 대 한 비용 지불을 중지 하려면 다음 절차를 참조 하세요.  또는 다른 사용자에 게 라이선스를 할당할 수 있습니다. 자동으로 사용자에 게 할당 되지 않습니다.

::: moniker-end

### <a name="stop-paying-for-the-license"></a>라이선스 비용 지불 중지

라이선스 수를 줄이는 것은 전역 관리자 또는 대금 청구 관리자만 수행할 수 있는 별도의 단계입니다. 
  
::: moniker range="o365-worldwide"

1. 관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요. 이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.

2. 구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.  

   나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다. 이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.

2. 구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.  

   나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다. 이 옵션이 표시 되지 않으면 전역 관리자 또는 대금 청구 관리자가 아니므로이 단계를 수행할 수 없습니다.

2. 구독을 하나 이상 선택한 다음 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이선스에 대해 비용을 지불 하지 않을 수 있습니다.  

   나중에 비즈니스에 다른 사람을 추가 하는 단계를 진행할 때 동시에 라이선스를 구입 하 라는 메시지가 표시 되며,이는 한 단계만 진행 됩니다.

::: moniker-end 

## <a name="delete-many-users-at-the-same-time"></a>여러 사용자를 동시에 삭제

[Get-msoluser](https://go.microsoft.com/fwlink/p/?linkid=842230) PowerShell cmdlet을 참조 하세요.

## <a name="fix-issues-with-deleting-a-user"></a>사용자 삭제와 관련된 문제 해결

사용자를 삭제할 때 발생할 수 있는 가장 일반적인 문제는 다음과 같습니다.
  
- **"사용자를 삭제할 수 없습니다. 라는 줄에 오류 메시지가 표시 됩니다. 나중에 다시 시도 하세요. "** 계정에 전자 메일 전달이 설정 되어 있는지, 아니면 공유 사서함으로 변환 붙여넣으세요. 두 경우 모두 해당 오류가 발생 합니다. 전자 메일 전달이 있거나 공유 사서함으로 변환 된 경우에는 계정을 삭제 하지 마세요.

- **사용자를 삭제하기 위한 적절한 권한이 없습니다**. [Microsoft 365 전역 관리자 또는 사용자 관리 관리자](about-admin-roles.md) 만 사용자를 삭제할 수 있습니다. 일반적으로 학교 또는 회사의 기술 지원 담당자입니다.

- **사용자를 삭제했지만 해당 이름이 전체 주소록에 계속 나타납니다**. 회사에서 Active Directory를 사용하는 경우 이 문제가 발생합니다. Active Directory에서 사용자 계정을 삭제해야 합니다. 지침은 다음 TechNet 문서를 참조하세요. [사용자 계정 삭제.](https://go.microsoft.com/fwlink/p/?linkid=841808)

||
|:-----|
|**컴퓨터에서 Microsoft 365을 (를) 삭제 하 시겠습니까? [구독 취소](../../commerce/subscriptions/cancel-your-subscription.md)로 이동 합니다.**|
   
## <a name="related-articles"></a>관련 문서

[사용자 복원](restore-user.md)
  
[사서함을 영구적으로 삭제](https://technet.microsoft.com/library/jj863440%28v=exchg.150%29.aspx)

[Office 365에서 이전 직원 제거](remove-former-employee.md)

[Office 365에 새 직원 추가](add-new-employee.md)

[사용자 계정 삭제](https://go.microsoft.com/fwlink/p/?linkid=841808): 회사에서 Azure AD와 동기화 되는 **Active Directory** 를 사용 하는 경우 이러한 지침을 사용 합니다. Office 365를 통해서는 이렇게 할 수 없습니다.