---
title: 이전 직원 제거
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: '다음 검사 목록을 따라 Microsoft 365에서 직원을 제거 하 고 데이터를 보호 합니다. '
ms.openlocfilehash: 293ad26645aa3b190c25271273b29ac6c4ec8ed0
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/27/2020
ms.locfileid: "44387048"
---
# <a name="remove-a-former-employee"></a>이전 직원 제거

::: moniker range="o365-21vianet"

> [!NOTE]
> 관리 센터가 변경되고 있습니다. 사용자의 환경이 여기에 설명된 세부 정보와 맞지 않는 경우에는 [새 Microsoft 365 관리 센터 정보](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)를 참조하세요.

::: moniker-end
  
## <a name="sign-out-now"></a>지금 로그아웃!

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

직원을 제거 하는 방법에 대 한 간단한 동영상을 시청 하세요. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

이 비디오가 도움이 된 경우에는 [소규모 비즈니스 및 Microsoft 365를 처음 사용하는 사용자들을 위한 완전한 교육 시리즈](https://support.office.com/article/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)를 참조하세요.

직원을 제거 하려면 다음을 수행 합니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 사용자 이름 옆의 상자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)
    
4. 사용자 이름을 선택 하 여 해당 속성 창으로 이동 하 고 **OneDrive** 탭에서 **로그 아웃 시작**을 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 사용자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)

4. 사용자를 다시 선택 하 고 **OneDrive 설정을**확장 한 후 **로그 아웃**옆에 있는 **시작** 을 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 사용자를 선택 하 고 **암호 다시 설정을**선택 합니다.

3. 새 암호를 입력 하 고 **재설정**을 선택 합니다. (여기로 보내지 않습니다.)

4. 사용자를 다시 선택 하 고 **OneDrive 설정을**확장 한 후 **로그 아웃**옆에 있는 **시작** 을 선택 합니다.

::: moniker-end

    
한 시간 이내에 또는 현재 Microsoft 365 페이지에서 나간 후에 다시 로그인 하 라는 메시지가 표시 됩니다. (액세스 토큰은 한 시간 동안 유효 하므로 타임 라인은 해당 토큰에 남은 시간과 현재 웹 페이지에서 벗어나 이동 하는지 여부에 따라 달라 집니다.)
  
 **주의 사항**: 사용자가 웹용 Outlook에 있는 경우 사서함 주위를 클릭하는 것만으로는 즉시 로그아웃되지 않을 수 있습니다. OneDrive와 같은 다른 타일을 선택 하거나 브라우저를 새로 고치면 로그 아웃이 시작 됩니다. 
  
PowerShell을 사용하여 사용자를 즉시 로그아웃하려면 [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345) cmdlet을 참조하세요. 
  
