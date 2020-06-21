---
title: 사용자의 다른 전자 메일 별칭 추가
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- okr_smb
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 0b0bd900-68b1-4bf5-808b-5d240a7739f4
description: 'Microsoft 365 for business 계정에 연결 된 전자 메일 주소를 두 개 이상 사용할 수 있는 방법을 알아봅니다. '
ms.openlocfilehash: c0e71ef150ccf592ea4f808a5e6609e1675767a4
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780292"
---
# <a name="add-another-email-alias-for-a-user"></a>사용자의 다른 전자 메일 별칭 추가

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end
  
이 문서는 비즈니스 구독을 보유 하 고 있는 Microsoft 365 관리자를 위한 것입니다. 가정용 사용자용이 아닙니다.
  
Microsoft 365의 기본 전자 메일 주소는 일반적으로 계정을 만들 때 사용자에 게 할당 된 전자 메일 주소입니다. 사용자가 다른 사람에게 전자 메일을 보내면 전자 메일 앱의  *보낸 사람*  필드에 일반적으로 사용자의 기본 전자 메일 주소가 표시됩니다. 또한 Microsoft 365 for business 계정에 연결 된 전자 메일 주소가 두 개 이상 있을 수도 있습니다. 이러한 추가 주소를 별칭이라고 합니다. 
  
예를 들어 Jenna에 전자 메일 주소가 jenna@contosoco.com 있다고 가정 하지만 일부 사용자가 해당 이름으로 그녀를 참조 하기 때문에 jen@contosoco.com에서 전자 메일도 수신 하려고 합니다. 두 전자 메일 주소가 모두 Jenna의 받은 편지 함으로 이동 하도록 별칭을 만들 수 있습니다.
<br><br>  
  
사용자는 최대 400의 별칭을 만들 수 있습니다. 추가 요금이나 라이선스는 필요하지 않습니다.
  
> [!Tip]
> 여러 사용자가 info@NodPublishers.com 또는 sales@NodPublishers.com와 같은 단일 전자 메일 주소로 보내는 전자 메일을 관리 하도록 하려면 공유 사서함을 만듭니다. 자세한 내용은 [공유 사서함 만들기](create-a-shared-mailbox.md)를 참조 하십시오.
  
## <a name="add-email-aliases-to-a-user"></a>사용자에게 전자 메일 별칭 추가
<a name="AddEmailPreview"> </a>

이 작업을 수행 하려면 [관리자 권한이](../add-users/about-admin-roles.md) 있어야 합니다. 

  
::: moniker range="o365-worldwide"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. **활성 사용자** 페이지에서 **전자 메일 별칭 관리**> 사용자를 선택 합니다. 사용자에 게 라이선스가 할당 되어 있지 않은 경우에는이 옵션이 표시 되지 않습니다. 
    
3. **+ 별칭 추가** 를 선택 하 고 사용자의 새 별칭을 입력 합니다.   
    
    > [!Important] 
    > "**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
    
  
    > [!IMPORTANT]
    > GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다. 
  
    > [!TIP]
    > 전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다. 목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오. 
  
     
5. 작업을 마치면 **변경 내용 저장**을 선택 합니다.
    
6. Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다.
    
    이제 사용자에 게 기본 주소와 별칭이 표시 됩니다. 예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.
    
  
7. **사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.** 예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다. 지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다. 
    
::: moniker-end

::: moniker range="o365-germany"
    
1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다. 
    
    
2. **활성 사용자** 페이지에서 편집할 사용자 이름을 선택합니다.

3. **사용자 이름/전자 메일 별칭**옆에 있는 **편집**을 선택 합니다.

    > [!Important] 
    > "**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.

4. **별칭**아래의 텍스트 상자에 새 전자 메일 별칭의 첫 부분을 입력 합니다. Office 365에 고유 도메인을 추가한 경우 드롭다운 목록을 사용하여 새 전자 메일의 도메인을 선택할 수 있습니다. 그런 다음 **추가**를 선택합니다.

    > [!IMPORTANT]
    > GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다. 
  
    > [!TIP]
    > 전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다. 목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오. 

5. 작업을 마치면 **Save (저장**)를 선택 합니다.

6. Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다. 
    
    이제 사용자에 게 기본 주소와 별칭이 표시 됩니다. 예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.
    
  
7. **사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.** 예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다. 지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다. 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다. 

    
2. **활성 사용자** 페이지에서 편집할 사용자 이름을 선택합니다.

3. **사용자 이름/전자 메일 별칭**옆에 있는 **편집**을 선택 합니다.

    > [!Important] 
    > "**매개 변수 이름 ' EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정을 완료 하는 데 약간 시간이 걸리고, 최근에 추가한 경우 사용자 지정 도메인을 사용 하는 것입니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.

4. **별칭**아래의 텍스트 상자에 새 전자 메일 별칭의 첫 부분을 입력 합니다. Office 365에 고유 도메인을 추가한 경우 드롭다운 목록을 사용하여 새 전자 메일의 도메인을 선택할 수 있습니다. 그런 다음 **추가**를 선택합니다.

    > [!IMPORTANT]
    > GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다. 
  
    > [!TIP]
    > 전자 메일 별칭은 드롭다운 목록의 도메인으로 끝나야 합니다. 목록에 다른 도메인 이름을 추가 하려면 [add a domain To Office 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain)을 참조 하십시오. 

5. 작업을 마치면 **Save (저장**)를 선택 합니다.

6. Office 365 전체를 새 별칭으로 채울 때까지 24시간을 기다립니다. 
    
    이제 사용자에 게 기본 주소와 별칭이 표시 됩니다. 예를 들어 메일이 지 민의 Hoffman의 기본 주소, Eliza@NodPublishers.com 및 별칭, Sales@NodPublishers.com 등으로 전송 되는 모든 메일은 메일이 지 민의의 받은 편지 함으로 이동 합니다.
    
  
7. **사용자가 회신 하면 *보낸* 사람 주소가 기본 전자 메일 별칭이 됩니다.** 예를 들어 메시지가 Sales@NodPublishers.com에 게 전송 되 고 메일이 지 민의의 받은 편지함에 도착 한다고 가정해 보겠습니다. 지민이 메시지에 회신하면 Sales@NodPublishers.com이 아니라 기본 전자 메일 주소가 보낸 사람으로 표시됩니다. 

::: moniker-end


## <a name="did-you-get-a-parameter-cannot-be-found-that-matches-parameter-name-emailaddresses"></a>"Parameter name EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다." 라는 메시지가 표시 되었습니까?


"**매개 변수 이름 EmailAddresses와 일치 하는 매개 변수를 찾을 수 없습니다**." 라는 오류 메시지가 표시 되 면 테 넌 트 설정이 완료 되는 데 시간이 더 오래 걸리거나 사용자 지정 도메인이 최근에 추가 된 경우에는이를 수행 하는 것입니다. 설정 프로세스를 완료하는 데 최대 4시간이 걸릴 수 있습니다. 설정 프로세스가 완료될 때까지 기다린 후 다시 시도하세요. 문제가 계속되는 경우 고객 지원에 문의하면 전체 동기화를 수행해 드립니다.
  
## <a name="did-you-purchase-your-subscription-from-godaddy-or-another-partner"></a>GoDaddy 또는 다른 파트너로부터 구독을 구입했나요?


GoDaddy 또는 다른 파트너로부터 구독을 구입한 경우 새 별칭을 기본으로 설정하려면 GoDaddy/파트너 관리 콘솔로 이동해야 합니다.
  
## <a name="related-articles"></a>관련 문서

[다른 주소에서 전자 메일 보내기](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e)

[사용자 이름 및 이메일 주소 변경](../add-users/change-a-user-name-and-email-address.md)
  