전자 메일에서 다른 사람을 제거하는 데 걸리는 시간에 대한 자세한 내용은 [직원의 전자 메일 세션 종료에 대해 알아야 할 사항](#what-you-need-to-know-about-terminating-an-employees-email-session)을 참조하세요.
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>직원을 제거하고 데이터를 보호하기 위한 모든 단계의 개요
<a name="bkmk_now"> </a>

"직원이 퇴사하는 경우 데이터를 보호하려면 어떻게 해야 하나요?"라는 질문을 자주 받습니다. 이 문서에서는 Microsoft 365에 대 한 액세스를 차단 하는 방법과 데이터를 보호 하기 위해 수행 해야 하는 단계에 대해 설명 합니다.
  
> [!NOTE]
> 전역 관리자는 직원을 삭제 하 고, 전자 메일을 전달 하 고, 새로운 안내가 제공 되는 환경을 사용 하 여 OneDrive 콘텐츠로 수행할 작업을 선택할 수 있습니다. 자세한 내용은 [전역 관리자: 사용자 삭제](remove-former-employee.md)를 참조 하세요. 그러나 직원에 게 회사 데이터에 대 한 액세스 권한이 없는지 확인 하려면 여기에 나열 된 추가 단계를 모두 완료 하는 것이 좋습니다. 
  
간략한 개요는 다음과 같습니다. 각 단계는 이 문서에 자세히 설명되어 있습니다.
  
|||
|:-----|:-----|
|**단계** <br/> |**이렇게 하는 이유** <br/> |
|1. [이전 직원 사서함의 콘텐츠 저장](#save-the-contents-of-a-former-employees-mailbox) <br/> |해당 직원의 업무를 인수하는 사람에게 또는 소송이 발생하는 경우 유용합니다.  <br/> |
|2. [이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |이렇게 하면 이전 직원의 전자 메일 주소를 활성 상태로 유지할 수 있습니다. 이전 직원의 주소로 여전히 전자 메일을 보내는 고객 또는 파트너가 있는 경우 업무를 인수하는 사람에게 전자 메일이 전달됩니다.  <br/> |
|3. [이전 직원의 모바일 장치 초기화 및 차단](#wipe-and-block-a-former-employees-mobile-device) <br/> |휴대폰 또는 태블릿에서 비즈니스 데이터를 제거합니다.  <br/> |
|4. [Microsoft 365 데이터에 대 한 이전 직원의 액세스 차단](#block-a-former-employees-access-to-microsoft-365-data)<br/> |이를 통해 사용자가 이전 Microsoft 365 사서함 및 데이터에 액세스 하지 못합니다.  <br/><br/> **팁**: 사용자의 액세스를 차단 해도 해당 라이선스에 대 한 비용을 지불 하 고 있습니다. 라이선스 비용 지불을 중지하려면 구독에서 라이선스를 삭제(5단계)해야 합니다.           |
|5. [직원의 OneDrive 콘텐츠 이동](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |사용자의 라이선스만 제거하고 계정을 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/><br/> 계정을 삭제하기 전에 OneDrive의 콘텐츠를 액세스하기 쉬운 다른 위치로 이동해야 합니다. 직원의 계정을 삭제하면 해당 OneDrive의 콘텐츠는 **30** 일 동안 보관됩니다. 그러나 이 기간 동안 사용자의 계정을 복원하고 OneDrive 콘텐츠에 대한 액세스 권한을 얻을 수 있습니다. 사용자의 계정을 복원하는 경우에는 30일이 지난 후에도 OneDrive 콘텐츠에 계속 액세스할 수 있습니다.  <br/> |
|5a. 사용자가 개인용 컴퓨터를 사용하여 OneDrive 및 SharePoint에 액세스하는 경우 어떻게 해야 하나요?  <br/> |회사에서 발급한 컴퓨터 대신 개인용 컴퓨터를 사용하여 OneDrive 및 SharePoint에서 파일을 다운로드하는 경우 저장한 파일을 지울 방법이 없습니다.  <br/><br/> 컴퓨터와 동기화된 모든 파일에 계속 액세스할 수 있습니다.  <br/> |
|6. [이전 직원의 Microsoft 365 라이선스 제거 및 삭제](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |라이선스를 제거하면 다른 사람에게 해당 라이선스를 할당할 수 있습니다. 또는 다른 사람을 고용할 때까지 라이선스 비용을 지불하지 않도록 라이선스를 삭제할 수 있습니다.  <br/><br/> 라이선스를 제거하거나 삭제하면 사용자의 이전 전자 메일, 연락처 및 일정이 **30일** 간 보존된 후 영구적으로 삭제됩니다. 라이선스를 제거하거나 삭제하되 계정은 삭제하지 않으면 30일이 지난 후에도 사용자의 OneDrive에 있는 콘텐츠에 계속 액세스할 수 있습니다.  <br/> |
|7. [이전 직원의 사용자 계정 삭제](#delete-a-former-employees-user-account)<br/> |이렇게 하면 관리 센터에서 계정이 제거 됩니다. 깔끔하게 정리됩니다.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>이전 직원 사서함의 콘텐츠 저장
<a name="bkmk_preserve"> </a>

이전 직원 사서함의 콘텐츠를 저장하는 방법은 다음과 같은 두 가지가 있습니다.
  
1. Outlook 2013 또는 2016 버전에 이전 직원의 전자 메일 주소를 추가한 다음 데이터를 .pst 파일로 내보냅니다. 필요에 따라 다른 전자 메일 계정으로 데이터를 가져올 수 있습니다. 이 작업을 수행하는 방법을 알아보려면 [이전 사용자의 데이터 액세스 및 백업](get-access-to-and-back-up-a-former-user-s-data.md)을 참조하세요.
    
    또는
    
2. 사용자 계정을 삭제하기 전에 사서함에 대해 소송 보존 또는 원본 위치 유지를 적용합니다. 이 옵션은 첫 번째 옵션보다 훨씬 더 복잡하지만, Enterprise 요금제에 보관 및 법적 보존이 포함되어 있고 소송 가능성이 있으며 기술적으로 강력한 IT 부서가 있는 경우 수행할 가치가 있습니다.
    
    사서함을 "비활성 사서함"으로 전환하면 관리자, 준수 관리자 또는 레코드 관리자가 Exchange Online의 원본 위치 eDiscovery 도구를 사용하여 콘텐츠에 액세스하고 콘텐츠를 검색할 수 있습니다.
    
    비활성 사서함은 전자 메일을 받을 수 없으며 조직의 공유 주소록 또는 기타 목록에 표시되지 않습니다.
    
    사서함에 보존을 적용 하는 방법에 대 한 자세한 내용은 [Exchange Online에서 비활성 사서함 관리](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes)를 참조 하세요.
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>이전 직원의 전자 메일을 다른 직원에게 전달 또는 공유 사서함으로 변환
<a name="bkmk_forward"> </a>

이 단계에서는 이전 직원의 전자 메일 주소를 다른 직원에게 할당하거나 [사용자의 사서함을 공유 사서함](../email/convert-user-mailbox-to-shared-mailbox.md)으로 변환합니다. 
  
- **사서함이 50GB보다 작은 한** 라이선스 비용을 지불할 필요가 없으므로 공유 사서함을 만드는 것이 비용이 덜 드는 방법입니다. 50GB 이상이면 사서함에 라이선스를 할당해야 합니다. 
    
- 사서함을 공유 사서함으로 변환한 경우 이전 전자 메일을 모두 사용할 수 있습니다. 이렇게 하면 공간을 많이 차지할 수 있습니다.
    
- 전자 메일 전달을 설정한 경우 이제 이전 직원에게 전송되는  *새*  전자 메일만 현재 직원에게 전송됩니다. 
    
- 전자 메일을 전달하려면 이전 직원의 계정에 라이선스가 있어야 합니다.
    
 > [!IMPORTANT] 
 > 전자 메일 전달 또는 공유 사서함을 설정 하는 경우 끝에서 이전 직원의 계정을 삭제 하지 마세요. 전자 메일 전달 또는 공유 사서함의 기준 위치가 되는 기존 계정이 있어야 합니다. 

::: moniker range="o365-worldwide"  

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 **메일** 탭을 선택 합니다.

3. **전자 메일 전달**에서 **전자 메일 전달 관리**를 선택 합니다.

4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. **전달 주소** 상자에 전자 메일을 받게 될 현재 직원(또는 공유 사서함)의 전자 메일 주소를 입력합니다. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.
 
::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단 하려는 직원을 선택 하 고 **메일 설정을**확장 합니다.

3. **전자 메일 전달**옆에 있는 **편집**을 선택 합니다.

4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. **전달 주소** 상자에 전자 메일을 받게 될 현재 직원(또는 공유 사서함)의 전자 메일 주소를 입력합니다. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단 하려는 직원을 선택 하 고 **메일 설정을**확장 합니다.

3. **전자 메일 전달**옆에 있는 **편집**을 선택 합니다.

4. **이 사서함으로 전송된 모든 전자 메일을 전달** 을 켭니다. **전달 주소** 상자에 전자 메일을 받게 될 현재 직원(또는 공유 사서함)의 전자 메일 주소를 입력합니다. 
  
5. **저장**을 선택합니다. 
    
6. 이전 직원의 계정을 삭제하지 않습니다.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>이전 직원의 모바일 장치 초기화 및 차단
<a name="bkmk_mobile"> </a>

이전 직원이 조직 휴대폰을 보유했던 경우 해당 장치에서 모든 조직 데이터가 제거되고 해당 장치가 더 이상 Office 365에 연결될 수 없도록 Exchange 관리 센터를 사용하여 해당 장치를 초기화 및 차단할 수 있습니다.
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.

3. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다. 
    
4. 사용자를 선택 하 고 **모바일 장치**에서 **세부 정보 보기**를 선택 합니다. 
    
5. 모바일 장치 **세부 정보** 페이지의 **모바일**장치에서 모바일 장치를 선택 하 고 **데이터** ![ 지우기 장치 지우기를 선택한 ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) 다음 **차단을**선택 합니다. 
    
6. **저장**을 선택합니다. 
    
    **팁**: 온-프레미스 Blackberry Enterprise Service에서 사용자를 제거하거나 사용하지 않도록 설정해야 합니다. 또한 사용자에 대해 Blackberry 장치를 사용하지 않도록 설정해야 합니다. 사용자를 사용하지 않도록 설정하는 방법에 대한 구체적인 단계가 필요한 경우 Blackberry Business Cloud Services Administration Guide를 참조하세요. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Microsoft 365 데이터에 대 한 이전 직원의 액세스 차단
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > 계정 차단이 적용 되는 데 최대 24 시간이 걸릴 수 있습니다. 사용자의 로그인 액세스를 즉시 방지 해야 하는 경우 [암호를 다시 설정한](reset-passwords.md) 다음 모든 장치에서 Microsoft 365 세션에서 로그 아웃 하는 일회성 이벤트를 시작 해야 합니다. [지금 로그아웃!](#sign-out-now)을 참조하세요.
 

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 사용자 이름 아래에 **이 사용자 차단**에 대 한 기호를 선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단할 직원을 선택한 다음 **로그인 차단을**선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단할 직원을 선택한 다음 **로그인 차단을**선택 합니다.

3. **사용자가 로그인**하지 못하도록 차단을 선택한 다음 **저장**을 선택 합니다. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>전자 메일(Exchange Online)에 대한 이전 직원의 액세스 차단
<a name="bkmk_block_email"> </a>

Microsoft 365 구독의 일부로 전자 메일이 있는 경우 다음 단계를 수행 하 여 이전 직원이 전자 메일에 액세스 하지 못하도록 차단 하려면 Exchange 관리 센터에 로그인 해야 합니다.
  

1. <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange 관리 센터</a>로 이동합니다.
     
2. Exchange 관리 센터에서 **받는 사람** \> **사서함** 으로 이동합니다. 
    
3. 사용자를 두 번 클릭 하 고 **사서함 기능** 페이지로 이동 합니다. **모바일 장치**에서 **Exchange ActiveSync 사용 안 함** 및 **장치용 OWA 사용 안** 함을 **선택 하 고** 메시지가 표시 되 면 둘 다에 대해 응답 합니다. 
    
4. **전자 메일 연결**에서 메시지가 표시 되 면 **사용 안 함** 및 대답이 **예** 를 선택 합니다. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>이전 직원의 Microsoft 365 라이선스 제거 및 삭제
<a name="bkmk_remove"> </a>

누군가가 조직에서 나간 후에 라이선스 비용을 계속 지불 하지 않으려면 Microsoft 365 라이선스를 제거한 다음 구독에서 삭제 해야 합니다. 구독에서 라이선스를 삭제하지 않도록 선택하면 해당 라이선스를 다른 사용자에게 할당할 수 있습니다.
  
라이선스를 제거하면 해당 사용자의 모든 데이터가 30일간 보존됩니다. 데이터에 [액세스](get-access-to-and-back-up-a-former-user-s-data.md)하거나 해당 사용자가 복귀하면 계정을 [복원](restore-user.md)할 수 있습니다. 30 일 후에는 사용자의 모든 데이터 (SharePoint Online에 저장 된 문서를 제외)가 Microsoft 365에서 영구적으로 삭제 되며 복구할 수 없습니다. 

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 차단할 직원의 이름을 선택 하 고 **라이선스 및 앱** 탭을 선택 합니다.

4. 제거할 라이선스에 대 한 확인란의 선택을 취소 한 다음 **변경 내용 저장**을 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단할 직원을 선택 하 고 **제품 라이선스**옆에 있는 **편집**을 선택 합니다.

3. **제품 라이선스** 페이지에서 제거 하려는 라이선스를 설정/해제 하 고 **저장**을 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 차단할 직원을 선택 하 고 **제품 라이선스**옆에 있는 **편집**을 선택 합니다.

3. **제품 라이선스** 페이지에서 제거 하려는 라이선스를 설정/해제 하 고 **저장**을 선택 합니다.

::: moniker-end


다른 사람을 고용할 때까지 **비용을 지불하는 라이선스 수를 줄이려면** 다음을 수행합니다. 

::: moniker range="o365-worldwide"



1. 관리 센터에서 **결제**\> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">내 상품</a>페이지로 이동하세요.


::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">구독</a> 페이지로 이동합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **청구** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">구독</a> 페이지로 이동합니다.

::: moniker-end
    
2. 라이선스 **추가/제거** 를 선택 하 여 다른 사람을 고용 하기 전까지 라이센스 비용을 지불 하지 않을 수 있습니다.

비즈니스에 다른 사람을 [추가](add-users.md) 하면 동시에 라이선스를 구입 하 라는 메시지가 표시 되며 한 단계만 진행 됩니다.
    
비즈니스용 Microsoft 365에 대 한 사용자 라이선스를 관리 하는 방법에 대 한 자세한 내용은 microsoft 365의 사용자 [에 게 라이선스 할당](../manage/assign-licenses-to-users.md)및 [비즈니스용 microsoft 365의 사용자](../manage/remove-licenses-from-users.md)에 대 한 라이선스 제거를 참조 하세요.
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>삭제된 직원 계정이 비즈니스용 Skype에 영향을 미치는 방식
<a name="bkmk_remove"> </a>

Office 365에서 사용자 라이선스를 제거하면 사용자와 연결된 PSTN 호출 번호가 해제됩니다. 이 PSTN 호출 번호를 다른 사용자에게 할당할 수 있습니다.
  
사용자가 큐 그룹에 속하는 경우 더 이상 통화 큐 에이전트의 실행 가능한 대상이 아닙니다. 따라서 통화 큐와 연결된 그룹에서도 사용자를 제거하는 것이 좋습니다. 
  
## <a name="delete-a-former-employees-user-account"></a>이전 직원의 사용자 계정 삭제
<a name="bkmk_delete"> </a>

이전 직원의 모든 사용자 데이터에 액세스하여 저장한 후에는 이전 직원의 계정을 삭제할 수 있습니다.
  
전자 메일 전달을 설정했거나 공유 사서함으로 변환한 경우 계정을 삭제하지 마세요. 전달 또는 공유 사서함의 기준 위치가 되는 계정이 필요합니다.

::: moniker range="o365-worldwide"

> [!NOTE]
> 새로운 Microsoft 365 관리 센터를 사용하지 않는 경우 홈페이지 상단에 있는 **새 관리 센터 시도** 토글을 선택하여 켤 수 있습니다.

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">활성 사용자</a> 페이지로 이동합니다.

2. 삭제할 직원의 이름을 선택 합니다.

3. 사용자 이름 아래에서 **사용자 삭제**에 대 한 기호를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

::: moniker range="o365-germany"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 삭제할 직원의 이름을 선택 합니다.

3. 페이지 맨 위에서 **사용자 삭제**를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

::: moniker range="o365-21vianet"

1. 관리 센터에서 **사용자** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">활성 사용자</a> 페이지로 이동합니다..

2. 삭제할 직원의 이름을 선택 합니다.

3. 페이지 맨 위에서 **사용자 삭제**를 선택 합니다. 이 사용자에 대해 원하는 옵션을 선택 하 고 **사용자 삭제**를 선택 합니다.

::: moniker-end

사용자를 삭제하면 해당 계정은 약 30일간 비활성 상태가 됩니다. 이 기간에 계정을 복원하지 않으면 영구적으로 삭제됩니다.
  
### <a name="does-your-organization-use-active-directory"></a>조직에서 Active Directory를 사용하나요?

조직에서 로컬 Active Directory 환경에서 사용자 계정을 Microsoft 365와 동기화 하는 경우 로컬 Active Directory 서비스에서 해당 사용자 계정을 삭제 하 고 복원 해야 합니다. Office 365에서는 해당 사용자 계정을 삭제하거나 복원할 수 없습니다.
  
자세한 내용은 [사용자 계정 삭제](https://go.microsoft.com/fwlink/?linkid=841808)문서를 참조 하십시오.
  
Azure Active Directory를 사용하는 경우 [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet을 참조하세요. 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>직원의 전자 메일 세션 종료에 대해 알아야 할 사항
<a name="bkmk_session"> </a>

다음은 전자 메일(Exchange)에서 직원을 제거하는 방법에 대한 정보입니다.
  
|||
|:-----|:-----|
|**실행할 수 있는 작업** <br/> |**방법** <br/> |
|세션(예: 웹용 Outlook, Outlook, Exchange Active Sync 등) 종료 및 새 세션 열기  <br/> |암호 재설정  <br/> |
|세션 종료 및 향후 세션에 대한 액세스 차단(모든 프로토콜에 대해)  <br/> |계정을 사용하지 않도록 설정합니다. 예(Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|특정 프로토콜(예: ActiveSync)에 대한 세션 종료  <br/> |프로토콜을 사용하지 않도록 설정합니다. 예(Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
위 작업은 다음 세 위치에서 수행할 수 있습니다.
  
|||
|:-----|:-----|
|**여기에서 세션을 종료하는 경우** <br/> |**소요 시간** <br/> |
|Exchange 관리 센터에서 또는 PowerShell을 사용하는 경우  <br/> |30분 이내의 지연이 예상됨  <br/> |
|Azure Active Directory 관리 센터에서  <br/> |60분의 지연이 예상됨  <br/> |
|온-프레미스 환경에서  <br/> |3시간 이상의 지연이 예상됨  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>계정 종료에 대해 가장 빠른 응답을 받는 방법

 **가장 빠름**: Exchange 관리 센터(PowerShell 사용) 또는 Azure Active Directory 관리 센터를 사용합니다. 온-프레미스 환경에서 DirSync를 통해 변경 내용을 동기화하는 데 몇 시간이 걸릴 수 있습니다. 
  
 **온 - 프레미스 및 Exchange Datacenter에 있는 사용자에게 가장 빠름**: Azure Active Directory 관리 센터/Exchange 관리 센터를 사용하여 세션을 종료하고 온 - 프레미스 환경에서도 변경합니다. 그렇지 않으면 Azure Active Directory 관리 센터/Exchange 관리 센터의 변경 사항이 DirSync에 의해 덮어 쓰여집니다. 
  
## <a name="related-articles"></a>관련 문서

[사용자 복원](restore-user.md)
  
